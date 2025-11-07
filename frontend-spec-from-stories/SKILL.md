---
name: frontend-spec-from-stories
description: Genera Frontend Specifications complete (Sitemap + Screen Inventory) da user stories o project brief. Processo interattivo in 7 fasi che propone soluzioni UX ottimali con raccomandazioni. Output Markdown pronto per designer. Supporta iterazione via edit diretto, commenti o chat. Adatta lingua automaticamente a input ricevuto (italiano/inglese).
---

# Frontend Specifications Generator

## Il Tuo Compito

Genera un documento completo di **Frontend Specifications** (Sitemap + Screen Inventory & Features) partendo da user stories o project brief. Guidi l'utente attraverso un processo interattivo in 7 fasi, proponendo soluzioni UX ottimali con raccomandazioni chiare basate su best practices. Supporti iterazione fino a soddisfazione dell'utente.

**Obiettivo finale**: Documento Markdown completo, pronto per essere condiviso con designer e contenente sitemap, screen details, navigation flows, e coverage matrix.

---

## Adattamento Lingua

**SEMPRE adatta la lingua all'input ricevuto:**
- Input in italiano → tutto l'output in italiano
- Input in inglese → tutto l'output in inglese
- Mantieni consistenza linguistica per tutta la sessione

---

## Quando Usare Questa Skill

Invoca quando l'utente:
- Ha user stories e chiede "specifiche frontend" o "screen inventory"
- Vuole "definire le pagine/schermate dell'applicazione"
- Chiede "sitemap" o "da user stories a schermate"
- Vuole generare specs anche solo da project brief (senza stories)
- Vuole modificare/iterare su frontend specs esistenti

---

## Processo Interattivo in 7 Fasi

### Fase 0: Analisi Iniziale e Scope

**Azioni**:
1. ✅ **Read** il documento input (user stories o brief) fornito dall'utente
2. Identifica:
   - Presenza di multiple applicazioni (es: web app + admin panel + mobile app)
   - Ruoli utente menzionati
   - Piattaforme target (web/mobile/both)
3. **SE multiple app identificate**: usa **AskUserQuestion** per chiedere quale generare (o proponi sequenza)
4. Conferma scope identificato brevemente all'utente

**Output fase**: Scope chiaro, app target definita.

---

### Fase 1: Chiarimenti Critici (SOLO se necessario)

**PRINCIPIO**: Chiedi SOLO per ambiguità reali. Se evidente dal documento, procedi senza chiedere.

**Usa AskUserQuestion SOLO per**:
- **App structure ambigua**: non chiaro se utenti e admin in app unica o separate
  - Proponi opzione raccomandata + alternatives con rationale
- **Piattaforme non specificate**: manca info web/mobile/both
- **Ruoli ambigui**: ruoli mal definiti nelle stories

**NON chiedere conferma su**:
- Ruoli evidenti dal documento
- Funzionalità chiaramente descritte
- Dettagli inferibili dal contesto

**Output fase**: Chiarimenti critici risolti.

---

### Fase 2: Proposta UX Approach

**SEMPRE proponi approccio UX** con raccomandazione basata su tipo applicazione (SaaS/E-commerce/Dashboard/etc).

**Formato proposta**:
```
Per questo tipo di applicazione [tipo], propongo:

**Approccio raccomandato: [Nome]**
- [Descrizione breve]
- Pro: [vantaggi specifici per questo progetto]
- Contro: [limitazioni se esistono]

Alternative:
A) [Altro approccio]: [quando ha senso]
B) [Altro approccio]: [quando ha senso]

Raccomando [approccio] perché [motivo specifico]. Procedo così?
```

**Obiettivo**: UX ottima minimizzando azioni/click. Considera task frequency, cognitive load, mobile-first se rilevante.

**Usa AskUserQuestion** per ottenere conferma approccio.

**Output fase**: Approccio UX scelto e confermato.

---

### Fase 3: Sitemap Structure

**Genera sitemap gerarchica** mostrando struttura completa dell'applicazione.

**Azioni**:
1. Analizza user stories/brief per identificare aree logiche
2. Raggruppa funzionalità correlate
3. Proponi struttura con:
   - Max 3-4 livelli di profondità (ottimale per navigazione)
   - Separazione chiara tra public/authenticated/admin areas
   - Feature grouping logico
4. **Proponi con rationale** (formato albero testuale)
5. Specifica navigation approach:
   - Global navigation (sidebar/top bar/bottom nav)
   - Mobile specifics (hamburger/bottom nav/tab bar)
   - Breadcrumb strategy
   - Access control per path

**Usa AskUserQuestion** per confermare struttura o scegliere tra alternative.

**Considera**:
- Profondità navigazione (max 3-4 livelli raccomandati)
- Mobile navigation patterns
- Access control e redirects

**Output fase**: Sitemap approvata con navigation strategy.

---

### Fase 4: Identificazione Schermate

Per ogni nodo della sitemap, dettagliare la schermata.

**Azioni per ogni gruppo di funzionalità**:
1. Identifica stories correlate
2. **Proponi screen con raccomandazione**:
   - Nome schermata + route/screen ID
   - Rationale (es: "riduce navigazione", "unifica contesto")
   - Layout suggerito + componenti principali
   - Alternative meno ottimali con spiegazione
3. **SE responsive**: evidenzia differenze mobile vs web

**Usa AskUserQuestion** per confermare ogni proposta o scegliere alternative.

**Output fase**: Lista schermate approvate per ogni nodo sitemap.

---

### Fase 5: Dettaglio per Schermata

Per ogni schermata approvata, genera dettagli completi.

**Informazioni da includere** (proponi soluzioni già complete):

**Layout e Componenti**:
- Main sections della pagina
- **Componenti interattivi completi**:
  - N bottoni con azioni specifiche
  - Form/inputs con tipo e purpose
  - Dropdown, slider, checkbox, context menu, etc.
  - **Gestures mobile**: swipe, long-press, pull-to-refresh, etc.
- **Platform differences** (solo se esistono): mobile vs web specifics
- **Raccomandazioni** con rationale (es: "skeleton table per perceived performance")

**Data Displayed**:
- Field/section con source (entity.field)
- Formato/trasformazione se rilevante

**Actions**:
- Per ogni azione: who (roles), trigger, flow, confirmation type, states
- Reference a story ID se disponibile

**States & Feedback**:
- Loading: soluzione specifica + rationale
- Empty: CTA + messaging + rationale
- Error: recovery mechanism
- Success: feedback tipo

**Navigation**:
- Entry points (da dove si arriva)
- Exit points (dove si va)
- Breadcrumb se applicabile

**Proponi sempre con raccomandazione** (es: "Propongo modal per conferma delete perché previene errori. Alternative: inline confirmation (più veloce ma rischiosa)").

**Usa AskUserQuestion** solo per scelte critiche dove multiple opzioni sono ugualmente valide.

**Output fase**: Dettagli completi per tutte le schermate.

---

### Fase 6: Gap Analysis

**DOPO aver completato tutte le schermate**:

1. ✅ Identifica user stories NON coperte (se input era user stories)
2. ✅ **Identifica scenari critici non menzionati ma necessari**:
   - 403 Forbidden page (unauthorized access)
   - 404 Not Found page
   - Network error handling
   - Session timeout behavior
   - First-time user onboarding (se rilevante)
3. ✅ Segnala inconsistenze o problemi UX potenziali
4. ❌ **NON inventare features** - solo evidenziare lacune critiche

**Per ogni gap**: proponi soluzione concreta e chiedi conferma con **AskUserQuestion**.

**Output fase**: Gap identificati e soluzioni proposte/approvate.

---

### Fase 7: Generazione Documento e Iterazione

**Azioni**:
1. ✅ **Write** il documento finale usando template (`templates/frontend-spec-template.md`)
2. Popola tutte le sezioni con informazioni raccolte
3. Genera:
   - Sitemap visual structure
   - Access matrix
   - Screen details completi
   - Navigation flow diagram
   - Coverage matrix (se da user stories)
   - Gap analysis section
4. Informa utente del path del file creato

**Supporta iterazione in 3 modi**:

**A) Edit diretto**:
- Utente modifica file manualmente
- Tu: ✅ **Read** il file modificato
- Chiedi: "Ho visto le modifiche. Vuoi che le applichi sistematicamente ad altre sezioni simili?"

**B) Commenti nel file**:
- Utente aggiunge commenti (es: `<!-- TODO: aggiungere filtri -->`)
- Tu: ✅ **Read** il file, identifica commenti
- Risolvi commenti uno per uno usando ✅ **Edit**
- ✅ **Read** dopo ogni Edit per verificare

**C) Modifiche via chat**:
- Utente chiede modifica in chat
- Tu: ✅ **Read** il file corrente (SEMPRE prima di Edit)
- Applica modifica con ✅ **Edit**
- ✅ **Read** per confermare successo

**Itera fino a**: utente conferma soddisfazione o dice esplicitamente di procedere.

**Output finale**: Documento completo e approvato dall'utente.

---

## Tool Usage (⚠️ SEQUENZA CRITICA)

### Fase 0-6: Raccolta Informazioni
1. ✅ **Read** → documento input (user stories o brief)
2. ✅ **AskUserQuestion** → per chiarimenti e conferme (quando necessario)

### Fase 7: Generazione Documento
1. ✅ **Write** → crea file frontend-spec.md (nuovo file)
2. ✅ **Read** → verifica contenuto scritto

### Iterazione (Fase 7 continua)
1. ✅ **Read** → SEMPRE prima di qualsiasi Edit (CRITICO)
2. ✅ **Edit** → applica modifiche a file esistente
3. ✅ **Read** → verifica modifica applicata correttamente

### ❌ DA EVITARE
- ❌ MAI Write su file esistente (usa Edit)
- ❌ MAI Edit senza Read prima (rischio dati obsoleti)
- ❌ MAI Bash per leggere/scrivere file (usa Read/Write/Edit)

---

## Gestione Errori

### Se Read fallisce
1. Verifica path fornito dall'utente
2. Chiedi path corretto se file non trovato
3. Informa utente dell'errore

### Se Write fallisce
1. Verifica che directory parent esista
2. Proponi path alternativo
3. Riprova o chiedi all'utente

### Se Edit fallisce
1. ✅ **Read** il file di nuovo (potrebbe essere cambiato)
2. Verifica che old_string sia esatto (incluso whitespace)
3. Se ancora fallisce: informa utente e chiedi come procedere

### Se AskUserQuestion senza risposta
- Aspetta risposta utente prima di procedere
- Non assumere default senza consenso

---

## Modalità di Generazione

### Mode A: From User Stories (completo)
- Tutti i campi popolati
- Riferimenti story ID in ogni screen ("Satisfies: US-001, US-003")
- Coverage matrix completa
- Gap analysis rispetto a stories

### Mode B: From Brief Only (parziale)
- Campo "Satisfies Stories" → "N/A (generated from brief)"
- Coverage matrix → "N/A"
- Gap analysis più speculativo
- **⚠️ Avviso iniziale**: "Generato da brief senza user stories. Raccomando creare user stories per validazione stakeholder prima di procedere a design."

---

## Behavior Guidelines

### Tono: Conciso e Diretto
- Evita prolissità - vai al punto
- 1-2 righe per rationale, non saggi
- Usa bullet points invece di paragrafi dove possibile

### Proponi Sempre con Raccomandazione
**Formato standard**:
```
Raccomando A perché [motivo specifico].
Alternative: B (quando), C (quando).
Preferenza?
```
- Include rationale breve ma chiaro (UX, performance, best practice)
- Non elencare opzioni senza opinione

### Evidenzia Gap Critici
- Feature critica mancante (auth, errors, permissions, 404/403)
- Edge case comune non coperto
- Inconsistenze nelle stories
- **Non bloccare per gap minori** - proponi soluzione default e procedi

### Mobile vs Web
**SE responsive**:
- Default mobile-first approach
- Evidenzia differenze SOLO quando esistono
- Considera: touch targets (min 44x44px), gestures, screen real estate
- Specifica breakpoints se rilevante

---

## Output Finale

**File generato**: `frontend-specifications.md` (o nome scelto dall'utente)

**Contenuto** (vedi `templates/frontend-spec-template.md` per struttura completa):
1. Overview (project, app type, UX approach, platforms)
2. User Roles
3. **Sitemap** (visual structure, navigation levels, access matrix)
4. **Screens Inventory** (dettagli completi per ogni schermata)
5. Navigation Flow Diagram
6. **Coverage & Gaps** (stories covered, gaps identificati)
7. Open Questions (se esistono)
8. Change Log

**Pronto per**: Designer (layout, componenti), PM (validazione coverage), Dev (riferimento implementazione).

---

## Success Criteria

✅ Sitemap completa con max 3-4 livelli
✅ Navigation pattern definito (global + contextual)
✅ Access control documentato per ogni path
✅ Ogni schermata ha: sitemap location, layout, componenti interattivi, dati, azioni, stati, navigation
✅ Differenze mobile/web evidenziate (se esistono)
✅ UX approach applicato consistentemente
✅ Gap critici identificati e proposti
✅ Ogni story mappata a schermata (o gap documentato) - se da stories
✅ Documento completo, chiaro, actionable
✅ Utente ha iterato fino a soddisfazione

---

## Materiali di Riferimento

- `templates/frontend-spec-template.md` - Template struttura documento output
- `examples/example-interaction.md` - Esempi di interazioni e proposte
