# Fase 2: Ristrutturazione Brief

## Obiettivo

Creare **brief-structured.md** come documento **completo, autosufficiente e definitivo** che:
- **SOSTITUISCE brief.md** - Brief.md diventa obsoleto dopo questa fase e non sarà più consultato
- **Contiene TUTTE le informazioni** dal brief originale più tutto ciò dedotto e fornito dall'utente
- È **completo e leggibile autonomamente** senza bisogno di consultare altri documenti
- È **condivisibile con stakeholder** con formattazione professionale
- È **privo di riferimenti al processo** di creazione
- È **non ridondante** - Ogni informazione compare una volta nel posto più appropriato

---

## Overview del Processo

**Fase 2 in 9 passi**:
1. **Passo 1** - Leggere brief.md aggiornato (estrarre TUTTE le informazioni e risposte)
2. **Passo 2** - Creare brief-structured.md (documento stand-alone, struttura flessibile fino a 12 sezioni)
3. **Passo 2.5** - Review anti-ridondanza (verificare completezza e eliminare ripetizioni)
4. **Passo 3** - Tracciare modifiche internamente (per output chat, non nel file)
5. **Passo 4** - Output riepilogo all'utente in chat
6. **Passo 5** - Chiedere conferma con AskUserQuestion
7. **Passo 6** - Gestire modifiche richieste (se necessarie)
8. **Passo 7** - Loop fino ad approvazione (iterare Passo 5-6)
9. **Passo 8** - Annunciare pronto per Fase 3

---

## Quando Usare Questa Fase

- brief.md è sufficientemente chiaro (Fase 1 completata o saltata)
- L'utente ha risposto alle domande poste in Fase 1
- L'utente ha esplicitamente richiesto di passare a Fase 2

---

## Tools da Usare

1. **Read** tool → leggere brief.md aggiornato
2. **Write** tool → creare brief-structured.md (prima volta)
3. **Edit** tool → modificare brief-structured.md (iterazioni successive)
4. **AskUserQuestion** tool → conferme e richiesta modifiche

---

## Processo Dettagliato

### Passo 1: Leggere brief.md Aggiornato

Usa **Read tool** per leggere il file brief.md con le risposte dell'utente alle domande di Fase 1.

Estrai:
- Informazioni esplicite fornite dall'utente
- Risposte alle domande poste in Fase 1
- Nuovi dettagli aggiunti dall'utente

---

### Passo 2: Creare brief-structured.md

Usa **Write tool** per creare brief-structured.md come **documento stand-alone completo**.

#### REGOLE CRITICHE (⚠️ MOLTO IMPORTANTE)

**✅ FARE**:
- Scrivere come documento completo e leggibile autonomamente
- Integrare risposte e assunzioni in modo seamless
- Usare paragrafi narrativi con tono professionale
- Rendere il documento condivisibile con stakeholder
- Scrivere come se fosse il primo e unico documento del progetto

**❌ NON FARE**:
- ❌ NO markers tipo [CONFERMATO], [AGGIUNTO], [MODIFICATO], [ASSUNTO]
- ❌ NO riferimenti a "Q[N]", "risposta alla domanda N", "come da Q3"
- ❌ NO riferimenti a "defaults.md", "template.md", o altri file tecnici
- ❌ NO linguaggio tipo "Basato su brief.md", "Come indicato in brief.md"
- ❌ NO riferimenti al processo di creazione del documento
- ❌ NO linguaggio "diff-like" che mostra cosa è cambiato

#### Struttura brief-structured.md (fino a 12 sezioni)

**Vedi template completo**: `templates/brief-structured-template.md`

⚠️ **IMPORTANTE**: Il documento è **flessibile**. Non tutte le sezioni devono essere presenti - includi solo quelle:
- Presenti nel brief.md originale
- Pertinenti e importanti per il progetto specifico

**Sezioni possibili** (vedi template per dettagli su quali sono obbligatorie/opzionali):
1. Problema - Descrizione completa e impatto [SEMPRE]
2. Utenti e Contesto - Primari, secondari, contesto operativo [SEMPRE]
3. Obiettivi - Primario, secondari, criteri successo [SEMPRE]
4. Vincoli - Tecnici, organizzativi, business [SE PRESENTI NEL BRIEF]
5. Assunzioni - Con rationale per ognuna [SE NECESSARIE]
6. Funzionalità Primarie - Must-have per MVP (2-5 funzionalità) [SEMPRE]
7. Funzionalità Secondarie - Nice-to-have (TUTTE quelle citate nel brief) [SE PRESENTI NEL BRIEF]
8. Workflow Principali - 2-4 workflow documentati [SE DESCRITTI NEL BRIEF]
9. Workflow Secondari - Nice-to-have (TUTTI quelli citati nel brief) [SE PRESENTI NEL BRIEF]
10. Criticità e Rischi - Fattibilità, time-to-market, costi, dipendenze, adozione [SE RILEVANTI]
11. Scope MVP - Incluso/Escluso/Fasi future [SEMPRE]
12. Domande Aperte - Decisioni posticipabili [SE PRESENTI]

---

### Passo 2.5: Review Anti-Ridondanza e Completezza

**Prima di procedere**, rivedi mentalmente il documento appena creato per verificare:

**Checklist Completezza**:
- [ ] TUTTE le informazioni dal brief.md originale sono presenti
- [ ] TUTTE le risposte alle domande di Fase 1 sono integrate
- [ ] TUTTE le funzionalità menzionate nel brief sono elencate (primarie o secondarie)
- [ ] TUTTI i workflow menzionati nel brief sono elencati (principali o secondari)
- [ ] Solo le sezioni pertinenti al progetto sono state incluse (no sezioni vuote o non rilevanti)
- [ ] Nessuna informazione rilevante è stata persa o dimenticata

**Checklist Anti-Ridondanza**:
- [ ] Ogni informazione compare UNA SOLA VOLTA nel posto più appropriato
- [ ] Nessuna sezione ripete informazioni già presenti in altre sezioni
- [ ] Workflow non ripetono informazioni già nelle funzionalità (sono complementari)
- [ ] Scope MVP non ripete lista funzionalità (referenzia sezioni 6-7 dove applicabile)
- [ ] Scope MVP non ripete lista workflow (referenzia sezioni 8-9 dove applicabile)

**Se trovi ridondanze o informazioni mancanti**: Usa Edit tool per correggere prima di procedere al Passo 3.

---

### Passo 3: Tracciare Modifiche Internamente

Mentre scrivi brief-structured.md, **traccia mentalmente** (per il tuo output in chat):

- **Confermato**: Cosa veniva dal brief originale (già chiaro)
- **Aggiunto**: Cosa viene dalle risposte dell'utente alle domande
- **Assunto dalla skill**: Scelte tecniche fatte usando defaults.md (es. piattaforma web, autenticazione email/password, scala MVP)

⚠️ **IMPORTANTE - Due tipi di assunzioni**:
1. **Assunzioni TECNICHE della skill** (da defaults.md): Vanno comunicate SOLO in chat, NON nel documento brief-structured.md
2. **Assunzioni DI PROGETTO concordate** (dall'utente): Vanno documentate nella sezione "Assunzioni" di brief-structured.md

**Esempi**:
- ❌ NON nel documento: "Web responsive", "Email/password auth", "50-100 utenti per MVP" → Queste vanno solo in chat
- ✅ Nel documento: "Processore costa <10€/unità", "Utenti impiegano ~10min per task", "API pubblica disponibile" → Queste sono assunzioni concordate

---

### Passo 4: Output all'Utente in Chat

Dopo aver creato brief-structured.md, comunica all'utente in chat (NON nel file):

```markdown
# Fase 2: Brief Strutturato Creato

Ho creato **brief-structured.md** - il secondo documento di progetto.

## Cosa contiene

- Problema e contesto utenti dettagliati
- [N] assunzioni esplicitate per MVP
- Scope chiaro (cosa è incluso / non incluso)
- [N] funzionalità core descritte
- [N] workflow principali documentati

## Principali integrazioni dalle tue risposte

- **[Aspetto 1]**: [Breve descrizione di cosa hai integrato dalla risposta utente]
- **[Aspetto 2]**: [Breve descrizione]
- **[Aspetto 3]**: [Breve descrizione]

## Scelte tecniche fatte per MVP (da defaults.md)

- **[Aspetto X]**: Assunto [cosa]. Rationale: [perché]
- **[Aspetto Y]**: Assunto [cosa]. Rationale: [perché]

[Nota: Qui vanno le SCELTE TECNICHE della skill (piattaforma, autenticazione, scala, etc.). Elenca solo le più significative, max 3-4]
[Queste NON vanno nel documento brief-structured.md, sono solo per trasparenza in chat]

## Prossimo passo

Per favore rivedi **brief-structured.md**.
È un documento stand-alone che può essere condiviso con stakeholder.

Ti chiedo conferma: il brief strutturato riflette correttamente il progetto?
```

---

### Passo 5: Chiedere Conferma con AskUserQuestion

Usa **AskUserQuestion** tool per chiedere:

```
Domanda: "Il brief strutturato riflette correttamente il progetto?"

Opzioni:
- "Sì, procedi con Fase 3"
- "Sì, ma voglio alcune modifiche prima"
- "No, ci sono errori da correggere"
```

---

### Passo 6: Gestire Modifiche Richieste

Se l'utente richiede modifiche:

1. **Ascolta le modifiche** richieste dall'utente
2. **Leggi brief-structured.md** con Read tool (sempre!)
3. **Usa Edit tool** per applicare le modifiche specifiche
4. **Comunica in chat** cosa hai modificato e perché
5. **Chiedi conferma di nuovo** con AskUserQuestion
6. **Ripeti** fino a quando l'utente approva

#### Esempio Output Dopo Modifica

```markdown
# Modifiche Applicate a brief-structured.md

Ho aggiornato il documento con le tue richieste:

## Cosa ho modificato

- **[Sezione X]**: [Cosa hai cambiato e perché]
- **[Sezione Y]**: [Cosa hai cambiato e perché]

## Cosa ho rimosso

- [Cosa hai rimosso e perché]

## Cosa ho aggiunto

- [Cosa hai aggiunto e perché]

Per favore rivedi di nuovo brief-structured.md.
```

---

### Passo 7: Loop Fino ad Approvazione

**Continua il ciclo** Passo 5-6 fino a quando:
- L'utente conferma che brief-structured.md è corretto
- L'utente chiede di procedere con Fase 3

⚠️ **NON procedere a Fase 3 senza approvazione esplicita dell'utente**

---

### Passo 8: Annunciare Pronto per Fase 3

Quando l'utente approva:

```markdown
# Brief Strutturato Approvato ✓

Ottimo! brief-structured.md è completo e approvato.

## Prossimo passo: Fase 3

Posso ora procedere con la **Fase 3** per creare il documento formale di requisiti (requirements.md).

Vuoi che proceda con Fase 3?
```

Aspetta conferma prima di iniziare Fase 3.

---

## Esempio di Formato Assunzioni NEL DOCUMENTO

⚠️ **IMPORTANTE**: Le assunzioni in brief-structured.md sono **assunzioni DI PROGETTO concordate**, NON scelte tecniche della skill.

Le assunzioni in brief-structured.md devono seguire questo formato:

```markdown
## 5. Assunzioni

Le seguenti assunzioni sono state concordate per definire l'MVP:

- **Costo processore**: Assumiamo che sia possibile trovare un processore adeguato a meno di 10€ per unità. Rationale: Budget hardware limitato a 50€/unità totali, processore è componente principale.

- **Tempo attività utente**: Assumiamo che gli utenti impieghino circa 10 minuti per completare l'attività principale. Rationale: Basato su osservazioni preliminari del workflow attuale manuale.

- **Disponibilità API**: Assumiamo che l'API pubblica del fornitore X fornisca i dati necessari senza costi aggiuntivi. Rationale: Documentazione API indica disponibilità gratuita fino a 10k chiamate/mese, ampiamente sufficiente per MVP.

- **Connettività rete**: Assumiamo che la sede abbia connessione WiFi stabile con banda minima 10 Mbps. Rationale: Sede attuale ha infrastruttura WiFi, da verificare banda effettiva prima del deployment.
```

**Caratteristiche delle assunzioni nel documento**:
- Riguardano fattibilità, costi, tempi, vincoli di PROGETTO
- Concordate o validate con l'utente
- Hanno impatto sul successo MVP
- Sono verificabili/misurabili

---

## Riferimento a defaults.md (Solo per Chat Output)

⚠️ **Usa `defaults.md` per SCELTE TECNICHE, comunica in CHAT, NON scrivere nel documento**

Consulta `defaults.md` per scelte tecniche pragmatiche su:

- **Architettura**: Single-tenant, web responsive, cloud managed
- **Scala**: Decine-centinaia utenti, single-digit concurrent, business hours
- **Sicurezza**: Standard (HTTPS, DB encryption), email/password auth
- **Integrations**: None in v1, email/CSV export
- **Platform**: Modern browsers, desktop-first, no native apps
- **Data**: Relational DB, cloud file storage, daily backups
- **Hardware** (se applicabile): Off-shelf components, WiFi, USB charging, 50-200 units

**Come usare defaults.md**:
1. Usa i defaults per prendere decisioni tecniche dove il brief non specifica
2. Comunica queste scelte nella sezione "Scelte tecniche fatte per MVP" nell'output chat (Passo 4)
3. **NON scriverle** nella sezione "Assunzioni" di brief-structured.md
4. La sezione "Assunzioni" del documento è solo per assunzioni di progetto concordate con l'utente

**Quando fare override dei defaults**: Vedi `defaults.md` sezione "When to Override"

---

## Checklist: Fase 2 Completata

Prima di considerare Fase 2 completa, verifica:

### Documento brief-structured.md Creato
- [ ] File brief-structured.md creato con Write tool
- [ ] Solo le sezioni pertinenti al progetto incluse (no sezioni vuote o non rilevanti)
- [ ] Sezioni sempre necessarie presenti (Problema, Utenti, Obiettivi, Funzionalità Primarie, Scope MVP)
- [ ] Documento stand-alone completo (leggibile senza altri file)
- [ ] Tono professionale narrativo (no markers, no riferimenti processo)
- [ ] Assunzioni documentate con rationale (se presenti)
- [ ] Scope MVP chiaramente definito (incluso/escluso)

### Qualità Contenuto
- [ ] Problema chiaramente descritto
- [ ] Utenti e contesto dettagliati
- [ ] 2-5 funzionalità primarie descritte
- [ ] Funzionalità secondarie elencate (se presenti nel brief)
- [ ] Workflow principali documentati (se descritti nel brief)
- [ ] Workflow secondari documentati (se presenti nel brief)
- [ ] Assunzioni di progetto concordate documentate (se presenti) - NON scelte tecniche da defaults.md
- [ ] Scope MVP realistico

### Processo Seguito
- [ ] brief.md letto con Read tool
- [ ] Informazioni da brief.md integrate
- [ ] Risposte utente (se Fase 1) integrate
- [ ] Assunzioni di progetto concordate documentate (se presenti nel brief/discussioni)
- [ ] Scelte tecniche da defaults.md comunicate in chat (NON nel documento)
- [ ] Output riepilogo fornito in chat (non nel file)
- [ ] AskUserQuestion usato per conferma
- [ ] Modifiche gestite con Edit tool (se richieste)
- [ ] Utente ha approvato esplicitamente

### Pronto per Fase 3
- [ ] brief-structured.md approvato dall'utente
- [ ] Annunciato pronto per Fase 3
- [ ] In attesa conferma utente per procedere

---

## Errori Comuni da Evitare

### ❌ Errore 1: Documento con Markers
**Sbagliato**:
```markdown
## 1. Problema
[CONFERMATO] Gli utenti devono tracciare spese.
[AGGIUNTO] Attualmente usano Excel manualmente.
```

**Corretto**:
```markdown
## 1. Problema
Gli utenti devono tracciare le spese aziendali in modo efficiente. Attualmente utilizzano Excel manualmente, processo che risulta inefficiente e soggetto a errori.
```

### ❌ Errore 2: Riferimenti al Processo
**Sbagliato**:
```markdown
## 5. Assunzioni
Come da Q3, assumiamo piattaforma web responsive.
Basato su defaults.md, autenticazione email/password.
```

**Corretto**:
```markdown
## 5. Assunzioni
- **Tempo elaborazione dati**: Assumiamo che l'elaborazione dei dati richieda meno di 5 secondi. Rationale: Necessario per garantire un'esperienza utente fluida durante l'upload.
- **Disponibilità connessione**: Assumiamo connettività internet stabile nelle sedi operative. Rationale: Sistema richiede sincronizzazione dati in tempo reale.
```

**Nota**: Le scelte tecniche (piattaforma, autenticazione, etc.) NON vanno nella sezione Assunzioni del documento. Vanno solo comunicate in chat.

### ❌ Errore 3: Troppo Tecnico
**Sbagliato**:
```markdown
## 4. Vincoli
Useremo React, Next.js, PostgreSQL, AWS Lambda, API Gateway...
```

**Corretto**:
```markdown
## 4. Vincoli
- Piattaforma web moderna
- Database relazionale per gestione dati strutturati
- Cloud hosting per scalabilità futura
```

### ❌ Errore 4: Scope Vago
**Sbagliato**:
```markdown
## 8. Scope MVP
Includiamo le funzionalità principali.
Altre funzionalità in futuro.
```

**Corretto**:
```markdown
## 8. Scope MVP

### Incluso in MVP v1
- Creazione e modifica spese manualmente
- Categorizzazione spese (max 10 categorie predefinite)
- Export report mensile in CSV

### Esplicitamente NON Incluso in v1
- Import automatico da carte di credito → v2 dopo validazione MVP
- App mobile nativa → Web responsive sufficiente per MVP
- Workflow approvazione multi-livello → v2 se richiesto da utenti
```

---

## Riepilogo Tool per Fase 2

1. **Read tool**: Leggere brief.md all'inizio
2. **Write tool**: Creare brief-structured.md (prima volta)
3. **Edit tool**: Modificare brief-structured.md (iterazioni)
4. **AskUserQuestion tool**: Conferma e richiesta modifiche
5. **Output diretto**: Comunicare summary in chat (non tool)

**NON usare**:
- ❌ Write su file esistente (usa Edit)
- ❌ Edit senza Read prima
- ❌ Procedere senza conferma utente
