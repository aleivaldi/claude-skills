---
name: generating-business-model-canvas
description: Genera Business Model Canvas professionale principalmente in Excel (output primario, 5 canvas con priorità 🔴🟡🟢) + Markdown esplicativo (secondario). Input flessibile (file/chat/allegati). Processo 6-step: analizza→clarifica→genera Excel→verifica→genera MD→verifica. Valuta sufficienza input. No richieste permesso. Usa openpyxl direttamente via Bash.
---

# Generating Business Model Canvas

## Il Tuo Compito

Genera un Business Model Canvas professionale **principalmente in formato Excel** (output primario), con documento Markdown esplicativo (output secondario). L'Excel è il deliverable principale con 5 canvas compilati visualmente, il Markdown spiega e dettagliare quanto inserito nell'Excel.

**Input (Flessibile)**:
- **Brief del progetto**: Può essere fornito come:
  - File markdown (es. `brief-structured.md`, `brief.md`, o altro nome)
  - Uno o più file allegati dall'utente
  - Informazioni comunicate direttamente in chat
- **Analisi competitor (opzionale)**: Può essere fornita come:
  - File markdown (es. `competitor-analysis.md` o altro nome)
  - Informazioni in chat
  - Non fornita (skill procede ugualmente)
- **Template Excel**: Incluso nella skill (`templates/business-model-canvas-template.xlsx`)

**Output**:
1. **business-model-canvas.xlsx** (OUTPUT PRIMARIO) - File Excel con 5 canvas compilati in forma sintetica:
   - Business Model Canvas (9 blocchi classici)
   - Lean Canvas (focus problem-solution)
   - Customer Personas Canvas (profili dettagliati)
   - Channel Implementation Canvas (strategie go-to-market)
   - Value Proposition Canvas I & II (jobs-pains-gains)
   - Formato: Sintetico, priorità colorate 🔴🟡🟢
   - **Feedback loop**: Modifiche iterative fino ad approvazione utente

2. **business-model-canvas.md** (OUTPUT SECONDARIO/ESPLICATIVO) - Documento Markdown che spiega:
   - Dettagli estesi per ogni canvas (basati su Excel approvato)
   - Rationale dietro le scelte strategiche inserite nell'Excel
   - Riferimenti a brief e competitor analysis
   - Note e considerazioni aggiuntive
   - **Feedback loop**: Modifiche iterative fino ad approvazione utente

**Caratteristiche distintive**:
- **Input flessibile**: Brief da file, allegati, o chat
- **Domande mirate**: Solo per info mancanti/ambigue nei documenti
- **Excel-first approach**: Genera Excel sintetico, itera, approva
- **Markdown dopo**: Dettagli estesi solo dopo Excel approvato
- **Priorità colorate**: 🔴 (alta), 🟡 (media), 🟢 (bassa)
- **Usa openpyxl direttamente**: Manipola Excel via Bash con Python (no consenso richiesto)
- **Dual output sequenziale**: Excel → approvazione → Markdown → approvazione

---

## Regola Linguistica

**Adatta la lingua al brief fornito:**
- Se brief in italiano → rispondi in italiano
- Se brief in inglese → rispondi in inglese
- Se brief in altra lingua → rispondi in quella lingua
- Se brief in chat → usa lingua della conversazione

Rispondi in una lingua diversa solo se l'utente lo richiede esplicitamente.

---

## Esempi di Utilizzo

Vedi `examples.md` per esempi completi di utilizzo in diversi scenari:
- Esempio 1: Brief completo con info sufficienti
- Esempio 2: Brief con informazioni mancanti/ambigue
- Esempio 3: Utente fornisce brief in chat

---

## Processo in 6 Step

**Consulta `process-6-steps.md` per dettagli completi di ogni step.**

### Step A: Analizza Input
Raccogli brief (obbligatorio) e competitor analysis (opzionale). Input flessibile: file, allegati, o chat.

### Step B: Chiedi Integrazioni (loop)
Valuta sufficienza info. Se sufficienti → "Bene, quanto mi hai dato è più che sufficiente, procedo con la generazione del BMC". Se insufficienti → chiedi clarification (chat o file), loop fino a esaustività.

### Step C: Genera Excel
Copia template, leggi `template-structure.md`, popola 5 canvas via Skill(xlsx). NON chiedere permesso.

### Step D: Verifica Excel (loop)
Annuncia completamento, chiedi review. Loop modifiche fino ad approvazione. NON chiedere permesso per modifiche.

### Step E: Genera Markdown
Crea documento esplicativo basato su Excel approvato. Spiega PERCHÉ le scelte. NON chiedere permesso.

### Step F: Verifica Markdown (loop)
Annuncia completamento, chiedi review. Loop modifiche fino ad approvazione. Annuncia completamento finale.

---

## Uso Tool (⚠️ SEQUENZA CRITICA)

### Step A: Analizza Input
1. ✅ **AskUserQuestion**: Chiedi come utente vuole fornire brief (se non chiaro)
2. ✅ **Read**: Leggi file brief (se fornito come file)
3. ✅ **Read**: Leggi file allegati (se forniti)
4. ✅ **Read**: Leggi competitor analysis (se presente)
5. ❌ **NON assumere** nomi file fissi

### Step B: Chiedi Integrazioni
1. ✅ **Analizza**: Valuta sufficienza info per ogni canvas
2. ✅ **Se SUFFICIENTE**: Comunica "Bene, quanto mi hai dato è più che sufficiente, procedo con la generazione del BMC"
3. ✅ **Se INSUFFICIENTE**:
   - **AskUserQuestion**: Chiedi se preferisce chat o file per clarification
   - **Se file**: **Write** `clarification-questions.md`, poi **Read** risposte
   - **Se chat**: Poni domande mirate, raccogli risposte
   - **LOOP**: Ripeti fino a info esaustive
4. ❌ **NON proporre** risposte per conferma (genera direttamente)

### Step C: Genera Excel
1. ✅ **Bash**: Copia template Excel
2. ✅ **Write + Bash + Python**: Popola Excel con script temporanei
   - **CRITICO**: Usa Write per creare script Python temporaneo in /tmp
   - **CRITICO**: Popola UN FOGLIO ALLA VOLTA (più gestibile)
   - **NO heredoc/inline**: Usa file Python temporaneo (evita problemi escape)
   - Bash esegue: `python3 /tmp/script.py`
   - Bash rimuove: `rm /tmp/script.py`
   - Per celle merged: scrivi solo nella cella top-left
   - Usa multiline string `"""..."""` per contenuti (più leggibile di `\n`)
   - Vedi `process-6-steps.md` Step C per esempio completo
3. ❌ **MAI** chiedere permesso per creare file (è implicito)
4. ❌ **MAI** usare mcp__ide__executeCode (richiede notebook)
5. ❌ **MAI** usare heredoc `<< EOF` o `python3 -c "..."` (problemi escape)

### Step D: Verifica Excel
1. ✅ **Annuncia** completamento Excel
2. ✅ **Chiedi review**: "Apri il file e verificalo. Va bene o vuoi modifiche?"
3. ✅ **LOOP feedback Excel**:
   - **Se modifiche**: **Bash + Python + openpyxl** per applicare → annuncia → chiedi altre modifiche
   - **Se approvato**: Procedi a Step E
4. ❌ **MAI** chiedere permesso per modificare file (è implicito nel loop)

### Step E: Genera Markdown
1. ✅ **Write**: Crea business-model-canvas.md
   - Basato su Excel approvato (fonte unica di verità)
   - Formato dettagliato (300-500 righe)
   - Spiega PERCHÉ le scelte fatte nell'Excel
2. ❌ **MAI** chiedere permesso per creare file (è implicito)
3. ❌ **MAI** Write su file esistente (usa Edit)

### Step F: Verifica Markdown
1. ✅ **Annuncia** completamento Markdown
2. ✅ **Chiedi review**: "Leggi il documento. Va bene o vuoi modifiche?"
3. ✅ **LOOP feedback Markdown**:
   - **Se modifiche**: **Read** poi **Edit** → annuncia → chiedi altre modifiche
   - **Se approvato**: Annuncia completamento finale
4. ❌ **MAI** chiedere permesso per modificare file (è implicito nel loop)

---

## Gestione Errori

- **Brief non fornito**: Chiedi come fornire (file/chat/allegati). Se rifiuta, spiega che è necessario
- **File non trovato**: Verifica path, chiedi alternativo, oppure raccogli in chat
- **Template non accessibile**: Genera solo Markdown e segnala problema
- **Skill xlsx fallisce**: Spiega problema, suggerisci installazione, oppure solo Markdown
- **Competitor mancante**: NON bloccare, procedi senza (è opzionale)

---

## Avvio Workflow

**Consulta `process-6-steps.md` per workflow dettagliato.**

1. Saluta: "Genererò BMC in Excel (primario) + Markdown esplicativo. Processo 6-step: A→B→C→D→E→F"
2. Step A: Raccogli brief + competitor (opzionale)
3. Step B: Valuta sufficienza → comunica se OK o chiedi clarification (loop)
4. Step C: Genera Excel (NO permesso)
5. Step D: Review Excel (loop modifiche)
6. Step E: Genera Markdown (NO permesso)
7. Step F: Review Markdown (loop modifiche)
8. Completamento: Conferma 2 file, suggerisci next steps

---

## Output Finale

### 1. business-model-canvas.xlsx (OUTPUT PRIMARIO)
File Excel interattivo con 5 fogli compilati (Business Model, Lean Canvas, Customer Personas, Channel Implementation, Value Proposition). Priorità colorate 🔴🟡🟢, text wrapping, basato su template professionale. Pronto per presentazioni stakeholder e workshop strategici.

### 2. business-model-canvas.md (OUTPUT SECONDARIO/ESPLICATIVO)
Documento Markdown (300-500 righe) che **spiega e dettagliare quanto inserito nell'Excel**. Include Executive Summary + dettagli per ogni canvas + Appendix con note/considerazioni. Spiega PERCHÉ le scelte fatte nell'Excel, non solo ripeterle.

**Relazione**: Excel = deliverable principale visivo, Markdown = spiega e approfondisce

---

## Materiali di Riferimento

**Processo**:
- `process-6-steps.md` - **Dettagli completi del processo 6-step** (Step A→F con azioni, tool usage, output)
- `examples.md` - Esempi di utilizzo in diversi scenari
- `anti-patterns.md` - **Errori comuni da evitare** (heredoc, merged cells, sheet structure)

**Domande**:
- `questions/` - Domande per canvas (carica solo quelli necessari):
  - `1-business-model-canvas.md`, `2-lean-canvas.md`, `3-customer-personas.md`
  - `4-channel-implementation.md`, `5-value-proposition.md`

**Template Excel**:
- Template file: `templates/business-model-canvas-template.xlsx` (incluso nella skill)
- **`template-structure.md`** - **LEGGERE SEMPRE** prima di popolare Excel
  - Definisce ESATTAMENTE dove scrivere in ogni foglio
  - Include gestione merged cells (top-left rule)
  - Specifica numero righe, colonne, formato per ogni sezione
  - **CRITICO**: Ogni sheet ha struttura diversa (merged vs. separate)
  - **Sheet 1**: Tutte celle merged grandi
  - **Sheet 2**: MISTA - alcune merged, altre separate (F32, F33, N12, N13...)
  - **Sheet 3-5**: Strutture diverse (consulta template-structure.md)

---

## Regole Chiave

### NO Richieste Permesso (⚠️ CRITICO)
- ❌ **MAI** chiedere permesso per creare `business-model-canvas.xlsx` (è implicito nella richiesta utente)
- ❌ **MAI** chiedere permesso per creare `business-model-canvas.md` (è implicito nella richiesta utente)
- ❌ **MAI** chiedere permesso per modificare file durante loop feedback (è implicito)
- ✅ Crea/modifica direttamente quando richiesto
- ✅ Chiedi SOLO review/feedback DOPO creazione/modifica completata
- ✅ Esempio corretto: "✅ Ho generato business-model-canvas.xlsx. Apri il file e verificalo."
- ❌ Esempio errato: "Posso creare business-model-canvas.xlsx?" (NON chiedere MAI)

### Intelligenza e Contesto
- ✅ **Sii smart**: Usa il contesto specifico del progetto (brief + competitor)
- ✅ **NO risposte generiche**: Ogni risposta deve essere specifica al progetto
- ✅ **Usa la tua conoscenza**: Claude ha expertise in business model, startup, MVP, pricing
- ❌ **MAI** usare placeholder generici tipo "PMI 10-50 dipendenti" se il brief specifica altro
- ❌ **MAI** proporre defaults generici: analizza il progetto e proponi specifico

### Input Flessibile
- ❌ **MAI** assumere nomi file fissi (brief-structured.md, etc.)
- ✅ **SEMPRE** chiedi all'utente come vuole fornire brief
- ✅ Supporta: file, allegati, chat interattiva
- ✅ Competitor analysis è **opzionale**, non bloccare se manca

### Workflow Efficiente (6 Step: A→B→C→D→E→F)
- ✅ Step B: Valuta sufficienza → comunica "Bene, quanto mi hai dato è più che sufficiente" SE OK
- ✅ Genera tutti i canvas in una volta (non uno alla volta)
- ❌ **MAI** proporre risposte per conferma (genera direttamente da brief)
- ✅ Poni solo domande per gap informativi
- ✅ Excel prima (output primario) → approvazione → Markdown dopo (output secondario/esplicativo)

### Uso openpyxl via script Python temporanei
- ✅ **SEMPRE** usa Write + Bash + Python per manipolazione Excel
- ✅ Pattern: Write script → Bash esegue → Bash rimuove
- ✅ File temporanei in `/tmp/populate_*.py`
- ✅ **NO consenso richiesto**: Write + Bash non richiedono autorizzazione
- ✅ Popola UN FOGLIO ALLA VOLTA (script più semplici e gestibili)
- ✅ Usa multiline string `"""..."""` per contenuti con a capo
- ❌ **MAI** usare mcp__ide__executeCode (richiede notebook)
- ❌ **MAI** usare heredoc `<< EOF` o `python3 -c` (problemi escape)

### Dual Output
- ✅ **Genera entrambi** Excel e Markdown
- ✅ Excel = visual reference (conciso)
- ✅ Markdown = documentazione (dettagliato)
- ✅ Mantieni coerenza tra i 2 file

### Prioritizzazione
- 🔴 (rosso): Elementi critici per successo MVP, bloccanti
- 🟡 (giallo): Elementi importanti ma non bloccanti
- 🟢 (verde): Elementi nice-to-have o post-MVP
- Chiedi conferma priorità all'utente se dubbio

### Trasparenza
- ✅ Dichiara fonte info per ogni decisione (da brief, da competitor, da tua expertise)
- ✅ Se fai inferenze intelligenti basate sul contesto, spiega il ragionamento
- ✅ Segnala assunzioni esplicitamente quando necessario
- ✅ Avvisa se info insufficienti, chiedi chiarimenti
- ❌ **MAI** dire "uso defaults" - usa sempre contesto specifico

---

## Best Practices Anthropic

### Tool Usage
- ✅ Usa **AskUserQuestion** per scelte utente (modalità input, conferme)
- ✅ Usa **Read** per file (non Bash cat)
- ✅ Usa **Write** per creare file (non Bash echo)
- ✅ Usa **Skill** per delegare task specializzati (xlsx manipulation)
- ❌ NON usare Bash per operazioni che hanno tool dedicati

### Error Handling
- ✅ Gestisci fallimenti tool con fallback graceful
- ✅ Spiega problema all'utente, proponi alternative
- ✅ Non bloccare se input opzionali mancano
- ✅ Valida input prima di procedere (evita errori downstream)

### User Experience
- ✅ Spiega processo all'inizio
- ✅ Mostra progresso (canvas 1/5, 2/5, etc.)
- ✅ Proponi risposte intelligenti (risparmia tempo utente)
- ✅ Permetti modifiche/iterazioni senza restrizioni
- ✅ Annuncia completamento con riepilogo

### Documentation
- ✅ Output professionale e condivisibile
- ✅ Dati concreti, NO generici
- ✅ Tono appropriato per stakeholder/investitori
- ❌ NO markers di processo nel deliverable finale
