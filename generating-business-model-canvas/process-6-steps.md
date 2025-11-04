# Processo in 6 Step - Dettaglio Completo

Questo documento descrive in dettaglio il processo di generazione del Business Model Canvas.

---

## Step A: Analizza Input

**Obiettivo**: Raccogliere brief del progetto (obbligatorio) e competitor analysis (opzionale)

**Azioni**:
1. **Identifica fonte brief**:
   - Chiedi all'utente come vuole fornire il brief
   - Opzioni: file esistente, uno o più allegati, informazioni in chat
   - Usa **AskUserQuestion** se non chiaro

2. **Raccogli brief progetto**:
   - **Se file**: Usa **Read** tool per leggere file indicato dall'utente
   - **Se allegati**: Usa **Read** per leggere tutti i file allegati
   - **Se chat**: Poni domande essenziali guidate da `questions/` (leggi canvas necessari)

3. **Raccogli competitor analysis (opzionale)**:
   - Chiedi se disponibile
   - **Se sì**: Leggi file o raccogli info in chat
   - **Se no**: Procedi senza (NON bloccare)

**Output**: Brief completo + competitor analysis (se disponibile)

**Tool Usage**:
- ✅ **AskUserQuestion**: Chiedi come utente vuole fornire brief (se non chiaro)
- ✅ **Read**: Leggi file brief (se fornito come file)
- ✅ **Read**: Leggi file allegati (se forniti)
- ✅ **Read**: Leggi competitor analysis (se presente)
- ❌ **NON assumere** nomi file fissi

---

## Step B: Chiedi Integrazioni (loop fino a esaustività)

**Obiettivo**: Valutare se le informazioni raccolte sono sufficienti per generare BMC completo

**Azioni**:
1. **Analizza informazioni** raccolte in Step A:
   - Esamina brief + competitor per ogni canvas
   - Identifica **solo** informazioni mancanti o ambigue per generare BMC completo
   - Valuta sufficienza complessiva

2. **Se informazioni SUFFICIENTI**:
   - Comunica: **"Bene, quanto mi hai dato è più che sufficiente, procedo con la generazione del BMC"**
   - Vai direttamente a **Step C**

3. **Se informazioni INSUFFICIENTI**:
   - Comunica: "Ho bisogno di alcune informazioni aggiuntive per procedere con la creazione del Business Model Canvas"
   - Usa **AskUserQuestion**: "Preferisci rispondere qui in chat o ricevere un file con le domande?"
   - **Se chat**: Poni domande mirate una per una, raccogli risposte
   - **Se file**:
     - Crea `clarification-questions.md` con **Write**
     - Organizza domande per canvas
     - Utente compila file
     - Leggi risposte con **Read**
   - **LOOP**: Ripeti valutazione sufficienza fino a info esaustive

**Output**: Conferma info sufficienti + eventuali risposte clarification

**Tool Usage**:
- ✅ **Analizza**: Valuta sufficienza info per ogni canvas
- ✅ **Se SUFFICIENTE**: Comunica "Bene, quanto mi hai dato è più che sufficiente, procedo con la generazione del BMC"
- ✅ **Se INSUFFICIENTE**:
  - **AskUserQuestion**: Chiedi se preferisce chat o file per clarification
  - **Se file**: **Write** `clarification-questions.md`, poi **Read** risposte
  - **Se chat**: Poni domande mirate, raccogli risposte
  - **LOOP**: Ripeti fino a info esaustive
- ❌ **NON proporre** risposte per conferma (genera direttamente)

---

## Step C: Genera Excel

**Obiettivo**: Creare business-model-canvas.xlsx con tutti i 5 canvas compilati

**⚠️ CRITICO - PRIMA DI SCRIVERE CODICE**:
- **LEGGI `template-structure.md` per OGNI SHEET** prima di generare script Python
- **CONSULTA `anti-patterns.md`** per evitare errori comuni
- Ogni sheet ha struttura DIVERSA (merged vs. separate)
- Sheet 1: Tutte celle merged
- Sheet 2: MISTA (merged + separate)
- Sheet 3-5: Strutture diverse

**Azioni**:
1. **Prepara template**:
   - Copia template: `cp ~/.claude/skills/generating-business-model-canvas/templates/business-model-canvas-template.xlsx ./business-model-canvas.xlsx`
   - Template sempre disponibile (incluso nella skill)
   - **NOTA**: Se utente ha hook che richiedono conferma per `cp`, questo è normale

2. **Genera contenuto per tutti i 5 canvas**:
   - Analizza brief + competitor + risposte clarification
   - Per ogni canvas, estrai info e assegna priorità 🔴🟡🟢
   - Mantieni contenuto **sintetico** (Excel è visual reference)
   - Usa `questions/` come guida (leggi file canvas specifici solo se necessario)

3. **Popola Excel via Bash + Python + openpyxl**:
   - **CRITICO**: Popola UN FOGLIO ALLA VOLTA per evitare script troppo complessi
   - **CRITICO**: Usa file Python temporaneo, NON inline con `python3 -c`
   - **NO heredoc `<< EOF`**: Causa problemi con escape di stringhe complesse
   - Per celle merged: scrivi solo nella cella top-left con `\n` per andare a capo
   - Abilita wrap_text=True e vertical='top' per celle merged
   - Pattern: Write script Python → Bash esegue script → rm script

**Output**: business-model-canvas.xlsx creato con 5 canvas compilati

**Tool Usage**:
- ✅ **Bash**: Copia template Excel
- ✅ **Write**: Crea script Python temporaneo
- ✅ **Bash**: Esegue script Python
- ✅ **Bash**: Rimuove script temporaneo

**Approccio corretto - Popolare un foglio**:

**Step 1**: Crea script Python con Write tool
```python
# File: /tmp/populate_bmc_sheet1.py
from openpyxl import load_workbook
from openpyxl.styles import Alignment

wb = load_workbook('business-model-canvas.xlsx')
ws = wb['Business Model Canvas']

# Metadata
ws['J4'] = 'Nome Progetto'
ws['N4'] = 'Team'
ws['U4'] = 'v1.0'

# Key Partners (merged B10:E47) - scrivi solo in top-left B10
content = """🔴 Partner critico 1
🔴 Partner critico 2
🟡 Partner importante 3"""
ws['B10'] = content
ws['B10'].alignment = Alignment(wrap_text=True, vertical='top')

# Key Activities (merged F10:I27) - scrivi solo in top-left F10
content = """🔴 Attività critica 1
🔴 Attività critica 2
🟡 Attività importante 3"""
ws['F10'] = content
ws['F10'].alignment = Alignment(wrap_text=True, vertical='top')

# Value Propositions (merged J10:M47) - scrivi solo in top-left J10
content = """🔴 Valore principale 1
🔴 Valore principale 2
🟡 Valore secondario 3"""
ws['J10'] = content
ws['J10'].alignment = Alignment(wrap_text=True, vertical='top')

# ... continua per tutte le sezioni del foglio

wb.save('business-model-canvas.xlsx')
print('✅ Sheet Business Model Canvas completato')
```

**Step 2**: Esegui con Bash
```bash
python3 /tmp/populate_bmc_sheet1.py
```

**Step 3**: Rimuovi script temporaneo
```bash
rm /tmp/populate_bmc_sheet1.py
```

**Esempio Sheet 2 (Lean Canvas) - Struttura MISTA**:

Sheet 2 combina celle merged + celle separate. Esempio:

```python
# File: /tmp/populate_bmc_sheet2.py
from openpyxl import load_workbook
from openpyxl.styles import Alignment

wb = load_workbook('business-model-canvas.xlsx')
ws = wb['Lean Canvas']

# Metadata
ws['J4'] = 'Nome Progetto'
ws['N4'] = 'Team'
ws['U4'] = 'v1.0'

# ✅ CELLE MERGED - Usa multiline string
ws['B10'] = """🔴 Problem 1
🔴 Problem 2
🔴 Problem 3"""
ws['B10'].alignment = Alignment(wrap_text=True, vertical='top')

ws['F10'] = """🔴 Solution 1
🔴 Solution 2
🔴 Solution 3"""
ws['F10'].alignment = Alignment(wrap_text=True, vertical='top')

ws['J12'] = '🔴 Unique Value Proposition chiara e convincente'
ws['J12'].alignment = Alignment(wrap_text=True, vertical='top')

# ⚠️ CELLE SEPARATE - Scrivi in righe diverse
ws['F32'] = '🔴 Metric 1 - Target 50-100'
ws['F33'] = '🔴 Metric 2 - Target €100k MRR'
ws['F34'] = '🟡 Metric 3 - NPS > 40'

ws['N12'] = '🔴 Unfair Advantage 1'
ws['N13'] = '🔴 Unfair Advantage 2'

ws['N32'] = '🔴 Channel 1 - Direct sales'
ws['N33'] = '🟡 Channel 2 - Partner network'

ws['R12'] = '🔴 Bar e pub 20-100 coperti'
ws['R13'] = '🔴 Gestori locali 30-50 anni'

ws['B52'] = '🔴 CAC: €50/customer'
ws['B53'] = '🔴 Hosting: €500/mese'
ws['B54'] = '🟡 Development: €8k/mese'

ws['L52'] = '🔴 Revenue Model: Subscription'
ws['L53'] = '🔴 LTV: €2400'
ws['L54'] = '🔴 Revenue Y1: €120k'

wb.save('business-model-canvas.xlsx')
print('✅ Sheet Lean Canvas completato')
```

**BEST PRACTICES per contenuto celle**:
1. **Leggi SEMPRE template-structure.md** per capire struttura dello sheet
2. **Sheet 1**: Tutte celle merged (usa multiline string)
3. **Sheet 2**: MISTA - merged + separate (vedi esempio sopra)
4. **Sheet 3-5**: Diverse strutture (consulta template-structure.md)
5. **Usa multiline string `"""..."""`** per celle merged (più leggibile di `\n`)
6. **Scrivi SOLO nella cella top-left** delle celle merged (es. B10, NON B11, B12...)
7. **Per celle separate**: Scrivi in righe diverse (F32, F33, F34...)
8. **UN FOGLIO ALLA VOLTA**: Crea script separati per ogni sheet (più gestibile)

- ❌ **MAI** chiedere permesso per creare file (è implicito)
- ❌ **MAI** usare mcp__ide__executeCode (richiede notebook)

**NOTA CRITICA**: NON chiedere permesso per creare file (è implicito nella richiesta utente)

---

## Step D: Verifica Excel (loop fino a OK)

**Obiettivo**: Iterare modifiche Excel fino ad approvazione utente

**Azioni**:
1. **Annuncia completamento**:
   - "✅ Ho generato business-model-canvas.xlsx con i 5 canvas compilati"

2. **Chiedi review**:
   - "Apri il file e verificalo. Quando hai finito, dimmi se va bene o se vuoi modifiche"
   - Aspetta feedback utente

3. **Gestisci feedback (LOOP)**:
   - **Se "va bene" / "OK" / "approvato"**: Vai a **Step E**
   - **Se modifiche richieste**:
     - Applica modifiche via **Skill(xlsx)**
     - Annuncia modifica completata
     - Chiedi se altre modifiche necessarie
     - **LOOP**: Ripeti fino ad approvazione

**Output**: Excel approvato dall'utente

**Tool Usage**:
- ✅ **Annuncia** completamento Excel
- ✅ **Chiedi review**: "Apri il file e verificalo. Va bene o vuoi modifiche?"
- ✅ **LOOP feedback Excel**:
  - **Se modifiche**: **Bash + Python + openpyxl** per applicare → annuncia → chiedi altre modifiche
  - **Se approvato**: Procedi a Step E
- ❌ **MAI** chiedere permesso per modificare file (è implicito nel loop)

**NOTA CRITICA**: NON chiedere permesso per modificare file (è implicito nel loop feedback)

---

## Step E: Genera Markdown

**Obiettivo**: Creare business-model-canvas.md che spiega e dettagliare quanto inserito nell'Excel

**Azioni**:
1. **Genera documento Markdown**:
   - Usa **Write** tool per creare file
   - Basato su Excel approvato (fonte unica di verità)
   - Include dettagli estesi per ogni canvas
   - Formato: 300-500 righe, bullet points + tabelle
   - Sezioni:
     - Executive Summary
     - Canvas 1: Business Model Canvas (dettagliato)
     - Canvas 2: Lean Canvas (dettagliato)
     - Canvas 3: Customer Personas (dettagliato)
     - Canvas 4: Channel Implementation (dettagliato)
     - Canvas 5: Value Proposition Canvas (dettagliato)
     - Appendix: Note e Considerazioni
   - **Focus**: Spiega PERCHÉ le scelte fatte nell'Excel, non solo ripeterle

**Output**: business-model-canvas.md creato

**Tool Usage**:
- ✅ **Write**: Crea business-model-canvas.md
  - Basato su Excel approvato (fonte unica di verità)
  - Formato dettagliato (300-500 righe)
  - Spiega PERCHÉ le scelte fatte nell'Excel
- ❌ **MAI** chiedere permesso per creare file (è implicito)
- ❌ **MAI** Write su file esistente (usa Edit)

**NOTA CRITICA**: NON chiedere permesso per creare file (è implicito nella richiesta utente)

---

## Step F: Verifica Markdown (loop fino a OK)

**Obiettivo**: Iterare modifiche Markdown fino ad approvazione utente

**Azioni**:
1. **Annuncia completamento**:
   - "✅ Ho generato business-model-canvas.md con documentazione dettagliata che spiega le scelte nell'Excel"

2. **Chiedi review**:
   - "Leggi il documento. Va bene o vuoi modifiche?"
   - Aspetta feedback utente

3. **Gestisci feedback (LOOP)**:
   - **Se "va bene" / "OK" / "approvato"**: Vai a Step 4
   - **Se modifiche richieste**:
     - Usa **Read** poi **Edit** per applicare modifiche
     - Annuncia modifica completata
     - Chiedi se altre modifiche necessarie
     - **LOOP**: Ripeti fino ad approvazione

4. **Annuncia completamento finale**:
   - Conferma 2 file finali approvati
   - Riepilogo canvas inclusi
   - Suggerisci next steps (es. requirements tecnici, pitch deck)

**Output**: Markdown approvato dall'utente + deliverable completo (Excel + MD)

**Tool Usage**:
- ✅ **Annuncia** completamento Markdown
- ✅ **Chiedi review**: "Leggi il documento. Va bene o vuoi modifiche?"
- ✅ **LOOP feedback Markdown**:
  - **Se modifiche**: **Read** poi **Edit** → annuncia → chiedi altre modifiche
  - **Se approvato**: Annuncia completamento finale
- ❌ **MAI** chiedere permesso per modificare file (è implicito nel loop)

---

## Riepilogo Flusso Completo

```
Step A: Analizza Input
  ↓ (brief + competitor)
Step B: Chiedi Integrazioni (loop)
  ↓ (info sufficienti)
Step C: Genera Excel
  ↓ (business-model-canvas.xlsx)
Step D: Verifica Excel (loop)
  ↓ (Excel approvato)
Step E: Genera Markdown
  ↓ (business-model-canvas.md)
Step F: Verifica Markdown (loop)
  ↓ (MD approvato)
Completamento! (2 file finali)
```

---

## Note Importanti

1. **NO Richieste Permesso**: Mai chiedere permesso per creare/modificare file (implicito)
2. **Loop Espliciti**: Step B, D, F hanno loop fino a condizione soddisfatta
3. **Comunicazione Sufficienza**: Step B deve comunicare esplicitamente se info sufficienti
4. **Excel Prima**: Output primario, MD è secondario/esplicativo
5. **Skill xlsx**: SEMPRE usare per manipolazione Excel, MAI Python diretto
