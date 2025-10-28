# Fase 3: Generazione Requirements

## Obiettivo

Creare **requirements.md** come documento formale di requisiti MVP/PoC con 8 sezioni, basato su brief-structured.md approvato. Il documento risultante deve essere:
- Formale e professionale
- Condivisibile con team tecnico e stakeholder
- Utilizzabile per analisi e progettazione future
- Con struttura chiara e navigabile

---

## Quando Usare Questa Fase

- brief-structured.md è stato approvato dall'utente (Fase 2 completata)
- L'utente ha esplicitamente richiesto di passare a Fase 3
- L'utente conferma che brief-structured.md riflette correttamente il progetto

---

## Tools da Usare

1. **Read** tool → leggere brief-structured.md
2. **Write** tool → creare requirements.md (prima volta)
3. **Edit** tool → modificare requirements.md (iterazioni successive)
4. **AskUserQuestion** tool → conferme opzionali

---

## Processo Dettagliato

### Step 1: Leggere brief-structured.md

Usa **Read tool** per leggere brief-structured.md approvato.

Estrai:
- Problema e contesto utenti
- Obiettivi e criteri di successo
- Funzionalità core e workflow
- Vincoli tecnici, organizzativi e di business
- Assunzioni documentate
- Scope MVP (incluso/escluso)
- Domande aperte

---

### Step 2: Creare requirements.md

Usa **Write tool** per creare requirements.md seguendo la struttura in 8 sezioni.

#### Struttura requirements.md (8 sezioni)

```markdown
# Requirements: [NOME PROGETTO]

**Fase**: MVP / PoC / Beta
**Versione**: 1.0
**Data Aggiornamento**: [Data]
**Status**: Draft

---

## 1. Overview

### Problema e Opportunità

[2-3 paragrafi: Quale problema risolve? Perché è importante?]
[Chi ne beneficia? Quale mercato/base utenti?]

### Definizione di Successo per Questa Fase

[Cosa significa "fatto e di valore" per MVP/PoC?]
[Specifico, misurabile se possibile]

---

## 2. Utenti e Contesto

### Utenti Primari

**Ruolo/Tipo**: [descrizione di chi usa questo]
**Numero**: [ordine di grandezza: 10, 100, 1000?]
**Competenze Tecniche**: [non tecnico, intermedie, avanzate?]
**Ambiente**: [desktop in ufficio, mobile in campo, entrambi?]

### Scenari d'Uso

**Workflow Principale**:
1. Utente [azione]
2. Sistema [risposta]
3. Utente [azione]
4. Sistema [risultato]

### Perché Ne Hanno Bisogno

[Quale problema risolve? Quanto tempo/sforzo risparmia?]

---

## 3. Requisiti Core

### Requisiti Funzionali (Cosa Deve Fare)

**Funzionalità 1: [Nome]**
- **Cosa**: [Descrizione chiara e semplice]
- **Perché**: [Quale problema risolve?]
- **Esperienza Utente**: [Come l'utente la sperimenta]

**Funzionalità 2: [Nome]**
- **Cosa**: [Descrizione chiara]
- **Perché**: [Quale problema risolve?]
- **Esperienza Utente**: [Come l'utente la sperimenta]

**Funzionalità 3: [Nome]**
[Stessa struttura]

[Tipicamente 3-5 funzionalità core per MVP]

### Requisiti Non-Funzionali (Come Si Comporta)

| Aspetto | Requisito | Perché |
|---------|-----------|--------|
| **Performance** | [es. Caricamento pagina <2 secondi] | [Perché: l'utente ha bisogno di reattività] |
| **Disponibilità** | [es. Orario lavorativo 9-18] | [Perché: adeguato per MVP] |
| **Scala** | [es. 50 agenzie, 5 utenti ciascuna] | [Perché: dimensione realistica MVP] |
| **Piattaforma** | [es. Web + mobile responsive] | [Perché: più veloce sul mercato] |
| **Dati** | [es. GDPR compliant, server EU] | [Perché: requisito legale] |
| **Integrazioni** | [es. Nessuna in v1, export email] | [Perché: focus su funzionalità core] |

---

## 3.1 Requisiti Hardware (Se Applicabile)

*Includere questa sezione solo se il progetto ha componenti hardware fisici.*

### Specifiche Dispositivo

**Tipo di Dispositivo**: [es. "Sensore IoT", "Wearable", "Dispositivo mobile", "Dispositivo industriale"]

**Fattore di Forma**: [Dimensioni, peso, materiali, note di design industriale]

**Alimentazione**: [Batteria, ricarica, consumo energetico, autonomia target]

**Connettività**: [WiFi, Bluetooth, cellular, cablato, capacità offline]

**Requisiti Ambientali**: [Temperatura operativa, umidità, durabilità, rating IP]

### Priorità Componenti (per MVP)

**Essenziali**:
- [Componente hardware core 1]
- [Componente hardware core 2]
- [Firmware/software per operarlo]

**Desiderabili**:
- [Componente o funzionalità di miglioramento]

**Future**:
- [Componenti avanzati o tipi di sensori]

### Punti di Integrazione

- **Software ↔ Hardware**: [Come l'app/firmware controlla il dispositivo?]
- **Integrazione Cloud**: [Il dispositivo invia dati al cloud? Ogni quanto?]
- **Interazione Utente**: [Come l'utente lo controlla? Pulsanti fisici, app, voce?]

### Produzione/Fornitura

- **Approvvigionamento**: [Dove si procurano i componenti? Tempi di consegna?]
- **Assemblaggio**: [Interno o in outsourcing?]
- **Target di Costo**: [Stima costo BOM, economia unitaria]
- **Volume Iniziale**: [Volume produzione MVP? 10 unità? 100? 1000?]

---

## 4. Scope

### Incluso in MVP v1

- [Funzionalità/capacità inclusa]
- [Funzionalità/capacità inclusa]
- [Funzionalità/capacità inclusa]

### Esplicitamente NON Incluso (v1)

- [Non avrà X] → fase futura
- [Non avrà Y] → workaround manuale accettabile
- [Non avrà Z] → dipende da feedback v1

### Fasi Future

**v2 (basato su apprendimento v1)**:
- [Miglioramento richiesto dagli utenti]
- [Integrazione voluta]

**v3+**:
- [Nice-to-have dallo scoping originale]

---

## 5. Vincoli

### Risorse

- **Team**: [es. "3 persone: 1 fullstack + 1 designer + 1 PM"]
- **Timeline**: [es. "3 mesi a beta"]
- **Budget**: [se rilevante: "budget ridotto, attenti ai costi"]

### Tecnici

- [Dipendenze esterne/must-have]
- [Requisiti di piattaforma]
- [Preferenze infrastrutturali]

### Organizzativi

- [Lacune competenze team?]
- [Approvazioni esterne necessarie?]

---

## 6. Assunzioni e Domande Aperte

### Assunzioni Chiave Fatte per MVP

Queste sono scommesse che stiamo facendo. Se qualcuna risultasse errata, ci adatteremo in v2.

| Assunzione | Se Sbagliata | Come Lo Sapremo |
|------------|--------------|-----------------|
| [Assunzione 1] | [Impatto se incorretta] | [Segnale/metrica da monitorare] |
| [Assunzione 2] | [Impatto se incorretta] | [Segnale/metrica da monitorare] |

### Da Validare Presto

Queste domande impattano la roadmap:

- [ ] [Domanda che influenza la direzione?]
- [ ] [Domanda che influenza la priorità?]

### Decisioni Aperte

- **[Argomento]**: [Cosa stiamo rimandando a v2 o dopo]
- **[Argomento]**: [Cosa stiamo rimandando]

---

## 7. Metriche di Successo

Come sappiamo che questo MVP ha funzionato:

| Metrica | Misurazione | Target |
|---------|-------------|--------|
| [Cosa] | [Come misuriamo] | [Numero target] |
| [Cosa] | [Come misuriamo] | [Numero target] |

---

## 8. Prossimi Passi

### Azioni Immediate

- [ ] Approvazione stakeholder di questo documento
- [ ] Condivisione con team design
- [ ] Condivisione con team dev
- [ ] [Altra azione]

### Timeline

| Quando | Cosa | Responsabile |
|--------|------|--------------|
| Settimana 1-2 | Lavoro Design/UX | [Responsabile] |
| Settimana 3-4 | Architettura tecnica | [Responsabile] |
| Settimana 5-X | Sviluppo | [Responsabile] |

### Rischi Noti e Mitigazione

| Rischio | Probabilità | Impatto | Mitigazione |
|---------|-------------|---------|-------------|
| [Rischio] | [B/M/A] | [scope/timeline/qualità] | [Come lo affrontiamo] |

---

## Appendice

### Glossario
[Se termini specifici del dominio, definirli qui]

### Storico Documento
| Versione | Data | Modifica |
|----------|------|----------|
| 1.0 | [Data] | Versione iniziale |

```

---

### Step 3: Mappare Sezioni da brief-structured.md a requirements.md

Mentre crei requirements.md, mappa le informazioni da brief-structured.md alle sezioni appropriate:

**Da brief-structured.md → A requirements.md**:

| Sezione brief-structured.md | → | Sezione requirements.md |
|------------------------------|---|-------------------------|
| 1. Problema | → | 1. Overview |
| 2. Utenti e Contesto | → | 2. Utenti e Contesto |
| 3. Obiettivi | → | 1. Overview (Success Definition) |
| 4. Vincoli | → | 5. Vincoli |
| 5. Assunzioni | → | 6. Assunzioni e Domande Aperte |
| 6. Funzionalità Principali | → | 3. Requisiti Core (Funzionali) |
| 7. Workflow Principali | → | 2. Utenti e Contesto (Scenari) |
| 8. Scope MVP | → | 4. Scope |
| 9. Domande Aperte | → | 6. Assunzioni e Domande Aperte |

**Aggiungi**:
- **Sezione 7**: Metriche di Successo (da creare basandoti su obiettivi)
- **Sezione 8**: Prossimi Passi (da creare con azioni concrete)
- **Sezione 3.1**: Requisiti Hardware (solo se applicabile)

---

### Step 4: Aggiungere Dettagli per Sezioni Nuove

Alcune sezioni richiedono sintesi o creazione:

#### Metriche di Successo (Sezione 7)

Basati su obiettivi in brief-structured.md e crea 3-5 metriche misurabili:

**Esempio**:
- Obiettivo: "Ridurre tempo di gestione ordini"
- Metrica: "Tempo medio gestione ordine" / "Cronometraggio dal placement alla conferma" / "<5 minuti (vs 15 attuali)"

#### Prossimi Passi (Sezione 8)

Crea azioni concrete basate su vincoli timeline e team:

**Esempio**:
- Timeline: "3 mesi a MVP"
- Azioni: "Settimana 1-2: Design UX", "Settimana 3-8: Sviluppo", "Settimana 9-12: Test e deploy"

---

### Step 5: Applicare Linee Guida di Scrittura

Mentre scrivi requirements.md, segui queste linee guida:

#### ✅ FARE:
- Usare linguaggio chiaro e professionale
- Essere specifici con numeri e target
- Usare tabelle per informazioni strutturate
- Spiegare il "perché" oltre al "cosa"
- Rendere il documento standalone (leggibile senza altri file)
- Usare voce attiva ("l'utente clicca" non "il pulsante viene cliccato")

#### ❌ NON FARE:
- ❌ Dettagli implementativi (React, PostgreSQL, AWS)
- ❌ Linguaggio vago ("il sistema dovrebbe essere veloce")
- ❌ Solo lista di funzionalità senza contesto
- ❌ Riferimenti a brief.md o brief-structured.md
- ❌ Markers tipo [CONFERMATO], [AGGIUNTO]

#### Livello Tecnico Corretto:

**Troppo tecnico** ❌:
```
Stack: React 18 + Next.js 14 + PostgreSQL 15 + AWS Lambda
```

**Livello giusto** ✅:
```
Piattaforma: Web moderna con database relazionale e hosting cloud
```

---

### Step 6: Output all'Utente in Chat

Dopo aver creato requirements.md, comunica all'utente in chat (NON nel file):

```markdown
# Fase 3: Documento Requirements Creato ✓

Ho creato **requirements.md** - il documento formale di requisiti per il progetto.

## Struttura Documento

- **8 sezioni** complete: Overview, Utenti, Requisiti, Scope, Vincoli, Assunzioni, Metriche, Prossimi Passi
- **[N] requisiti funzionali** dettagliati
- **[N] metriche di successo** definite
- **Scope chiaro** (cosa è incluso/escluso da v1)

## Informazioni Principali

- **Utenti**: [breve descrizione utenti primari]
- **Funzionalità core**: [lista 3-5 funzionalità]
- **Timeline**: [timeline indicativa]
- **Metriche**: [1-2 metriche chiave]

## Prossimo Passo

Il documento è pronto per:
- Condivisione con team design e sviluppo
- Approvazione stakeholder
- Inizio progettazione dettagliata

Se vuoi modifiche o integrazioni, dimmi quali sezioni aggiustare.
```

---

### Step 7: Gestire Iterazioni (Se Richieste)

Se l'utente richiede modifiche:

1. **Ascolta le modifiche** richieste
2. **Leggi requirements.md** con Read tool (sempre!)
3. **Usa Edit tool** per applicare modifiche specifiche
4. **Aggiorna versione** nel document header (1.0 → 1.1 per modifiche minori, 2.0 per modifiche maggiori)
5. **Aggiorna storico documento** in Appendice
6. **Comunica in chat** cosa hai modificato

#### Esempio Output Dopo Modifica

```markdown
# Modifiche Applicate a requirements.md

Ho aggiornato requirements.md alla **versione 1.1**.

## Cosa Ho Modificato

- **[Sezione X]**: [Descrizione modifica e rationale]
- **[Sezione Y]**: [Descrizione modifica e rationale]

## Storico Aggiornato

- v1.0: Versione iniziale
- v1.1: [Breve descrizione modifiche]

Il documento aggiornato è pronto per condivisione.
```

---

### Step 8: Versioning

Usa questo schema per versioning:

| Tipo Modifica | Esempio | Versione |
|---------------|---------|----------|
| Versione iniziale | Primo draft | 1.0 |
| Modifiche minori | Correzioni, piccole aggiunte | 1.1, 1.2, ... |
| Modifiche sostanziali | Nuove sezioni, scope cambiato | 2.0, 3.0, ... |

**Nel documento**: Aggiorna header e Appendice (Storico Documento)

```markdown
**Versione**: 2.0
**Data Aggiornamento**: [Nuova data]

---

### Storico Documento
| Versione | Data | Modifica |
|----------|------|----------|
| 1.0 | [Data1] | Versione iniziale |
| 2.0 | [Data2] | Aggiunto scope hardware, rivisti vincoli tecnici |
```

---

## Riferimento a Template

Quando crei requirements.md, consulta `templates/requirements-template.md` per:

- Template completo con tutte le sezioni
- Linee guida per lunghezza sezioni (Overview ~300 parole, Core Requirements ~1000 parole, etc.)
- Suggerimenti di scrittura
- Errori comuni da evitare
- Esempi di formato

---

## Riferimento a defaults.md

Se brief-structured.md non specifica alcuni aspetti, consulta `defaults.md` per assunzioni pragmatiche:

- Architettura: Single-tenant, web responsive, cloud managed
- Scala: Decine-centinaia utenti, single-digit concurrent
- Sicurezza: Standard (HTTPS, DB encryption)
- Performance: <2sec response time
- Integrazioni: Nessuna in v1, export email/CSV

**Documenta queste assunzioni** nella Sezione 6 (Assunzioni) con rationale.

---

## Checklist: Fase 3 Completata

Prima di considerare Fase 3 completa, verifica:

### Documento requirements.md Creato
- [ ] File requirements.md creato con Write tool
- [ ] Tutte le 8 sezioni presenti (+ 3.1 se hardware)
- [ ] Header con versione, data, status
- [ ] Documento standalone completo
- [ ] Appendice con glossario e storico

### Contenuto Completo
- [ ] Overview chiaro (problema, opportunità, successo)
- [ ] Utenti e scenari dettagliati
- [ ] 3-5 requisiti funzionali core documentati
- [ ] Requisiti non-funzionali in tabella
- [ ] Requisiti hardware (se applicabile)
- [ ] Scope chiaro (incluso/escluso/futuro)
- [ ] Vincoli documentati (risorse, tecnici, organizzativi)
- [ ] Assunzioni con if-wrong e segnali
- [ ] 3-5 metriche di successo misurabili
- [ ] Prossimi passi concreti (azioni, timeline, rischi)

### Qualità Documento
- [ ] Linguaggio professionale e chiaro
- [ ] Tabelle usate per dati strutturati
- [ ] Specifico (numeri, target, non vaghezza)
- [ ] Mostra "perché" oltre a "cosa"
- [ ] Livello tecnico appropriato (requisiti, non implementazione)
- [ ] NO riferimenti a brief.md o brief-structured.md
- [ ] NO markers [CONFERMATO], [AGGIUNTO]

### Processo Seguito
- [ ] brief-structured.md letto con Read tool
- [ ] Informazioni mappate correttamente alle sezioni
- [ ] templates/requirements-template.md consultato per struttura
- [ ] defaults.md consultato per assunzioni
- [ ] Output riepilogo fornito in chat
- [ ] Modifiche gestite con Edit + versioning (se richieste)

### Deliverable Finale
- [ ] Documento condivisibile con team e stakeholder
- [ ] Utilizzabile per analisi e progettazione
- [ ] Utente informato che documento è pronto

---

## Errori Comuni da Evitare

### ❌ Errore 1: Troppo Tecnico

**Sbagliato**:
```markdown
## 3. Requisiti Core
- Frontend: React 18 + TypeScript + Tailwind
- Backend: Node.js + Express + PostgreSQL 15
- Deploy: AWS Lambda + RDS + S3 + CloudFront
```

**Corretto**:
```markdown
## 3. Requisiti Core

### Requisiti Non-Funzionali

| Aspetto | Requisito | Perché |
|---------|-----------|--------|
| **Piattaforma** | Web moderna responsive | Accessibile da tutti i dispositivi |
| **Database** | Database relazionale | Dati strutturati, ACID compliance |
| **Hosting** | Cloud managed | Scalabilità, ridotto onere operativo |
```

### ❌ Errore 2: Metriche Vaghe

**Sbagliato**:
```markdown
## 7. Metriche di Successo
- Il sistema dovrebbe essere più veloce
- Gli utenti dovrebbero essere soddisfatti
```

**Corretto**:
```markdown
## 7. Metriche di Successo

| Metrica | Misurazione | Target |
|---------|-------------|--------|
| Tempo gestione ordine | Cronometro da placement a conferma | <5 minuti (vs 15 minuti attuali) |
| Soddisfazione utente | Survey NPS post-ordine | NPS ≥40 dopo 2 settimane uso |
```

### ❌ Errore 3: Scope Senza Confini

**Sbagliato**:
```markdown
## 4. Scope
In v1 facciamo le funzionalità principali.
Altre cose verranno aggiunte in futuro.
```

**Corretto**:
```markdown
## 4. Scope

### Incluso in MVP v1
- Creazione manuale ordini con 5 campi base
- Visualizzazione lista ordini ultimi 30 giorni
- Export report CSV giornaliero

### Esplicitamente NON Incluso (v1)
- Sincronizzazione con QuickBooks → v2 dopo validazione MVP
- App mobile nativa → Web responsive sufficiente per MVP
- Notifiche push real-time → Email sufficienti per v1

### Fasi Future
**v2**: Integrazione QuickBooks, notifiche push
**v3+**: Dashboard analytics avanzata, workflow approvazione multi-livello
```

### ❌ Errore 4: Riferimenti a Documenti Precedenti

**Sbagliato**:
```markdown
## 1. Overview
Come specificato in brief-structured.md sezione 1...
Basato su quanto discusso in Fase 2...
```

**Corretto**:
```markdown
## 1. Overview

### Problema e Opportunità

Gli agenti immobiliari devono gestire decine di proprietà e clienti quotidianamente. Attualmente utilizzano Excel e email, processo inefficiente che porta a errori e opportunità perse.
```

---

## Tools Summary per Fase 3

1. **Read tool**: Leggere brief-structured.md all'inizio
2. **Write tool**: Creare requirements.md (prima volta)
3. **Edit tool**: Modificare requirements.md (iterazioni + versioning)
4. **Output diretto**: Comunicare summary in chat (non tool)

**NON usare**:
- ❌ Write su file esistente (usa Edit)
- ❌ Edit senza Read prima
- ❌ AskUserQuestion per ogni modifica (solo se necessario)

---

## Lunghezza Documento

**Target lunghezza requirements.md**:

| Tipo Progetto | Parole | Pagine A4 |
|---------------|--------|-----------|
| Piccolo | 2000-2500 | 4-5 |
| Medio | 2500-3500 | 5-7 |
| Complesso | 3500-4500 | 7-9 |

Raramente più di 4500 parole per un documento MVP.

---

## Quando Fase 3 è Completa

Fase 3 è completa quando:

1. **requirements.md esiste** e contiene tutte le 8 sezioni (+ 3.1 se hardware)
2. **Documento è standalone** e condivisibile
3. **Utente è informato** che documento è pronto
4. **Eventuali modifiche** gestite con versioning

**NON è necessaria approvazione esplicita** per completare Fase 3, a meno che l'utente non richieda modifiche sostanziali.

---

## Comunicazione Finale

Quando Fase 3 è completa, comunica:

```markdown
# ✓ Documento Requirements Completato

Il documento **requirements.md** è pronto e contiene:

- Analisi completa problema e utenti
- [N] requisiti funzionali core
- [N] metriche di successo
- Scope chiaro e roadmap fasi
- Timeline e rischi identificati

## Il Documento È Pronto Per

- **Team Design**: Per iniziare UX/UI
- **Team Dev**: Per architettura tecnica
- **Stakeholder**: Per approvazione budget/timeline
- **Analisi**: Come base per progettazione dettagliata

Se serve qualche modifica o aggiunta, fammi sapere quale sezione modificare.
Altrimenti il workflow di generazione requisiti è completato! 🎉
```
