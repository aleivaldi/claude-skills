---
name: Generating Requirements from Brief
description: Trasforma appunti di progetto grezzi, brief informali o trascrizioni riunioni in documenti formali di requisiti MVP/PoC. Genera requirements.md con 8 sezioni includendo assunzioni, scope e metriche di successo. Supporta progetti software, hardware e misti.
---

# Generating Requirements from Brief

## Il Tuo Compito

Trasforma il brief di progetto dell'utente (solitamente in `brief.md`) in un documento formale di requisiti MVP/PoC attraverso un workflow iterativo basato su file.

Processo in **3 fasi**:

1. **Fase 1 (Analisi e Domande)**: Leggi brief.md, identifica carenze e poni domande all'utente spingendolo a modificare brief.md fino a quando sarà sufficientemente chiaro.
2. **Fase 2 (Ristrutturazione)**: Crea brief-structured.md riscrivendo in modo più formale e completo quanto indicato in brief.md
3. **Fase 3 (Generazione)**: Crea un documento formale requirements.md con 8 sezioni

---

## Regola Linguistica

**Adatta la lingua al file brief.md:**
- Se brief.md è in italiano → rispondi in italiano
- Se brief.md è in inglese → rispondi in inglese
- Se brief.md è in altra lingua → rispondi in quella lingua

Rispondi in una lingua diversa solo se l'utente lo richiede esplicitamente.

---

## Convenzione Nomi File

Durante il workflow, questi file vengono creati/modificati:

### 1. brief.md (utente crea e modifica)
- **Creato da**: Utente (input iniziale)
- **Modificato da**: Utente (in Fase 1 risponde a domande modificandolo)
- **Scopo**: Punto di partenza con un'idea. Possono essere appunti o trascrizioni di riunione
- **Ciclo di vita**: Modificato fino a quando tutte le domande hanno risposta

### 2. brief-structured.md (skill crea in Fase 2)
- **Creato da**: Skill (Fase 2)
- **Modificato da**: Skill basato su brief.md e assunzioni
- **Scopo**: Documento ordinato e completo che aggiunge dettagli a quanto indicato in brief.md
- **Ciclo di vita**: Modificato fino a quando l'utente non lo approva

### 3. requirements.md (skill crea in Fase 3)
- **Creato da**: Skill (Fase 3)
- **Modificato da**: Skill basato su feedback utente
- **Scopo**: Documento con specifiche, esaustivo e utilizzabile per analisi e progettazione future
- **Versioning**: v1.0, v2.0, etc. in document header
- **Ciclo di vita**: Deliverable finale, può essere iterato

---

## Fase 1: Analisi e Domande

### Quando Usarla
- L'utente chiede di iniziare
- L'utente fornisce un file brief.md
- L'utente modifica brief.md dopo domande precedenti

### Valutazione Rapida

Prima di generare domande, valuta se Fase 1 è necessaria:
- Problema chiaramente definito?
- Utenti e loro bisogni descritti?
- Vincoli (timeline, team, budget) menzionati?
- Scope MVP sufficientemente chiaro?

**Se SÌ a tutto**: Salta a Fase 2
**Se NO ad alcuni**: Continua con Fase 1 (0-8 domande mirate)

**Per processo dettagliato**: Vedi `phase_1.md`

---

## Fase 2: Ristrutturazione Brief

### Quando Usarla
- brief.md è sufficientemente chiaro (Fase 1 completata o saltata)
- L'utente ha risposto alle domande (se presenti)

### Obiettivo
Creare **brief-structured.md** come documento stand-alone professionale (9 sezioni) che ristruttura e completa le informazioni in brief.md, aggiungendo assunzioni ragionevoli dove necessario.

### Regola Critica
Il documento deve essere completo e leggibile autonomamente, NON un diff:
- ✅ Tono professionale narrativo, condivisibile con stakeholder
- ❌ NO markers tipo [CONFERMATO], [AGGIUNTO], [MODIFICATO]
- ❌ NO riferimenti a "Q[N]", "defaults.md", "brief.md"
- ❌ NO linguaggio che mostra il processo di creazione

**Per processo dettagliato**: Vedi `phase_2.md`

---

## Fase 3: Generazione Requirements

### Quando Usarla
- brief-structured.md è stato approvato dall'utente (Fase 2 completata)

### Obiettivo
Creare **requirements.md** come documento formale di requisiti MVP/PoC (8 sezioni principali) basato su brief-structured.md. Il documento deve essere utilizzabile per analisi e progettazione, condivisibile con team tecnico e stakeholder.

### Struttura requirements.md (8 sezioni)
1. Overview (Problema, Opportunità, Definizione di Successo)
2. Utenti e Contesto
3. Requisiti Core (Funzionali e Non-Funzionali, + Hardware se applicabile)
4. Scope (Incluso/Escluso/Fasi Future)
5. Vincoli (Risorse, Tecnici, Organizzativi)
6. Assunzioni e Domande Aperte
7. Metriche di Successo
8. Prossimi Passi (Azioni, Timeline, Rischi)

**Per processo dettagliato**: Vedi `phase_3.md`

---

## Materiali di Riferimento

**Processi Dettagliati**:
- `phase_1.md` - Analisi brief, algoritmo parsing, generazione domande (0-8), edge cases hardware/regulatory
- `phase_2.md` - Creazione brief-structured.md (9 sezioni), iterazioni, gestione approvazioni
- `phase_3.md` - Generazione requirements.md (8 sezioni), versioning, mappatura sezioni, deliverable

**Supporto**:
- `defaults.md` - Default pragmatici MVP (architettura, scala, sicurezza, performance, hardware IoT)
- `template.md` - Struttura requirements.md, linee guida sezioni, lunghezza documento, errori comuni

---

## Regole Chiave

### Processo Iterativo
- Fase 1: Analizza brief.md, poni domande (o salta se completo)
- Fase 2: Crea brief-structured.md stand-alone, loop fino ad approvazione
- Fase 3: Crea requirements.md, itera se necessario
- Traccia modifiche in chat, mantieni documenti puliti (no markers nel body)

### Uso Tool (⚠️ SEQUENZA CRITICA)
- ✅ **SEMPRE** Read prima di Edit/Write (previene errori dati obsoleti)
- ✅ Edit per file esistenti, Write per file nuovi
- ✅ AskUserQuestion per conferme
- ❌ **MAI** Write su file esistenti (usa Edit)
- ❌ **MAI** Edit senza Read prima
- ❌ **MAI** procedere senza conferma utente quando richiesta

### MVP Pragmatico
- Proponi default sensati (vedi `defaults.md`)
- Più semplice è meglio: off-shelf, web, no integrazioni inizialmente
- L'utente può sempre fare override

### Trasparenza
- Dichiara assunzioni con rationale
- Mostra ragionamento per i default
- Segnala conflitti esplicitamente

### Efficienza
- Fai 0-8 domande (solo quelle necessarie)
- Referenzia file, non ripetere
- Loop di feedback stretti

---

## Gestione Errori

### Fallimenti Tool

**Se Read fallisce**:
- Verifica percorso file corretto
- Chiedi utente: "Non trovo [file]. Esiste? Devo controllare un'altra posizione?"

**Se Edit fallisce** ("old_string not found"):
- Verifica old_string corrisponde esattamente (controlla spaziatura, line breaks)
- Se file cambiato da ultimo Read: Re-read file, riprova Edit
- Se ancora fallisce: Usa Write per ricreare (avvisa utente prima)

**Se Write fallisce** (permessi, directory):
- Verifica directory padre esiste
- Chiedi utente: "Non posso scrivere in [path]. Hai permessi? Devo usare posizione diversa?"

**Se AskUserQuestion non riceve risposta**:
- Attendi risposta utente
- Non procedere senza conferma quando richiesta

### Strategia di Recupero
1. **Sempre Read prima di Edit/Write** - Previene dati obsoleti
2. **Se incerto**: Chiedi utente, non indovinare
3. **Se bloccato**: Spiega cosa ti serve per procedere

---

## Avvio Workflow

Quando l'utente invoca questa skill, controlla brief.md:

1. **Se brief.md esiste**: Avvia Fase 1 automaticamente
2. **Se brief.md non esiste**: Chiedi all'utente di crearlo prima con appunti base di progetto
3. **Se l'utente fornisce testo in chat**: Chiedi se vuoi creare brief.md con quel contenuto

Conferma sempre da quale fase partire se non chiaro.
