---
name: user-stories-generator
description: Genera user stories complete e tracciabili partendo da un project brief strutturato. Processo interattivo in 7 fasi che guida l'utente dall'analisi iniziale alla validazione finale, con conferme a ogni step. Produce documentazione in formato Markdown organizzata per area funzionale, ruoli e priorità. Supporta sia output singolo che multi-file per progetti complessi. Adatta automaticamente la lingua all'input ricevuto (italiano/inglese).
---

# User Stories Generator

## Il Tuo Compito

Trasformare project brief strutturati in user stories complete, tracciabili e condivisibili con clienti e partner per validazione. Guidare l'utente attraverso un processo interattivo a 7 fasi, chiedendo conferma a ogni step critico prima di procedere.

**Focus**: User stories dal punto di vista dell'utente finale (COSA vuole fare, PERCHÉ), NON specifiche tecniche o implementazione.

**Lingua**: Adatta automaticamente alla lingua del project brief - se italiano, tutto output in italiano; se inglese, tutto in inglese.

---

## Workflow: 7 Fasi Interattive con File Intermedi

Il processo è **sequenziale**, **interattivo** e **file-based**. A ogni fase critica genera file intermedi che l'utente può modificare direttamente prima di procedere.

### Overview Fasi e File Generati

1. **Analisi Iniziale** → Genera `user-stories-structure.md` (ruoli, aree, apps)
2. **Definizione Granularità** → Legge structure, chiede livello dettaglio
3. **Generazione Lista Stories** → Genera `user-stories-list.md` (SOLO titoli)
4. **Gestione Edge Cases** → Legge list, aggiorna con edge cases
5. **Espansione Stories Complete** → Genera `user-stories-draft.md` (complete)
6. **Validazione Finale** → Legge draft, mostra summary
7. **Generazione Output** → Genera file finale/i da draft confermato

**File intermedi permettono**:
- Modificare struttura prima di generare stories
- Aggiungere/rimuovere stories nella lista
- Commentare nel file per guidare espansione
- Iterare su draft prima di finalizzare

**Consulta `process-phases.md` per dettaglio completo di ogni fase.**

---

## Input Atteso

**File richiesto**: Project brief strutturato (generato da skill `generating-structured-brief`)

**Sezioni utili nel brief**:
- Problema e obiettivi
- Utenti target / Ruoli
- Funzionalità primarie e secondarie
- Workflow utente
- Applicazioni/frontend menzionati
- Scope MVP vs Nice-to-have

**Come ottenere il brief**:
1. Chiedi all'utente path del file brief
2. Se non specificato, cerca in directory corrente: `brief-structured.md` o `brief.md`
3. Se non trovato, chiedi conferma location

---

## Fase 1: Analisi Iniziale

**Obiettivo**: Estrarre ruoli, aree funzionali e applicazioni dal brief.

**Azioni**:
1. Leggi project brief con Read tool
2. Identifica ruoli, macro-aree funzionali, applicazioni/frontend
3. Genera `user-stories-structure.md` con Write tool
4. Comunica path file e ATTENDI conferma utente

**Output**: File `user-stories-structure.md` generato, utente conferma OK.

**Dettagli completi**: Vedi `process-phases.md` Fase 1.

---

## Fase 2: Definizione Granularità

**Obiettivo**: Leggere structure.md modificato e decidere livello dettaglio.

**Azioni**:
1. Leggi `user-stories-structure.md` con Read tool
2. Analizza modifiche utente
3. Spiega livelli con AskUserQuestion: Epic (5-10 stories) / Feature (15-40) / Task (40-100+)
4. Mostra stima basata su aree, raccomanda Feature level

**Output**: Livello granularità scelto, structure.md validato.

**Dettagli completi**: Vedi `process-phases.md` Fase 2.

---

## Fase 3: Generazione Lista Stories (Solo Titoli)

**Obiettivo**: Creare lista titoli con IDs (formato `US-[AREA]-[NUM]`).

**Nomenclatura**:
- AREA: 3-6 lettere uppercase (AUTH, PROFILE, PAYMENT)
- NUM: 3 cifre zero-padded (001, 002, 010)
- Sub-stories: US-XXX-001.1 per varianti
- Relazioni: [REQUIRES/EXTENDS/ALTERNATIVE TO]

**Azioni**:
1. Genera lista completa basata su structure.md e granularità
2. Genera `user-stories-list.md` con Write tool (titoli + IDs + priorità + relazioni)
3. Comunica path file, istruzioni modifica (può aggiungere/rimuovere, commentare inline)
4. ATTENDI conferma utente

**IMPORTANTE**: Con 100+ stories, editing diretto del file è essenziale.

**Output**: File `user-stories-list.md` generato, utente conferma OK.

**Dettagli completi**: Vedi `process-phases.md` Fase 3 per nomenclatura ed esempi.

---

## Fase 4: Gestione Edge Cases e Varianti

**Obiettivo**: Leggere list.md modificato e aggiungere edge cases.

**Azioni**:
1. Leggi `user-stories-list.md` con Read tool
2. Analizza modifiche utente
3. Identifica edge cases (validazioni, errori, casi limite)
4. Chiedi strategia con AskUserQuestion: AC vs Sub-stories vs Separate (raccomanda Mix)
5. Aggiorna `user-stories-list.md` con Edit tool
6. Comunica update e ATTENDI conferma utente

**Output**: File `user-stories-list.md` aggiornato con edge cases, confermato.

**Dettagli completi**: Vedi `process-phases.md` Fase 4.

---

## Fase 5: Espansione Stories Complete

**Obiettivo**: Espandere ogni story con descrizione, AC, priorità, relazioni.

**Formato**: "Come [ruolo], voglio [azione] per [beneficio]" + Acceptance Criteria ("Quando..., allora...") + Priorità (Must/Should/Nice) + Relazioni + Note.

**Azioni**:
1. Leggi `user-stories-list.md` con Read tool (versione finale con edge cases)
2. Espandi tutte stories considerando commenti utente
3. Genera `user-stories-draft.md` con Write tool (stories espanse + summary)
4. Comunica path file, istruzioni review
5. ATTENDI conferma utente

**IMPORTANTE**: Draft file permette review massiva ed editing diretto (essenziale con 100+ stories).

**Output**: File `user-stories-draft.md` generato, utente revisiona e conferma OK.

**Dettagli completi**: Vedi `process-phases.md` Fase 5 per formato e classificazione priorità.

---

## Fase 6: Validazione Finale

**Obiettivo**: Mostrare summary e raccogliere feedback finale.

**Azioni**:
1. Leggi `user-stories-draft.md` con Read tool
2. Calcola statistiche (totale, per priorità, per area, dipendenze critiche)
3. Mostra summary in chat (non file)
4. Chiedi feedback con AskUserQuestion: draft OK? glossario? single/multi-file?
5. Se modifiche: chiedi di modificare draft.md e re-confermare
6. Procedi a Fase 7 solo dopo conferma

**Output**: Draft validato, strategia output decisa.

**Dettagli completi**: Vedi `process-phases.md` Fase 6.

---

## Fase 7: Generazione Output

**Obiettivo**: Creare file Markdown finali da draft.md.

**Strategia**: Single-file (< 50 stories) vs Multi-file (> 50 stories o più app).

**Azioni**:
1. Leggi `user-stories-draft.md` con Read tool (versione finale confermata)
2. Popola template appropriato (`templates/user-stories-single.md` o overview + sezioni)
3. Aggiungi glossario se richiesto
4. Write file finali: `user-stories-[nome-progetto].md` (o overview + sezioni)
5. Comunica path file creati, summary, suggerimenti prossimi passi
6. Opzionalmente archivia file intermedi in `_intermediate/`

**Output**: File Markdown finali generati, skill completata.

**Dettagli completi**: Vedi `process-phases.md` Fase 7 per template e naming convention.

---

## Best Practices Stories

Stories devono essere SMART (Specific, Measurable, Achievable, Relevant, Time-bound).

**Focus**: Valore utente, non tecnologia. AC verificabili, stories indipendenti quando possibile.

**Consulta `defaults.md` per regole complete, cosa evitare, cosa fare, assunzioni e valori default.**

---

## Uso Tool (⚠️ CRITICO)

### Pattern Principale

**File-Based Workflow**:
- **Fase 1**: Read(brief) → Write(structure.md) → ATTENDI conferma
- **Fase 2**: Read(structure.md) → AskUserQuestion(granularità)
- **Fase 3**: Write(list.md) → ATTENDI conferma
- **Fase 4**: Read(list.md) → Edit(list.md con edge cases) → ATTENDI conferma
- **Fase 5**: Read(list.md) → Write(draft.md) → ATTENDI conferma
- **Fase 6**: Read(draft.md) → AskUserQuestion(strategia output)
- **Fase 7**: Read(draft.md) → Write(output finali)

### Regole Tool

- **Write**: File NUOVI (structure, list, draft, output finale)
- **Edit**: File ESISTENTI (solo list.md con edge cases)
- **Read**: SEMPRE prima di processare file intermedi (utente potrebbe averli modificati)
- **AskUserQuestion**: Decisioni critiche (granularità, edge cases, output strategy)

### Gestione Path Brief

**Se utente non specifica path**:
```
1. Glob("brief-structured.md") → cerca in directory corrente
2. Se non trovato: Glob("brief.md")
3. Se ancora non trovato: AskUserQuestion per path manuale
```

### Tool da NON usare

- ❌ **NO Bash** per leggere/scrivere file (usa Read/Write)
- ❌ **NO Edit** su file non esistenti (usa Write)
- ❌ **NO assunzioni** su preferenze utente (usa AskUserQuestion)

---

## Gestione Errori

### Brief non trovato
1. Cerca varianti nome (brief-structured.md, brief.md)
2. Se fallisce: Chiedi path con AskUserQuestion
3. Se path errato: Segnala e richiedi

### Brief ambiguo o incompleto
1. Identifica sezioni mancanti (ruoli, funzionalità)
2. Segnala lacune all'utente
3. Chiedi input aggiuntivo con AskUserQuestion
4. Procedi solo con informazioni sufficienti

### Modifiche richieste durante processo
**Con workflow file-based**:
1. Chiedi all'utente di modificare direttamente il file intermedio (structure, list, draft)
2. Aspetta conferma che ha finito modifiche
3. Leggi file aggiornato con Read
4. Procedi alla fase successiva

**Vantaggi**: Editing diretto più efficiente che patch incrementali via chat con 100+ stories.

### Write fallisce
1. Verifica directory esiste e permessi
2. Se directory non esiste: offri di crearla o proponi path alternativo
3. Se permessi insufficienti: suggerisci directory con write access
4. Riprova con path confermato

### Read di file intermedio fallisce
1. File potrebbe essere stato spostato o cancellato dall'utente
2. Chiedi path aggiornato
3. Se intenzionale (es: ripartire da Fase 1), conferma e ricomincia
4. Altrimenti segnala errore e suggerisci recovery

### File intermedio malformato dopo modifica utente
1. Segnala problema specifico (es: "ID duplicato US-AUTH-001")
2. Chiedi all'utente di fixare
3. Rileggi dopo fix
4. Se persistente, offri di rigenerare quella fase

---

## Output Finale

**Deliverable Principali**:
- 1+ file Markdown finali con user stories strutturate
- Organizzazione per area funzionale
- IDs tracciabili e univoci
- Priorità chiare
- Acceptance criteria verificabili
- Summary con statistiche

**Naming convention output finale**:
- `user-stories-[nome-progetto].md` (single file)
- `user-stories-[nome-progetto]-overview.md` + `user-stories-[app/area].md` (multi-file)

**File Intermedi Generati** (durante processo):
- `user-stories-structure.md` (Fase 1)
- `user-stories-list.md` (Fase 3-4)
- `user-stories-draft.md` (Fase 5-6)

**Gestione File Intermedi**:
- Mantieni in directory corrente durante processo
- Opzionalmente archivia in `_intermediate/` dopo completamento
- Utili per iterazioni future o modifiche incrementali

**Location**: Directory corrente, a meno che utente specifichi diversamente.

---

## Materiali di Riferimento

- **`process-phases.md`**: Dettaglio completo di ogni fase con esempi e edge cases
- **`templates/user-stories-single.md`**: Template per output single-file
- **`templates/user-stories-overview.md`**: Template per overview multi-file
- **`templates/user-stories-section.md`**: Template per sezioni multi-file
- **`examples/example-format.md`**: Esempio concreto di formato user stories
- **`defaults.md`**: Valori default e assunzioni pragmatiche

---

## Avvio Workflow

Quando l'utente invoca questa skill:

1. **Saluta** e spiega processo a 7 fasi
2. **Chiedi path** del project brief (o cerca automaticamente)
3. **Leggi brief** con Read
4. **Inizia Fase 1**: Analisi iniziale
5. **Procedi sequenzialmente** attraverso fasi 2-7
6. **Chiedi conferma** a ogni transizione di fase
7. **Genera output** finale

**Principio chiave**: INTERATTIVITÀ. L'utente deve guidare le scelte, tu faciliti il processo.
