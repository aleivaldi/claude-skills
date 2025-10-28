# Fase 1: Analisi Brief e Identificazione Gap

## Obiettivo

Valutare se la Fase 1 è necessaria. Se sì: estrarre informazioni chiare, identificare gap, adattarsi al livello tecnico dell'utente, proporre default pragmatici MVP, generare 0-8 domande di chiarimento (SOLO quelle necessarie), chiedere all'utente di aggiungere risposte direttamente in brief.md.

Se il brief è già sufficientemente dettagliato: saltare la Fase 1 e procedere direttamente alla Fase 2.

---

## Overview del Processo

**Fase 1 in 6 step**:
1. **STEP 0** - Valutare se Fase 1 è necessaria (può essere saltata se brief completo)
2. **STEP 1** - Estrarre informazioni e analizzare gap (10 categorie)
3. **STEP 3** - Identificare livello tecnico utente (non-tecnico, semi-tecnico, tecnico)
4. **STEP 4** - Formulare domande di chiarimento (0-8, formato suggestion-based)
5. **STEP 5** - Filtrare domande (chiedi solo ciò che serve)
6. **STEP 6** - Output domande in chat (non modificare brief.md)

---

## Algoritmo di Analisi

### STEP 0: Valutare se la Fase 1 è Necessaria

**Prima di generare domande**, valuta la completezza del brief:

Chiediti:
- Il problema è chiaramente definito?
- Gli utenti e i loro bisogni sono descritti?
- I vincoli (timeline, team, budget) sono menzionati o ragionevolmente deducibili?
- Lo scope MVP è sufficientemente chiaro per procedere?

**Decisione**:
- **Se SÌ a tutto**: Salta la Fase 1, procedi alla Fase 2
  - Output: "Il brief è sufficientemente dettagliato. Procedo con la Fase 2."
  - NON aggiungere domande
  - Vai direttamente alla Fase 2

- **Se NO ad alcuni**: Continua con STEP 1

---

### STEP 1: Estrazione Informazioni e Analisi Gap

**Obiettivo**: Analizzare brief.md ed estrarre tutte le informazioni rilevanti per il progetto, identificando per ciascuna categoria se le informazioni sono complete, incomplete, o non applicabili al contesto specifico.

**Istruzioni per l'Analisi**:

Per ciascuna delle seguenti categorie:
  1. Determina se la categoria è **rilevante** per questo tipo di progetto
  2. Se rilevante, estrai le informazioni disponibili dal brief
  3. Valuta lo stato delle informazioni secondo questi criteri:
     - ✅ **CHIARO**: Informazioni complete e sufficienti per procedere
     - 💡 **DEDUCIBILE**: Non menzionato, ma deducibile dal contesto o dalle conoscenze generali
     - ⚠️ **RICHIEDE CHIARIMENTI**: Menzionato ma incompleto o ambiguo
     - ❓ **NON MENZIONATO**: Non citato nel brief ma probabilmente rilevante per questo progetto
     - ⊗ **NON APPLICABILE**: Non rilevante per questo tipo di progetto

  ---

  ### 1. Definizione del Problema
  **Sempre Necessario**:
- [ ] problema che la soluzione vuole risolvere

  ### 2. Obiettivi del Progetto
  **Sempre Necessario**:
- [ ] risultati attesi
  **Solitamente Necessario**:
- [ ] modello di business
**Spesso Necessario**:
- [ ] come lo si vuole risolvere

  ### 3. Utenti Target
   **Sempre Necessario**:
   - [ ] Utenti primari identificati (ruolo/tipo, non nomi)
   **Solitamente Necessario**:
   - [ ] Utenti secondari, amministrativi o indiretti
   - [ ] numero di utenti

  ### 4. Funzionalità Core
   **Sempre Necessario**:
   - [ ] funzionalità core
   **Solitamente Necessario**:
   - [ ] workflow principali
   **Spesso Necessario**:
   - [ ] differenza fra must-have e nice-to-have

  ### 5. Vincoli Tecnici
   **Spesso Necessario** (non obbligatori per MVP):
   - [ ] tecnologie o stack specifici richiesti
   - [ ] linguaggi di programmazione preferiti
   - [ ] sistemi esistenti con cui integrare
   - [ ] cloud provider o infrastruttura preferita

  ### 6. Integrazioni Esterne
  **Spesso Necessario** (non obbligatorie per MVP v1):
   - [ ] API esterne da integrare
   - [ ] servizi di terze parti richiesti
   - [ ] sistemi legacy con cui comunicare

  ### 7. Requisiti Hardware
  Solo se dal brief si deduce che siano necessari prodotti fisici.
  **Sempre Necessario**:
   - [ ] funzionalità hardware
   **Solitamente Necessario**:
   - [ ] vincoli di dimensioni
   - [ ] costo massimo per unità
   **Spesso Necessario**:
   - [ ] certificazioni richieste

  ### 8. Vincoli di Sicurezza e Privacy
  **Sempre Necessario**:
   - [ ] presenza di dati sensibili da gestire
   **Solitamente Necessario**:
   - [ ] conformità GDPR
   **Spesso Necessario**:
   - [ ] conformità con altre regolamentazioni

  ### 9. Contesto e Timeline
   **Sempre Necessario**:
   - [ ] livello di urgenza
   **Solitamente Necessario**:
   - [ ] contesto aziendale
   - [ ] milestone principali
   **Spesso Necessario**:
   - [ ] deadline specifiche

  ### 10. Budget e Risorse
   **Spesso Necessario**:
   - [ ] budget del progetto disponibile

  ## Riepilogo Gap Identificati
  **Informazioni Critiche Mancanti**:
  1. [Lista prioritizzata dei gap che DEVONO essere colmati prima di procedere]
  **Informazioni Utili ma Non Bloccanti**:
  1. [Lista di informazioni che sarebbe utile avere ma su cui si possono fare assunzioni ragionevoli]
  **Categorie Non Applicabili**:
  - [Lista delle categorie non rilevanti per questo progetto specifico]

  ---


### STEP 3: Identificare il Livello Tecnico dell'Utente

Prima di generare domande, identifica il livello tecnico dal brief:

**Indicatori non-tecnici**:
- Nessun termine tecnico (es. API, database, cloud)
- Focus su problema di business e bisogni utente
- Descrive workflow in termini utente, non implementazione tecnica
- Esempio: "I clienti devono poter prenotare facilmente"

**Indicatori semi-tecnici**:
- Alcune menzioni tecniche ma non dettagliate
- Menziona "app" o "sito web" senza specifiche
- Mix di linguaggio business e tecnico
- Esempio: "Serve un'app web per gestire ordini"

**Indicatori tecnici**:
- Tecnologie specifiche menzionate (React, PostgreSQL, AWS)
- Preoccupazioni architetturali (microservizi, API, autenticazione)
- Vincoli o preferenze tecniche
- Esempio: "Vogliamo usare Next.js con autenticazione OAuth"

**Regola**: Adatta le tue domande al loro livello
- Non-tecnico → Chiedi SOLO domande di business
- Semi-tecnico → Mix business + tecnico ad alto livello
- Tecnico → Puoi fare domande tecniche

### STEP 4: Formulare Domande di Chiarimento 

Genera **0-8 domande** (SOLO quelle necessarie) usando il **formato basato su suggerimenti**:

**Template per le Domande**:
```
N. Che cosa intendi per [aspetto specifico]?
   Suggerimento: [approccio/default proposto]
   Perché: [perché è importante per i requisiti]
```

**Esempi di Qualità delle Domande**:

✓ Buona: "Che cosa intendi per 'accesso mobile'? Suggerimento: Web responsive. Perché: Più veloce da sviluppare."
✗ Cattiva (troppo tecnica): "Dovremmo usare GraphQL o REST?" → Meglio: "L'API deve supportare real-time?"
✗ Cattiva (vaga): "Come dovrebbe funzionare?" → Meglio: "Qual è il flusso principale per [azione]?"
✗ Cattiva (già risposta): "Quanti utenti?" quando il brief dice "50 utenti" → Salta
✗ Cattiva (implementazione): "Che database?" → Salta (il team dev decide)
✗ Cattiva (ovvia): "Volete HTTPS?" → Salta (sempre sì)

### STEP 5: Filtrare le Domande - Chiedi Solo Ciò Che Serve

**NON chiedere se**:
- ✗ L'informazione è già indicata in brief.md
- ✗ È un dettaglio di implementazione tecnica (scelta DB, framework, hosting)
- ✗ L'utente è non-tecnico e la domanda richiede conoscenze tecniche
- ✗ L'assunzione di default è sufficiente e a basso rischio per MVP
- ✗ La risposta non impatta significativamente lo scope MVP

**CHIEDI se**:
- ✓ L'informazione impatta significativamente scope o timeline MVP
- ✓ L'assunzione sarebbe ad alto rischio se sbagliata
- ✓ L'utente ha menzionato esplicitamente l'argomento ma senza chiarezza
- ✓ Necessario per risolvere conflitti o ambiguità nel brief
- ✓ Critico per stimare team/tempo/costi

**Risultato**:
- 0 domande = Il brief è completo e dettagliato
- 1-3 domande = Il brief necessita chiarimenti minori
- 4-6 domande = Il brief ha alcuni gap
- 7-8 domande = Il brief è molto vago (raro se filtri bene)

**Esempio di Filtro**:
Brief: "App web responsive per ordini. 50 ristoranti, 5-10 camerieri ciascuno."
✗ Salta: "Piattaforma?" (già: web responsive), "Quanti utenti?" (già: 250-500), "Database?" (dettaglio impl.)
✓ Chiedi: "Tablet propri o del ristorante?" (impatto UX), "Solo al tavolo o anche delivery?" (impatto scope)

### STEP 6: Aggiungere Domande nel Terminale

**IMPORTANTE**: Non modificare il file direttamente. Fai solo domande in chat.
Come suggerimenti scrivi frasi che possano essere copiate e incollate in brief.md

```markdown
## Domande da chiarire

1. Che cosa intendi per [specific aspect]?
   Suggerimento: [proposed approach/default]
   Perché: [impact on requirements]

2. Ho bisogno che mi indichi [specific aspect]?
   Suggerimento: [proposed approach/default]
   Perché: [impact on requirements]

[... continue for 0-8 questions]

---
**Istruzioni**: 
   1. Apri brief.md
   2. Modificalo per far si che vi sia risposta alle domande poste sopra.  Se il suggerimento è corretto puoi copiarlo direttamente, oppure puoi scrivere quello che ritieni corretto.
   4. Quando hai finito, dimmi di procedere con Phase 2
```

---

## Casi Limite - Riferimento Rapido

### Brief Completo (0 domande)
**Segnale**: Problema, utenti, vincoli, scope tutti chiaramente definiti
**Azione**: Output "Il brief è sufficientemente dettagliato. Procedo con la Fase 2." → Salta alla Fase 2

### Brief Molto Breve (4-6 domande base)
**Segnale**: "Serve app per tracciare spese" (senza dettagli)
**Azione**: Fai 4 domande base: chi usa, problema principale, timeline/team, preferenza piattaforma

### Stack Tecnico Menzionato (ignora, chiedi business)
**Segnale**: "Vogliamo React + GraphQL + microservizi..."
**Azione**: Chiedi di specificare le motivazioni per cui sono state richieste determinate tecnologie

### Scope Enorme (restringi)
**Segnale**: "Sistema finanziario completo con contabilità, fatturazione, tasse, multi-valuta..."
**Azione**: Verifica ed evidenzia eventuali incongruenze chiedendo all'utente di dettagliare come risolvere (sempre proponendo un default)

### Parole Chiave Regolamentari (domande compliance)
**Segnale**: "dati sanitari", "transazioni finanziarie", "utenti EU"
**Azione**: Fai 1-2 domande di compliance (GDPR? HIPAA? giurisdizione?)

### Progetto Hardware/IoT (domande dispositivo + software)
**Segnale**: "sensore IoT", "dispositivo", "hardware"
**Azione**: 3-5 domande specifiche hardware: tipo dispositivo, volume, connettività, alimentazione, fattore di forma
**Assunzioni**: Componenti off-shelf, WiFi, backend cloud, 50-200 unità MVP

---


## Rilevamento Conflitti

**Quando rilevi conflitti**, segnalali e aggiungi domanda di chiarimento:

Esempi:
- "50 utenti" + "1M transazioni/mese" → Verifica scala (20K tx/utente/mese?)
- "3 mesi" + "15 funzionalità" → Restringi a 4-5 funzionalità core MVP

**Azione**: Segnala in chat + aggiungi domanda con suggerimento pragmatico

---

## Checklist: Fase 1 Completata

### Se il Brief è Completo (0 domande):
- [ ] brief.md è stato letto con Read tool
- [ ] Valutato che problema, utenti, vincoli, scope sono chiari
- [ ] Output fornito: "Il brief è sufficientemente dettagliato. Procedo con la Fase 2."
- [ ] Procedi immediatamente alla Fase 2

### Se Servono Domande:
- [ ] brief.md è stato letto con Read tool
- [ ] Problema core estratto e dichiarato chiaramente
- [ ] Scope del progetto è chiaro
- [ ] Utenti primari identificati
- [ ] Funzionalità core e workflow identificati
- [ ] Livello tecnico dell'utente identificato
- [ ] 0-8 domande di chiarimento generate (SOLO quelle necessarie)
- [ ] Domande filtrate: nessuna domanda tecnica per utenti non-tecnici
- [ ] Domande filtrate: nessuna domanda su info già nel brief
- [ ] Domande poste all'utente con default/suggerimenti ragionevoli proposti per ciascuna
- [ ] Eventuali conflitti segnalati e messi in domanda
- [ ] Utente ha istruzioni chiare per rispondere in brief.md
- [ ] Output fornito in chat con riepilogo

**Poi attendi che l'utente risponda alle domande in brief.md prima della Fase 2.**

---

## Riepilogo Tool per Fase 1

1. **Read tool**: Leggere brief.md all'inizio
2. **Output**: Fornire risposta strutturata in chat (non usare tool per output chat)

**NON fare**:
- Usare Write o Edit tool
- Saltare il formato suggerimenti nelle domande
- Creare nuovi file nella Fase 1 (solo l'utente modifica brief.md)
