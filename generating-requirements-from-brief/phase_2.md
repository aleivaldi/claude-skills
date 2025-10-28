# Fase 2: Ristrutturazione Brief

## Obiettivo

Creare **brief-structured.md** come documento stand-alone professionale che ristruttura e completa le informazioni in brief.md, aggiungendo assunzioni ragionevoli dove necessario.

Il documento risultante deve essere:
- Completo e leggibile autonomamente
- Condivisibile con stakeholder
- Privo di riferimenti al processo di creazione
- Scritto con tono professionale narrativo

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

#### Struttura brief-structured.md (9 sezioni)

```markdown
# [NOME PROGETTO] - Brief Strutturato

## 1. Problema

[Descrizione completa del problema che il progetto risolve]
[Chi è affetto da questo problema]
[Gravità e impatto del problema]
[Situazione attuale e pain points]

## 2. Utenti e Contesto

### Utenti Primari
[Tipo di utente, ruolo, competenze tecniche]
[Quanti utenti (ordine di grandezza)]
[Contesto d'uso (dove, quando, come)]

### Utenti Secondari (se applicabile)
[Altri stakeholder o utenti indiretti]

### Contesto Operativo
[Ambiente di lavoro degli utenti]
[Strumenti attuali utilizzati]
[Vincoli ambientali o organizzativi]

## 3. Obiettivi

### Obiettivo Primario
[Cosa si vuole ottenere con questo MVP/PoC]

### Obiettivi Secondari
- [Obiettivo 2]
- [Obiettivo 3]

### Criteri di Successo
[Come misuriamo se abbiamo raggiunto gli obiettivi]

## 4. Vincoli

### Vincoli Tecnici
[Tecnologie richieste o da evitare]
[Sistemi esistenti con cui integrarsi]
[Piattaforme target]

### Vincoli Organizzativi
[Team disponibile, competenze]
[Processi aziendali da rispettare]
[Stakeholder e approvazioni necessarie]

### Vincoli di Business
[Timeline e deadline]
[Budget disponibile]
[Priorità aziendali]

## 5. Assunzioni

Le seguenti assunzioni sono state fatte per definire l'MVP:

- **[Aspetto 1]**: [Assunzione fatta]. Rationale: [Perché questa assunzione è ragionevole per MVP]
- **[Aspetto 2]**: [Assunzione fatta]. Rationale: [Perché questa assunzione è ragionevole per MVP]
- **[Aspetto 3]**: [Assunzione fatta]. Rationale: [Perché questa assunzione è ragionevole per MVP]

[Nota: Usa defaults.md per scegliere assunzioni pragmatiche per MVP]

## 6. Funzionalità Principali

### Funzionalità 1: [Nome]
[Descrizione dettagliata della funzionalità]
[Come l'utente la usa]
[Perché è importante]

### Funzionalità 2: [Nome]
[Descrizione dettagliata della funzionalità]
[Come l'utente la usa]
[Perché è importante]

### Funzionalità 3: [Nome]
[Descrizione dettagliata della funzionalità]
[Come l'utente la usa]
[Perché è importante]

[Tipicamente 3-5 funzionalità core per MVP]

## 7. Workflow Principali

### Workflow 1: [Nome]
1. [Step 1]
2. [Step 2]
3. [Step 3]
4. [Risultato]

### Workflow 2: [Nome]
1. [Step 1]
2. [Step 2]
3. [Step 3]
4. [Risultato]

[Descrivere 2-4 workflow principali che coprono i casi d'uso più comuni]

## 8. Scope MVP

### Incluso in MVP v1
- [Funzionalità/capability inclusa]
- [Funzionalità/capability inclusa]
- [Funzionalità/capability inclusa]

### Esplicitamente NON Incluso in v1
- [Funzionalità esclusa] → [perché: future phase / workaround manuale accettabile / dipende da feedback v1]
- [Funzionalità esclusa] → [perché]
- [Funzionalità esclusa] → [perché]

### Fasi Future (dopo v1)
**v2 (basato su apprendimento v1)**:
- [Enhancement possibile]
- [Integrazione possibile]

**v3+**:
- [Nice-to-have dallo scoping originale]

## 9. Domande Aperte

[Lista di decisioni ancora da prendere o aspetti da validare]
[Solo se ci sono decisioni veramente posticipabili dopo MVP]
[Se non ce ne sono, scrivere: "Nessuna domanda aperta critica per MVP v1"]
```

---

### Passo 3: Tracciare Modifiche Internamente

Mentre scrivi brief-structured.md, **traccia mentalmente** (per il tuo output in chat):

- **Confermato**: Cosa veniva dal brief originale (già chiaro)
- **Aggiunto**: Cosa viene dalle risposte dell'utente alle domande
- **Assunto**: Cosa viene da defaults.md perché non specificato

⚠️ **IMPORTANTE**: Queste informazioni sono SOLO per il tuo output in chat all'utente. NON metterle nel file brief-structured.md.

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

## Assunzioni aggiunte per MVP

- **[Aspetto X]**: Assunto [cosa]. Rationale: [perché]
- **[Aspetto Y]**: Assunto [cosa]. Rationale: [perché]

[Nota: Elenca solo le assunzioni più significative, max 3-4]

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

## Esempio di Formato Assunzioni

Le assunzioni in brief-structured.md devono seguire questo formato:

```markdown
## 5. Assunzioni

Le seguenti assunzioni sono state fatte per definire l'MVP:

- **Autenticazione**: Sistema email/password standard. Rationale: Semplice da implementare, adeguato per 1-5 location pilota iniziali.

- **Piattaforma**: Web responsive (non app native). Rationale: Più veloce da sviluppare (50% tempo risparmiato), accessibile da tutti i dispositivi.

- **Integrazioni**: Nessuna integrazione esterna in v1. Export via email/CSV. Rationale: Focus su funzionalità core prima di integrare sistemi esterni.

- **Scala**: 50-100 utenti per MVP. Rationale: Sufficiente per validare prodotto con utenti reali prima di ottimizzare per migliaia.

- **Performance**: Tempo di risposta <2 secondi. Rationale: Standard web accettabile, non serve ottimizzazione prematura per MVP.
```

Usa `defaults.md` per trovare assunzioni pragmatiche appropriate.

---

## Riferimento a defaults.md

Quando aggiungi assunzioni, consulta `defaults.md` per:

- **Architettura**: Single-tenant, web responsive, cloud managed
- **Scala**: Decine-centinaia utenti, single-digit concurrent, business hours
- **Sicurezza**: Standard (HTTPS, DB encryption), email/password auth
- **Integrations**: None in v1, email/CSV export
- **Platform**: Modern browsers, desktop-first, no native apps
- **Data**: Relational DB, cloud file storage, daily backups
- **Hardware** (se applicabile): Off-shelf components, WiFi, USB charging, 50-200 units

**Quando fare override dei defaults**: Vedi `defaults.md` sezione "When to Override"

---

## Checklist: Fase 2 Completata

Prima di considerare Fase 2 completa, verifica:

### Documento brief-structured.md Creato
- [ ] File brief-structured.md creato con Write tool
- [ ] Tutte le 9 sezioni presenti
- [ ] Documento stand-alone completo (leggibile senza altri file)
- [ ] Tono professionale narrativo (no markers, no riferimenti processo)
- [ ] Assunzioni documentate con rationale
- [ ] Scope MVP chiaramente definito (incluso/escluso)

### Qualità Contenuto
- [ ] Problema chiaramente descritto
- [ ] Utenti e contesto dettagliati
- [ ] 3-5 funzionalità core descritte
- [ ] 2-4 workflow principali documentati
- [ ] Assunzioni ragionevoli basate su defaults.md
- [ ] Scope MVP realistico

### Processo Seguito
- [ ] brief.md letto con Read tool
- [ ] Informazioni da brief.md integrate
- [ ] Risposte utente (se Fase 1) integrate
- [ ] Assunzioni aggiunte dove necessario
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
- **Piattaforma**: Web responsive. Rationale: Accessibile da tutti i dispositivi, più veloce da sviluppare.
- **Autenticazione**: Email/password standard. Rationale: Semplice, adeguato per MVP.
```

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
