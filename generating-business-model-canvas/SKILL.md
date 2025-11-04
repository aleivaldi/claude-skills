---
name: generating-business-model-canvas
description: Genera Business Model Canvas in Excel (4 canvas) + Markdown esplicativo. Usa script Python per popolare Excel (no permessi). Workflow 6-step con JSON data.
---

# Generating Business Model Canvas

## Compito

Genera Business Model Canvas in **Excel** (4 canvas) + **Markdown** esplicativo.

**Output**:
1. `business-model-canvas.xlsx` - 4 canvas compilati (Business Model, Lean, Personas, Value Proposition)
2. `business-model-canvas.md` - Documentazione dettagliata che spiega le scelte

---

## Workflow (6 Step)

### A. Analizza Input
Raccogli brief (file/chat/allegati) + competitor analysis (opzionale).

### B. Chiedi Integrazioni (loop)
Valuta sufficienza info. Se OK → procedi. Se mancano dati → chiedi clarification.

### C. Genera Excel
1. **Bash**: Copia template
2. **Genera JSON** con dati strutturati (vedi `scripts/populate_excel.py` per formato)
3. **Write**: Crea `/tmp/bmc_data.json`
4. **Bash**: Esegui `python3 ~/.claude/skills/generating-business-model-canvas/scripts/populate_excel.py business-model-canvas.xlsx /tmp/bmc_data.json`
5. **Bash**: Rimuovi `/tmp/bmc_data.json`

### D. Verifica Excel (loop)
Annuncia completamento → chiedi review → applica modifiche → loop

### E. Genera Markdown
**Write**: Crea `business-model-canvas.md` con dettagli estesi basati su Excel approvato.

### F. Verifica Markdown (loop)
Annuncia completamento → chiedi review → applica modifiche → loop

---

## Script Python (pre-installati)

### `scripts/populate_excel.py`
Script principale che popola Excel da JSON.

**Usage**:
```bash
python3 populate_excel.py <excel_file> <data_json>
```

**JSON format**:
```json
{
  "metadata": {
    "project": "Nome Progetto",
    "author": "Team",
    "date": "2025-01-04",
    "version": "v1.0"
  },
  "sheet1": {
    "key_partners": "🔴 Partner 1\n🔴 Partner 2\n...",
    "key_activities": "...",
    "key_resources": "...",
    "value_propositions": "...",
    "customer_relationships": "...",
    "customer_segments": "...",
    "channels": "...",
    "cost_structure": "...",
    "revenue_streams": "..."
  },
  "sheet2": { ... },
  "sheet3": {
    "personas": [
      {
        "name": "Persona 1",
        "description": "...",
        "attributes": ["attr1", "attr2", ...]
      }
    ]
  },
  "sheet4": { ... }
}
```

Vedi firme funzioni in `scripts/sheet_populators.py` per dettagli campi.

---

## File di Riferimento

- `scripts/populate_excel.py` - Script principale
- `scripts/sheet_populators.py` - Funzioni per ogni sheet (firme dettagliate)
- `template-structure.md` - Mappatura celle Excel (reference)
- `process-6-steps.md` - Dettagli processo 6-step
- `questions/` - Domande per canvas (1-4)

---

## Regole Chiave

- ❌ **MAI** chiedere permesso per creare/modificare file
- ✅ Usa script Python (no generazione codice inline)
- ✅ Un solo JSON temporaneo in `/tmp/`
- ✅ Feedback loop per Excel e Markdown
- ✅ Priorità colorate: 🔴 (alta), 🟡 (media), 🟢 (bassa)
- ✅ Lingua: segui lingua del brief

---

## Gestione Errori

- Brief mancante → chiedi come fornire
- File non trovato → verifica path
- Script error → mostra errore, proponi fix
- Info insufficienti → Step B loop

