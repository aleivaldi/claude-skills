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

**Azioni**:
1. **Prepara template**:
   - Copia template: `cp ~/.claude/skills/generating-business-model-canvas/templates/business-model-canvas-template.xlsx ./business-model-canvas.xlsx`
   - Template sempre disponibile (incluso nella skill)

2. **Leggi mappatura celle**:
   - **Read** `template-structure.md`
   - **CRITICO**: Contiene ESATTAMENTE dove scrivere in ogni foglio
   - Include: righe, colonne, gestione merged cells, numero item per sezione
   - **NON perdere tempo** a studiare il template Excel, usa questa mappatura

3. **Genera contenuto per tutti i 5 canvas**:
   - Analizza brief + competitor + risposte clarification
   - Per ogni canvas, estrai info e assegna priorità 🔴🟡🟢
   - Mantieni contenuto **sintetico** (Excel è visual reference)
   - Usa `questions/` come guida (leggi file canvas specifici solo se necessario)

4. **Popola Excel via Skill(xlsx)**:
   - **CRITICO**: Invoca `Skill(xlsx)` con prompt testuale, NON scrivere codice Python diretto
   - Usa la sintassi: `Skill(command: "xlsx")` seguito da prompt testuale che descrive cosa popolare
   - Nel prompt per skill xlsx:
     - Specifica file: `business-model-canvas.xlsx`
     - Specifica foglio: es. "Sheet 'Business Model Canvas'"
     - Usa mappatura celle da `template-structure.md` (es. "Scrivi in B12-B26 per Key Partners")
     - Fornisci contenuto completo già formattato con priorità 🔴🟡🟢
     - Chiedi text wrapping e alignment top
   - Ripeti per tutti i 5 fogli
   - Skill xlsx gestirà merged cells automaticamente

**Output**: business-model-canvas.xlsx creato con 5 canvas compilati

**Tool Usage**:
- ✅ **Bash**: Copia template Excel
- ✅ **Read**: Leggi `template-structure.md` per mappatura celle
- ✅ **Skill(xlsx)**: Invoca skill xlsx per popolare Excel

**Esempio corretto invocazione skill xlsx**:
```
Skill(command: "xlsx")

Prompt: "Popola il file business-model-canvas.xlsx, foglio 'Business Model Canvas':

1. Metadata:
   - J4: 'MyKaraoke'
   - N4: 'Alessandro'
   - U4: 'v1.0'

2. Key Partners (celle B12-B26, una riga per item):
   - B12: '🔴 Stripe - Gateway pagamenti'
   - B13: '🔴 Library Provider - Licensing brani'
   - B14: '🟡 SIAE - Diritti autore'
   [...]

3. Key Activities (celle F12-F26):
   - F12: '🔴 Gestione inventory brani'
   [...]

Abilita text wrapping e vertical alignment top per tutte le celle con contenuto."
```

- ❌ **MAI** chiedere permesso per creare file (è implicito)
- ❌ **MAI** codice Python diretto (usa skill xlsx)

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
  - **Se modifiche**: **Skill(xlsx)** per applicare → annuncia → chiedi altre modifiche
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
