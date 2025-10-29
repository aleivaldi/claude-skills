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

Genera **0-8 domande** (SOLO quelle necessarie) usando **ESATTAMENTE** il **formato basato su suggerimenti**.

⚠️ **IMPORTANTE**: Il formato è OBBLIGATORIO. Deve essere seguito ALLA LETTERA. L'utente deve poter copiare il suggerimento direttamente.

**Template OBBLIGATORIO per le Domande**:
```
N. Che cosa intendi per [aspetto specifico]?
   Suggerimento: [approccio/default proposto - frase completa copiabile]
   Perché: [perché è importante per i requisiti]
```

**OGNI domanda DEVE avere tutte e 3 le parti**:
1. Domanda specifica (una sola domanda, non elenchi puntati)
2. Suggerimento (risposta completa copiabile, non solo keyword)
3. Perché (motivazione chiara e concisa)

---

**Esempi CORRETTI di Domande Ben Formattate**:

✅ **Esempio 1 - Accesso Mobile**:
```
1. Che cosa intendi per "accesso mobile"?
   Suggerimento: Applicazione web responsive accessibile da browser mobile (no app nativa).
   Perché: Più veloce da sviluppare per MVP, validabile con utenti reali prima di investire in app nativa.
```

✅ **Esempio 2 - Volume Utenti**:
```
2. Quanti locali karaoke prevedi di coinvolgere nel pilota MVP?
   Suggerimento: 3-5 locali per validare il sistema prima di scalare.
   Perché: Critico per dimensionare infrastruttura e stimare costi server.
```

✅ **Esempio 3 - Problema Principale**:
```
3. Qual è il problema principale che MyKaraoke risolve per i gestori di locali?
   Suggerimento: Eliminare gestione manuale delle code e prenotazioni brani, riducendo tempi morti e migliorando esperienza utente.
   Perché: Definisce il valore core del prodotto e guida priorità funzionalità.
```

✅ **Esempio 4 - Timeline**:
```
4. Entro quando deve essere pronto il sistema per il pilota?
   Suggerimento: 3-4 mesi per MVP funzionante in un locale test.
   Perché: Impatta team size, scope MVP, e scelte tecniche (build vs buy).
```

---

**Esempi SBAGLIATI - NON fare così**:

❌ **Errore 1 - Domanda con elenco puntato** (NON copiabile come suggerimento):
```
1. Problema e Valore (CRITICO per brief)
   Aggiungi una sezione all'inizio che risponda:
   - Qual è il problema principale che questo sistema risolve?
   - Perché dovrebbero usare MyKaraoke invece di gestire manualmente?
   - Qual è il valore principale offerto?
```
**Problema**: Più domande insieme, nessun suggerimento copiabile, formato sbagliato.

❌ **Errore 2 - Domanda troppo vaga**:
```
2. Come dovrebbe funzionare?
   Suggerimento: Bene
   Perché: Per sapere
```
**Problema**: Domanda vaga, suggerimento inutile, perché poco chiaro.

❌ **Errore 3 - Manca suggerimento**:
```
3. Quanti utenti?
```
**Problema**: Mancano suggerimento e perché.

❌ **Errore 4 - Domanda tecnica per utente non-tecnico**:
```
4. Dovremmo usare GraphQL o REST per le API?
   Suggerimento: GraphQL
   Perché: Più flessibile
```
**Problema**: Dettaglio implementativo, non rilevante per brief, utente non può rispondere.

❌ **Errore 5 - Suggerimento non copiabile** (solo keyword):
```
5. Che piattaforma?
   Suggerimento: Web
   Perché: Più veloce
```
**Problema**: Troppo sintetico, "Web" non è una risposta completa copiabile in brief.md.

---

**Come Correggere l'Errore 1** (esempio del karaoke):

❌ **Sbagliato**:
```
1. Problema e Valore (CRITICO per brief)
   Aggiungi una sezione che risponda:
   - Qual è il problema principale?
   - Perché usare MyKaraoke?
   - Qual è il valore?
```

✅ **Corretto** (3 domande separate):
```
1. Qual è il problema principale che MyKaraoke risolve per i gestori di locali?
   Suggerimento: Eliminare la gestione manuale delle code e prenotazioni brani, che crea tempi morti e frustrazioni per gli utenti.
   Perché: Definisce il valore core del prodotto e guida le priorità delle funzionalità.

2. Perché un gestore dovrebbe usare MyKaraoke invece di gestire le serate manualmente con carta o Excel?
   Suggerimento: Risparmio di tempo operativo (30-40 minuti/serata), riduzione errori, e maggior engagement degli utenti grazie a esperienza digitale moderna.
   Perché: Quantifica il valore e aiuta a definire metriche di successo MVP.

3. Qual è il valore principale offerto agli utenti finali (cantanti)?
   Suggerimento: Prenotare brani in anticipo da smartphone senza fare code, vedere quando sarà il proprio turno, e condividere performance sui social.
   Perché: Differenzia MyKaraoke da soluzioni esistenti e guida funzionalità primarie.
```

---

**Altri Esempi di Domande Mal Formattate**:

✗ Cattiva (troppo tecnica): "Dovremmo usare GraphQL o REST?" → Non rilevante per brief
✗ Cattiva (vaga): "Come dovrebbe funzionare?" → Troppo generica, non actionable
✗ Cattiva (già risposta): "Quanti utenti?" quando il brief dice "50 utenti" → Informazione già presente
✗ Cattiva (implementazione): "Che database?" → Dettaglio tecnico, non per brief
✗ Cattiva (ovvia): "Volete HTTPS?" → Sempre sì, non serve chiedere

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

### STEP 6: Output Domande in Chat

⚠️ **CRITICO**: Non modificare brief.md. Genera SOLO l'output in chat con domande nel formato ESATTO definito in STEP 4.

**Regole OBBLIGATORIE per l'Output**:
1. ✅ Usa **ESATTAMENTE** il template: Domanda + Suggerimento + Perché
2. ✅ Ogni domanda è **separata** (NO elenchi puntati dentro una domanda)
3. ✅ Suggerimenti sono **frasi complete copiabili**, non keyword
4. ✅ **UNA domanda = UNA cosa da chiarire** (no raggruppamenti tipo "Problema e Valore")
5. ❌ **MAI** usare sottopunti puntati dopo la domanda
6. ❌ **MAI** raggruppare più domande insieme
7. ❌ **MAI** omettere Suggerimento o Perché

**Template OUTPUT in Chat** (da seguire ALLA LETTERA):

```markdown
## Domande da chiarire

Per completare il brief, ho bisogno di alcune informazioni. Ho preparato suggerimenti per velocizzare le risposte - puoi copiarli direttamente se vanno bene.

1. [Domanda specifica su un aspetto]?
   Suggerimento: [Risposta completa copiabile come frase intera]
   Perché: [Motivazione chiara del perché serve questa info]

2. [Altra domanda specifica]?
   Suggerimento: [Altra risposta completa copiabile]
   Perché: [Motivazione chiara]

[... continua per 0-8 domande totali]

---
**Istruzioni per l'utente**:
1. Apri brief.md nel tuo editor
2. Per ogni domanda sopra, aggiungi la risposta nel brief
3. Puoi copiare il "Suggerimento" se è corretto, oppure scrivere la tua versione
4. Quando hai finito, dimmi "procedi con Fase 2"
```

---

**Esempio OUTPUT Corretto** (da seguire):

```markdown
## Domande da chiarire

Per completare il brief, ho bisogno di alcune informazioni. Ho preparato suggerimenti per velocizzare le risposte - puoi copiarli direttamente se vanno bene.

1. Qual è il problema principale che MyKaraoke risolve per i gestori di locali?
   Suggerimento: Eliminare la gestione manuale delle code e prenotazioni brani, che crea tempi morti e frustrazioni per gli utenti.
   Perché: Definisce il valore core del prodotto e guida le priorità delle funzionalità.

2. Quanti locali karaoke prevedi di coinvolgere nel pilota MVP?
   Suggerimento: 3-5 locali per validare il sistema prima di scalare.
   Perché: Critico per dimensionare infrastruttura e stimare costi server.

3. Entro quando deve essere pronto il sistema per il pilota?
   Suggerimento: 3-4 mesi per MVP funzionante in un locale test.
   Perché: Impatta team size, scope MVP, e scelte tecniche (build vs buy).

---
**Istruzioni**:
1. Apri brief.md nel tuo editor
2. Per ogni domanda sopra, aggiungi la risposta nel brief
3. Puoi copiare il "Suggerimento" se è corretto, oppure scrivere la tua versione
4. Quando hai finito, dimmi "procedi con Fase 2"
```

---

**Esempio OUTPUT SBAGLIATO** (NON fare così):

❌ **Sbagliato**:
```markdown
## Domande da chiarire

Per completare il brief, ho bisogno che tu modifichi il file brief.md aggiungendo le risposte a queste domande critiche:

1. Problema e Valore (CRITICO per brief)

   Aggiungi una sezione all'inizio che risponda:
   - Qual è il problema principale che questo sistema risolve per i gestori?
   - Perché dovrebbero usare MyKaraoke invece di gestire manualmente?
   - Qual è il valore principale offerto?

2. Timeline e Risorse

   Specifica:
   - Entro quando serve il sistema?
   - Quante persone nel team?
   - Budget disponibile?
```

**Problemi**:
- ❌ Domande raggruppate invece che separate
- ❌ Elenchi puntati al posto di domanda singola
- ❌ Nessun suggerimento copiabile
- ❌ Manca "Perché" per ogni domanda
- ❌ Formato non rispettato

---

**Checklist di Verifica Prima di Inviare Output**:

Prima di inviare le domande all'utente, verifica SEMPRE:
- [ ] Ogni domanda ha ESATTAMENTE 3 parti: Domanda, Suggerimento, Perché
- [ ] Nessuna domanda contiene elenchi puntati interni
- [ ] Ogni suggerimento è una frase completa copiabile (non solo keyword)
- [ ] Nessuna domanda raggruppa più aspetti insieme
- [ ] Il formato segue ESATTAMENTE il template (indentazione corretta)
- [ ] Numero totale domande: 0-8 (filtrate per rilevanza)
- [ ] Tutte le domande sono appropriate per il livello tecnico dell'utente

**Se anche UNA sola di queste checkbox non è spuntata**: CORREGGI prima di inviare.

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
- [ ] ⚠️ **FORMATO RISPETTATO**: Ogni domanda ha Domanda + Suggerimento + Perché (vedi STEP 6)
- [ ] ⚠️ **NO ELENCHI PUNTATI**: Nessuna domanda contiene sottopunti (una domanda = un aspetto)
- [ ] ⚠️ **SUGGERIMENTI COPIABILI**: Ogni suggerimento è frase completa, non keyword
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
