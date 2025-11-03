---
name: generating-business-model-canvas
description: Genera Business Model Canvas professionale in Excel + Markdown. Input flessibile da file o chat. Workflow step-by-step con 5 canvas (Business Model, Lean, Customer Personas, Channel Implementation, Value Proposition). Usa skill xlsx per manipolazione Excel. Output doppio per visual reference e documentazione dettagliata.
---

# Generating Business Model Canvas

## Il Tuo Compito

Genera un Business Model Canvas professionale in **2 formati complementari**: Excel per visual reference e Markdown per documentazione dettagliata.

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

**Output (2 File)**:
1. **business-model-canvas.xlsx** - File Excel con 5 canvas compilati:
   - Business Model Canvas (9 blocchi classici)
   - Lean Canvas (focus problem-solution)
   - Customer Personas Canvas (profili dettagliati)
   - Channel Implementation Canvas (strategie go-to-market)
   - Value Proposition Canvas I & II (jobs-pains-gains)

2. **business-model-canvas.md** - Documento Markdown con:
   - Dettagli estesi per ogni canvas
   - Rationale dietro le scelte strategiche
   - Riferimenti a brief e competitor analysis
   - Note e considerazioni aggiuntive

**Caratteristiche distintive**:
- **Input flessibile**: Brief da file, allegati, o chat
- **Workflow step-by-step**: Un canvas alla volta per ridurre contesto
- **Risposte proposte**: AI suggerisce risposte basate su brief, utente personalizza
- **Priorità colorate**: 🔴 (alta), 🟡 (media), 🟢 (bassa)
- **Usa skill xlsx**: Delega manipolazione Excel alla skill specializzata
- **Dual output**: Excel visuale + Markdown documentazione

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

<example>
Context: Utente ha file brief-structured.md e vuole BMC
User: "Genera il Business Model Canvas per il progetto"
Assistant: Perfetto! Prima di iniziare, ho bisogno del brief del progetto.

Vedo che hai menzionato brief-structured.md. Posso leggerlo? O preferisci:
- Passarmi altri file con il brief
- Descrivere il progetto direttamente in chat

[Usa AskUserQuestion per confermare]

User: "Sì, leggi brief-structured.md"
Assistant: [Legge brief-structured.md con Read tool]

Ho analizzato il brief. Hai anche un'analisi competitor da includere? (opzionale, posso procedere senza)

User: "No, procedi senza"
Assistant: Perfetto! Procedo con generazione BMC.

Ti proporrò risposte per ogni canvas basandomi sul brief. Potrai confermare o modificare.

**Canvas 1/5: Business Model Canvas**
...
</example>

<example>
Context: Utente fornisce brief in chat senza file
User: "Voglio creare un BMC per una piattaforma SaaS di automazione workflow per PMI"
Assistant: Ottimo! Per creare un Business Model Canvas completo, ho bisogno di più informazioni sul progetto.

Preferisci:
1. Fornirmi un file con il brief del progetto
2. Rispondere a domande in chat per raccogliere le info necessarie
3. Allegare documenti con dettagli progetto

[Usa AskUserQuestion]

User: "Rispondo in chat"
Assistant: Perfetto! Ti farò domande per raccogliere le informazioni chiave.

**Domanda 1/8**: Problema principale
Quale problema specifico risolve la tua piattaforma per le PMI?
...
</example>

<example>
Context: Utente allega più file
User: [Allega project-overview.md, market-research.pdf, competitor-notes.md]
"Usa questi file per generare il BMC"
Assistant: Perfetto! Ho ricevuto 3 file. Li leggo per analizzare il progetto.

[Legge project-overview.md con Read tool]
[Legge competitor-notes.md con Read tool]
[Nota: PDF richiede conversione, chiede se prioritario]

Ho analizzato project-overview.md e competitor-notes.md. Procedo con la generazione del BMC basandomi su questi documenti.

**Canvas 1/5: Business Model Canvas**
...
</example>

---

## Processo Principale

### Fase 1: Raccolta Input (Flessibile)

**Step 1**: Identifica fonte brief
- Chiedi all'utente come vuole fornire il brief
- Opzioni: file esistente, allegati, chat interattiva
- Usa **AskUserQuestion** per confermare approccio

**Step 2**: Raccogli brief progetto
- **Se file**: Usa **Read** tool per leggere file indicato
- **Se allegati**: Leggi file allegati dall'utente
- **Se chat**: Poni domande essenziali per raccogliere info:
  1. Problema risolto
  2. Target customer
  3. Soluzione proposta
  4. Differenziatori chiave
  5. Revenue model iniziale
  6. Scope MVP
  7. Budget/risorse disponibili
  8. Timeline progetto

**Step 3**: Raccogli competitor analysis (opzionale)
- Chiedi se disponibile
- **Se sì**: Leggi file o raccogli info in chat
- **Se no**: Procedi senza, genera BMC basandoti solo su brief

**Step 4**: Prepara template Excel
- Template skill: `templates/business-model-canvas-template.xlsx` (incluso nella skill)
- Copia template in working directory come `business-model-canvas.xlsx`
- Template sempre disponibile, nessuna dipendenza esterna

### Fase 2: Generazione Canvas (Step-by-Step)

**Per ogni canvas (5 totali)**:

1. **Genera risposte proposte**:
   - Analizza brief + competitor (se presente)
   - Consulta `canvas-questions.md` per domande
   - Proponi 3-7 risposte per sezione canvas
   - Assegna priorità: 🔴 (alta), 🟡 (media), 🟢 (bassa)
   - Fornisci rationale per ogni proposta

2. **Presenta all'utente**:
   - Mostra canvas corrente (X/5)
   - Elenca domande e risposte proposte
   - Chiedi conferma o modifiche

3. **Raccogli feedback**:
   - Utente conferma, modifica, o aggiunge
   - Registra risposte finali validate

4. **Salva progresso**:
   - Memorizza risposte per canvas corrente
   - Pronto per canvas successivo

**Ordine canvas**:
1. Business Model Canvas (fondamentale)
2. Lean Canvas (startup focus)
3. Customer Personas (target deep dive)
4. Channel Implementation (go-to-market)
5. Value Proposition Canvas (value alignment)

### Fase 3: Generazione Output

**Step 1**: Genera Markdown (business-model-canvas.md)
- Usa **Write** tool per creare file
- Include tutti i 5 canvas con dettagli estesi
- Aggiungi rationale e riferimenti a brief
- Formato: 300-500 righe, bullet points + tabelle
- Sezioni:
  - Executive Summary
  - Canvas 1: Business Model Canvas (dettagliato)
  - Canvas 2: Lean Canvas (dettagliato)
  - Canvas 3: Customer Personas (dettagliato)
  - Canvas 4: Channel Implementation (dettagliato)
  - Canvas 5: Value Proposition Canvas (dettagliato)
  - Appendix: Note e Considerazioni

**Step 2**: Genera Excel (business-model-canvas.xlsx)
- Invoca **Skill(xlsx)** per manipolazione Excel
- All'interno della skill xlsx:
  - Carica template con `load_workbook`
  - Popola ogni foglio canvas con risposte validate
  - Aggiungi priorità colorate: 🔴 (alta), 🟡 (media), 🟢 (bassa)
  - Abilita text wrapping per celle
  - Salva file Excel finale
  - Recalcola formule se presenti

**Step 3**: Annuncia completamento
- Riepilogo canvas compilati
- Conferma 2 file generati (Excel + Markdown)
- Segnala se utente vuole iterare su qualche canvas

---

## Uso Tool (⚠️ SEQUENZA CRITICA)

### Raccolta Input
1. ✅ **AskUserQuestion**: Chiedi come utente vuole fornire brief
2. ✅ **Read**: Leggi file brief (se fornito come file)
3. ✅ **Read**: Leggi competitor analysis (se presente)
4. ❌ **NON assumere** nomi file fissi (brief-structured.md, competitor-analysis.md)

### Generazione Canvas
1. ✅ **Consulta** canvas-questions.md per domande
2. ✅ **Proponi** risposte basate su brief analizzato
3. ✅ **AskUserQuestion**: Chiedi conferma/modifiche per ogni canvas
4. ✅ **Memorizza** risposte validate per uso successivo

### Generazione Output
1. ✅ **Write**: Crea business-model-canvas.md (nuovo file)
2. ✅ **Bash**: Copia template Excel dalla skill a working directory:
   - Template path: `~/.claude/skills/generating-business-model-canvas/templates/business-model-canvas-template.xlsx`
   - Comando: `cp ~/.claude/skills/generating-business-model-canvas/templates/business-model-canvas-template.xlsx ./business-model-canvas.xlsx`
   - Template sempre disponibile (incluso nella skill)
3. ✅ **Skill(xlsx)**: Invoca skill xlsx per manipolazione Excel
4. ✅ All'interno skill xlsx:
   - Carica workbook con openpyxl
   - Popola canvas con dati strutturati
   - Aggiungi priorità colorate (🔴🟡🟢) all'inizio di ogni item
   - Abilita text wrapping per celle
   - Salva Excel
5. ❌ **MAI** scrivere codice Python diretto (usa skill xlsx)

### Iterazioni (se richieste)
1. ✅ **Read**: Leggi business-model-canvas.md per revisione
2. ✅ **Edit**: Applica modifiche a Markdown
3. ✅ **Skill(xlsx)**: Re-invoca per aggiornare Excel
4. ✅ **AskUserQuestion**: Chiedi conferma finale

---

## Gestione Errori

### Brief Non Fornito
- **Scenario**: Utente invoca skill senza fornire brief
- **Azione**: Chiedi come vuole fornire brief (file, chat, allegati)
- **Fallback**: Se rifiuta, spiega che brief è necessario per generazione BMC

### File Brief Non Trovato
- **Scenario**: Utente indica file che non esiste
- **Azione**: Verifica path, chiedi path alternativo
- **Fallback**: Offri di raccogliere info in chat

### Template Excel Non Accessibile
- **Scenario**: Template skill non accessibile (molto raro)
- **Azione**: Verifica path skill, controlla permessi
- **Fallback**: Genera solo Markdown (senza Excel) e segnala problema

### Skill xlsx Non Disponibile
- **Scenario**: Skill xlsx fallisce o non installata
- **Azione**: Spiega problema, suggerisci installazione skill
- **Fallback**: Genera solo Markdown (senza Excel)

### Competitor Analysis Mancante (Opzionale)
- **Scenario**: Competitor analysis non fornito
- **Azione**: NON bloccare, procedi senza
- **Nota**: Avvisa che alcuni differenziatori potrebbero essere generici

---

## Avvio Workflow

Quando l'utente invoca questa skill:

1. **Saluta e spiega processo**:
   - "Genererò un Business Model Canvas in Excel + Markdown"
   - "Processo step-by-step, un canvas alla volta"
   - "Output: 2 file complementari"

2. **Raccogli brief** (input flessibile):
   - Chiedi come utente vuole fornire brief
   - Leggi file, allegati, o raccogli in chat
   - Valida che hai info sufficienti per procedere

3. **Raccogli competitor analysis** (opzionale):
   - Chiedi se disponibile
   - Se sì, leggi; se no, procedi senza

4. **Prepara template Excel**:
   - Template incluso nella skill (sempre disponibile)
   - Copia da `templates/` a working directory

5. **Esegui workflow canvas**:
   - Genera risposte per ogni canvas (1/5 → 5/5)
   - Raccogli feedback utente
   - Salva progresso dopo ogni canvas

6. **Genera output**:
   - Crea business-model-canvas.md
   - Crea business-model-canvas.xlsx (via skill xlsx)

7. **Annuncia completamento**:
   - Conferma 2 file generati
   - Offri iterazioni se necessario

---

## Output Finale

### 1. business-model-canvas.md (Documentazione Dettagliata)

Documento Markdown **completo** (300-500 righe) con:

**Executive Summary** (50-100 righe):
- Visione strategica del modello di business
- Key highlights da tutti i canvas
- Differenziatori principali vs competitor (se analisi disponibile)

**Canvas 1: Business Model Canvas** (60-80 righe):
- 9 blocchi dettagliati con bullet points
- Rationale per ogni scelta strategica
- Riferimenti a sezioni brief

**Canvas 2: Lean Canvas** (50-70 righe):
- Focus problem-solution fit
- Metriche chiave per validazione
- Unfair advantage e differenziatori

**Canvas 3: Customer Personas** (60-80 righe):
- 2-3 persona dettagliate
- Demographics, behaviors, goals, pains
- Buying process e decision criteria

**Canvas 4: Channel Implementation** (50-70 righe):
- Strategia per ogni canale
- Customer journey (awareness → retention)
- Budget allocation e CAC target

**Canvas 5: Value Proposition Canvas** (50-70 righe):
- Jobs-Pains-Gains (customer profile)
- Products-Pain relievers-Gain creators (value map)
- Fit analysis

**Appendix: Note e Considerazioni** (30-50 righe):
- Assunzioni chiave
- Rischi e mitigazioni
- Next steps suggeriti

**Caratteristiche**:
- ✅ Formato: Bullet points + tabelle markdown
- ✅ Tono professionale, condivisibile con stakeholder
- ✅ Dati concreti da brief, NO generici
- ✅ Riferimenti espliciti a brief/competitor
- ❌ NO markers di processo nel body

### 2. business-model-canvas.xlsx (Visual Reference)

File Excel **interattivo** con 5 fogli compilati:

**Foglio 1: Business Model Canvas**
- 9 blocchi posizionati secondo layout canonico
- Priorità colorate per ogni elemento
- Text wrapping abilitato

**Foglio 2: Lean Canvas**
- Layout startup-focused
- Problem-solution-metrics alignment
- Priorità colorate

**Foglio 3: Customer Personas Canvas**
- 2-3 persona visivamente separati
- Sezioni: demographics, behaviors, goals, pains, buying

**Foglio 4: Channel Implementation Canvas**
- Matrice canali × fasi customer journey
- Budget e CAC per canale
- Metriche chiave

**Foglio 5: Value Proposition Canvas I & II**
- Customer profile (jobs, pains, gains)
- Value map (products, relievers, creators)
- Visual fit mapping

**Caratteristiche**:
- 🔴🟡🟢 Priorità colorate: 🔴 (alta/critico), 🟡 (media/importante), 🟢 (bassa/nice-to-have)
- ✅ Text wrapping per leggibilità
- ✅ Basato su template professionale
- ✅ Pronto per presentazioni/pitch deck
- ❌ NO shape/post-it complessi (solo testo con priorità)

**Usi complementari**:
- **Excel**: Visual reference, presentazioni, workshop
- **Markdown**: Documentazione dettagliata, onboarding team, archivio strategico

---

## Materiali di Riferimento

**Guida Domande**:
- `canvas-questions.md` - Domande complete per ogni canvas con esempi di risposte

**Template**:
- Template Excel: `templates/business-model-canvas-template.xlsx` (incluso nella skill)
- Template risposte utente: `templates/bmc-answers-template.md`

**Supporto**:
- `defaults.md` - Default pragmatici per progetti MVP (pricing, cost structure, channels tipici)

---

## Regole Chiave

### Input Flessibile
- ❌ **MAI** assumere nomi file fissi (brief-structured.md, etc.)
- ✅ **SEMPRE** chiedi all'utente come vuole fornire brief
- ✅ Supporta: file, allegati, chat interattiva
- ✅ Competitor analysis è **opzionale**, non bloccare se manca

### Workflow Step-by-Step
- ✅ Un canvas alla volta (1/5 → 5/5)
- ✅ Proponi risposte, chiedi conferma/modifiche
- ✅ Salva progresso dopo ogni canvas
- ✅ Mostra rationale per risposte proposte

### Uso Skill xlsx
- ✅ **SEMPRE** usa Skill(xlsx) per manipolazione Excel
- ❌ **MAI** scrivere codice Python diretto in skill BMC
- ✅ Delega formattazione/popolamento a skill xlsx
- ✅ Skill xlsx ha expertise su openpyxl e Excel

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
- ✅ Dichiara fonte info per ogni proposta (da brief, da competitor, da defaults)
- ✅ Mostra quale canvas stai popolando (X/5)
- ✅ Segnala assunzioni esplicitamente
- ✅ Avvisa se info insufficienti, chiedi chiarimenti

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
