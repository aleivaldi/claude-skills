# Anti-Patterns - Errori Comuni da Evitare

Questo documento elenca gli errori comuni nella generazione del Business Model Canvas.

---

## ❌ Anti-Pattern 1: Usare heredoc o inline Python

**SBAGLIATO**:
```bash
python3 << 'EOF'
from openpyxl import load_workbook
ws['B10'] = "🔴 Valore con "virgolette" - problema!"
EOF
```

**PROBLEMA**:
- Errori di escape con virgolette, emoji, caratteri speciali
- Script illeggibili e difficili da debuggare
- SyntaxError: unterminated string literal

**CORRETTO**:
```python
# File: /tmp/populate.py
from openpyxl import load_workbook
ws['B10'] = """🔴 Valore con "virgolette" - ok!"""
```
```bash
python3 /tmp/populate.py && rm /tmp/populate.py
```

---

## ❌ Anti-Pattern 2: NON leggere template-structure.md

**SBAGLIATO**:
```python
# Assumo che F32 sia merged come nel Sheet 1
ws['F32'] = """🔴 Metric 1
🔴 Metric 2
🔴 Metric 3"""  # ← ERRORE: F32 NON è merged in Sheet 2!
```

**PROBLEMA**:
- AttributeError: 'MergedCell' object attribute 'value' is read-only
- Ogni sheet ha struttura DIVERSA

**CORRETTO**:
1. **LEGGI template-structure.md per lo sheet specifico**
2. Sheet 2 - Key Metrics usa celle SEPARATE:
```python
ws['F32'] = '🔴 Metric 1'
ws['F33'] = '🔴 Metric 2'
ws['F34'] = '🔴 Metric 3'
```

---

## ❌ Anti-Pattern 3: Scrivere in celle merged non top-left

**SBAGLIATO**:
```python
# B10:E47 è merged, ma scrivo in B12, B13, B14
ws['B12'] = '🔴 Partner 1'  # ← ERRORE: B12 è dentro merge B10:E47
ws['B13'] = '🔴 Partner 2'  # ← ERRORE: read-only
ws['B14'] = '🔴 Partner 3'  # ← ERRORE: read-only
```

**PROBLEMA**:
- AttributeError: 'MergedCell' object attribute 'value' is read-only
- Scrivi SOLO nella cella top-left del merge

**CORRETTO**:
```python
# Scrivi TUTTO nella top-left B10 con multiline string
ws['B10'] = """🔴 Partner 1
🔴 Partner 2
🔴 Partner 3"""
ws['B10'].alignment = Alignment(wrap_text=True, vertical='top')
```

---

## ❌ Anti-Pattern 4: Popolare tutti i fogli in un unico script

**SBAGLIATO**:
```python
# File da 500+ righe con tutti i 5 fogli
wb = load_workbook('file.xlsx')
# ... 100 righe per Sheet 1
# ... 100 righe per Sheet 2
# ... (errore in riga 548)
```

**PROBLEMA**:
- Script troppo complessi difficili da debuggare
- Un errore blocca tutto
- Escape problems in script lunghi

**CORRETTO**:
```python
# File 1: /tmp/populate_sheet1.py (solo Sheet 1)
# File 2: /tmp/populate_sheet2.py (solo Sheet 2)
# File 3: /tmp/populate_sheet3.py (solo Sheet 3)
# ...
```

**Esegui uno alla volta**:
```bash
python3 /tmp/populate_sheet1.py && rm /tmp/populate_sheet1.py
python3 /tmp/populate_sheet2.py && rm /tmp/populate_sheet2.py
```

---

## ❌ Anti-Pattern 5: Non usare multiline string per celle merged

**SBAGLIATO**:
```python
ws['B10'] = '🔴 Partner 1\n🔴 Partner 2\n🔴 Partner 3'  # Meno leggibile
```

**PROBLEMA**:
- Stringhe con `\n` inline difficili da leggere e manutenere
- Escape problems con caratteri speciali

**CORRETTO**:
```python
ws['B10'] = """🔴 Partner 1
🔴 Partner 2
🔴 Partner 3"""  # Più leggibile
ws['B10'].alignment = Alignment(wrap_text=True, vertical='top')
```

---

## ❌ Anti-Pattern 6: Confondere Sheet 1 e Sheet 2

**Sheet 1 (Business Model Canvas)**:
- ✅ TUTTE celle merged grandi
- B10, F10, J10, N10, R10, F28, N28, B48, J48

**Sheet 2 (Lean Canvas)**:
- ✅ ALCUNE celle merged: B10, B30, F10, J12, J30
- ⚠️ ALTRE celle separate: F32-F46 (metrics), N12-N26 (unfair adv), N32-N46 (channels), R12-R13 (segments), R30-R36 (early adopters), B52-B60 (costs), L52-L60 (revenue)

**ERRORE COMUNE**: Assumere che Sheet 2 funzioni come Sheet 1
**SOLUZIONE**: Leggi template-structure.md per capire la struttura di ogni sheet

---

## ✅ Checklist Prima di Generare Script

Prima di scrivere codice Python per popolare un sheet:

1. [ ] Ho letto `template-structure.md` per questo sheet specifico?
2. [ ] So quali celle sono merged e quali sono separate?
3. [ ] Sto usando file Python temporaneo in `/tmp/` (NON heredoc/inline)?
4. [ ] Sto popolando UN SOLO FOGLIO in questo script?
5. [ ] Sto usando multiline string `"""..."""` per celle merged?
6. [ ] Sto scrivendo SOLO nella cella top-left per merged cells?
7. [ ] Per celle separate, scrivo in righe diverse (F32, F33, F34...)?

---

## Summary: Pattern Corretto

```python
# File: /tmp/populate_sheetN.py
from openpyxl import load_workbook
from openpyxl.styles import Alignment

wb = load_workbook('business-model-canvas.xlsx')
ws = wb['Nome Sheet']

# Metadata
ws['J4'] = 'Project'
ws['N4'] = 'Team'
ws['U4'] = 'v1.0'

# CELLE MERGED - usa multiline string + alignment
ws['B10'] = """🔴 Item 1
🔴 Item 2
🟡 Item 3"""
ws['B10'].alignment = Alignment(wrap_text=True, vertical='top')

# CELLE SEPARATE - scrivi in righe diverse
ws['F32'] = '🔴 Item 1'
ws['F33'] = '🔴 Item 2'
ws['F34'] = '🟡 Item 3'

wb.save('business-model-canvas.xlsx')
print('✅ Sheet completato')
```

```bash
python3 /tmp/populate_sheetN.py && rm /tmp/populate_sheetN.py
```
