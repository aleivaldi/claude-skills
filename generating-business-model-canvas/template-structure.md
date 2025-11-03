# Template Excel Structure - Cell Mapping

Questo documento definisce **esattamente** dove scrivere in ogni foglio del template Excel.

## ⚠️ CRITICO: Celle Mergiate GRANDI

**ATTENZIONE**: Questo template usa CELLE UNICHE MERGIATE MOLTO GRANDI per ogni sezione.

### Regola Fondamentale
- **NON scrivere in celle separate** (es. B12, B13, B14...)
- **Scrivi in UN'UNICA CELLA** (top-left del merge) usando `\n` per andare a capo
- Esempio: Per Key Partners → Scrivi TUTTO in **B10** con `\n` tra items

### Formato Corretto
```
B10 = "🔴 Partner 1 - desc\n🔴 Partner 2 - desc\n🟡 Partner 3 - desc"
```

### ❌ Formato SBAGLIATO (non funziona)
```
B12 = "🔴 Partner 1"  # ← NON FARE: B12 è dentro B10:E47 merge
B13 = "🔴 Partner 2"  # ← NON FARE: errore MergedCell read-only
```

## Sheet 1: Business Model Canvas

### Metadata
- **J4**: Nome progetto (es. "MyKaraoke")
- **N4**: Designer/Team
- **U4**: Versione
- **W4-W5**: Lasciare intatti (link documentazione)

### ⚠️ IMPORTANTE: Celle Mergiate Grandi

**TUTTE le sezioni sono CELLE UNICHE MERGIATE**. NON scrivere righe separate (B12, B13, B14...), ma scrivi in UN'UNICA CELLA usando `\n` per andare a capo.

### Key Partners (B10:E47 - CELLA UNICA)
**Area di scrittura**: **B10** (cella merged B10:E47)
**Contenuto**: Lista partner con a capo `\n` tra items
**Formato**:
```
🔴 Partner 1 - description
🔴 Partner 2 - description
🟡 Partner 3 - description
```

### Key Activities (F10:I27 - CELLA UNICA)
**Area di scrittura**: **F10** (cella merged F10:I27)
**Contenuto**: Attività chiave con a capo `\n`
**Formato**: `🔴 Activity\n🟡 Activity 2\n...`

### Key Resources (F30:I47 - CELLA UNICA)
**Area di scrittura**: **F30** (cella merged F30:I47)
**Contenuto**: Risorse chiave con a capo `\n`
**Formato**: `🔴 Resource\n🟡 Resource 2\n...`

### Value Propositions (J10:M47 - CELLA UNICA)
**Area di scrittura**: **J10** (cella merged J10:M47)
**Contenuto**: Value propositions con a capo `\n`
**Formato**: `🔴 Value prop\n🟡 Value prop 2\n...`

### Customer Relationships (N10:Q27 - CELLA UNICA)
**Area di scrittura**: **N10** (cella merged N10:Q27)
**Contenuto**: Relazioni clienti con a capo `\n`
**Formato**: `🔴 Relationship\n🟡 Relationship 2\n...`

### Customer Segments (R10:U47 - CELLA UNICA)
**Area di scrittura**: **R10** (cella merged R10:U47)
**Contenuto**: Segmenti target con a capo `\n`
**Formato**: `🔴 Segment\n🟡 Segment 2\n...`

### Channels (N30:Q47 - CELLA UNICA)
**Area di scrittura**: **N30** (cella merged N30:Q47)
**Contenuto**: Canali con a capo `\n`
**Formato**: `🔴 Channel\n🟡 Channel 2\n...`

### Cost Structure (B50:K60 - CELLA UNICA)
**Area di scrittura**: **B50** (cella merged B50:K60)
**Contenuto**: Costi con a capo `\n`
**Formato**: `🔴 Cost 1\n🟡 Cost 2\n...`

### Revenue Streams (L50:U60 - CELLA UNICA)
**Area di scrittura**: **L50** (cella merged L50:U60)
**Contenuto**: Revenue streams con a capo `\n`
**Formato**: `🔴 Revenue 1\n🟡 Revenue 2\n...`

---

## Sheet 2: Lean Canvas

### Metadata
- **J4**: Nome progetto
- **N4**: Designer/Team
- **U4**: Versione

### ⚠️ CELLE UNICHE MERGIATE

### Problem (B10:E27 - CELLA UNICA)
**Area di scrittura**: **B10** (cella merged B10:E27)
**Contenuto**: Top 3 problemi con `\n` tra items
**Formato**: `🔴 Problem 1\n🔴 Problem 2\n🔴 Problem 3`

### Existing Alternatives (B30:E47 - CELLA UNICA)
**Area di scrittura**: **B30** (cella merged B30:E47)
**Contenuto**: Alternative esistenti con `\n`
**Formato**: `🟡 Alternative 1\n🟡 Alternative 2`

### Solution (F10:I27 - CELLA UNICA)
**Area di scrittura**: **F10** (cella merged F10:I27)
**Contenuto**: Top 3 soluzioni con `\n`
**Formato**: `🔴 Solution 1\n🔴 Solution 2\n🔴 Solution 3`

### Key Metrics (Colonne F-I, Righe 32-46)
**Area di scrittura**: F32, F33, F34...
**Contenuto**: Metriche chiave da misurare
**Formato**: `🔴 Metric name - target`

### Unique Value Proposition (Colonne J-M, Righe 12-26)
**Area di scrittura**: J12
**Contenuto**: Singolo messaggio chiaro e convincente
**Formato**: `🔴 Clear, compelling one-liner`

### High-Level Concept (Colonne J-M, Righe 30-36)
**Area di scrittura**: J30
**Contenuto**: Concetto high-level (X for Y)
**Formato**: `🟡 "Like X but for Y"`

### Unfair Advantage (Colonne N-Q, Righe 12-26)
**Area di scrittura**: N12, N13, N14...
**Contenuto**: Vantaggi non copiabili
**Formato**: `🔴 Advantage description`

### Channels (Colonne N-Q, Righe 32-46)
**Area di scrittura**: N32, N33, N34...
**Contenuto**: Percorsi verso clienti
**Formato**: `🔴 Channel - strategy`

### Customer Segments (Colonne R-U, Righe 12-26)
**Area di scrittura**: R12, R13
**Contenuto**: Target Customers + Target Users
**Formato**:
- R12: `🔴 Target Customers`
- R13: `🔴 Target Users`

### Early Adopters (Colonne R-U, Righe 30-36)
**Area di scrittura**: R30, R31, R32...
**Contenuto**: Early adopters specifici
**Formato**: `🔴 Early adopter profile`

### Cost Structure (Colonne B-K, Righe 52-60)
**Area di scrittura**: B52, B53, B54, B55...
**Contenuto**: Costi con categorie specifiche
**Formato**: `🔴 Category: amount`
**Categorie suggerite**: CAC, Distribution, Hosting, People

### Revenue Streams (Colonne L-U, Righe 52-60)
**Area di scrittura**: L52, L53, L54, L55...
**Contenuto**: Revenue model details
**Formato**: `🔴 Category: value`
**Categorie suggerite**: Revenue Model, LTV, Revenue, Gross Margin

---

## Sheet 3: Customer Personas Canvas

### Metadata
- **J4**: Nome progetto
- **N4**: Designer/Team
- **U4**: Versione

### ⚠️ CELLE MERGIATE A BLOCCHI

Sheet 3 usa merge "a blocchi" più piccoli (ogni 2-3 righe), NON un'unica cella grande.

### Persona 1 (Colonne D-I)

**Persona Name (D8:I9 - MERGE)**:
- **Area**: D8 (cella merged D8:I9)
- **Contenuto**: Nome descrittivo persona
- **Formato**: `Gestore Locale Mid-Market`

**Description (D10:I12 - MERGE)**:
- **Area**: D10 (cella merged D10:I12)
- **Contenuto**: One-liner con a capo se necessario
- **Formato**: `Bar/pub con 2-8 serate karaoke/mese\n50-200 partecipanti`

**Attributes (Merge multipli D15-D59)**:
Ogni attributo occupa un merge di 2-3 righe. Scrivi in cella top-left:
- **D15:I17** → Demographics
- **D18:I20** → Comportamenti
- **D21:I23** → Altri attributi
- [continua pattern ogni 3 righe]

**Formato**: Usa `\n` per a capo dentro ogni blocco merged

### Persona 2 (Colonne L-Q)
**Struttura identica a Persona 1**:
- **L8:Q9** → Nome persona
- **L10:Q12** → Description
- **L15:Q17, L18:Q20...** → Attributes

### Persona 3 (Colonne T-Y)
**Struttura identica a Persona 1**:
- **T8:Y9** → Nome persona
- **T10:Y12** → Description
- **T15:Y17, T18:Y20...** → Attributes

---

## Sheet 4: Channel Implementation Canvas

### Metadata
- **J4**: Nome progetto
- **N4**: Designer/Team
- **U4**: Versione

### ⚠️ CELLE MERGIATE A BLOCCHI (9 righe per fase)

Sheet 4 usa merge verticali grandi (~9 righe) per ogni fase del customer journey.

### Segment 1 (Colonne D-I)

**Segment Name (D8:I9 - MERGE)**:
- **Area**: D8
- **Contenuto**: Nome segmento
- **Formato**: `Gestore Locale Mid-Market`

**Description (D10:I12 - MERGE)**:
- **Area**: D10
- **Contenuto**: One-liner descrizione
- **Formato**: `Bar/pub 2-8 serate/mese Italia`

**Header (D13:E14)**: Intestazione "KEY ACTIVITIES"

#### Per ogni fase (5 fasi totali):

**AWARENESS (Righe 15-23)**:
- **D15:E23** → KEY ACTIVITIES (scrivi in D15 con `\n`)
- **F15:G23** → KEY RESOURCES (scrivi in F15 con `\n`)
- **H15:I23** → KEY PARTNERS (scrivi in H15 con `\n`)

**EVALUATION (Righe 24-32)**:
- **D24:E32** → KEY ACTIVITIES (scrivi in D24 con `\n`)
- **F24:G32** → KEY RESOURCES (scrivi in F24 con `\n`)
- **H24:I32** → KEY PARTNERS (scrivi in H24 con `\n`)

**PURCHASE (Righe 33-41)**:
- **D33:E41** → KEY ACTIVITIES (scrivi in D33)
- **F33:G41** → KEY RESOURCES (scrivi in F33)
- **H33:I41** → KEY PARTNERS (scrivi in H33)

**DELIVERY (Righe 42-50)**:
- **D42:E50** → KEY ACTIVITIES (scrivi in D42)
- **F42:G50** → KEY RESOURCES (scrivi in F42)
- **H42:I50** → KEY PARTNERS (scrivi in H42)

**AFTER SALES (Righe 51-59)**:
- **D51:E59** → KEY ACTIVITIES (scrivi in D51)
- **F51:G59** → KEY RESOURCES (scrivi in F51)
- **H51:I59** → KEY PARTNERS (scrivi in H51)

**Formato**: `🔴 Item 1\n🟡 Item 2\n🟢 Item 3` (usa `\n` per a capo)

### Segment 2 (Colonne L-R)
**Struttura identica a Segment 1**:
- **L8:Q9** → Segment Name
- **L10:Q12** → Description
- **L15:M23, N15:O23, P15:Q23** → Awareness (Activities, Resources, Partners)
- [pattern identico per altre fasi]

### Segment 3 (Colonne T-Z)
**Struttura identica a Segment 1**:
- **T8:Y9** → Segment Name
- **T10:Y12** → Description
- [pattern identico per fasi]

---

## Sheet 5: Value Proposition Canvas i

### Metadata
- **J4**: Nome progetto
- **N4**: Designer/Team
- **U4**: Versione

### ⚠️ CELLE UNICHE MERGIATE GRANDI (come Sheet 1 e 2)

### PRODUCT SIDE (Sinistra)

#### Benefits (B10:E27 - CELLA UNICA)
**Area di scrittura**: **B10** (cella merged B10:E27)
**Contenuto**: Benefici con `\n` tra items
**Formato**: `🔴 Benefit 1\n🔴 Benefit 2\n🟡 Benefit 3`

#### Features (B30:E47 - CELLA UNICA)
**Area di scrittura**: **B30** (cella merged B30:E47)
**Contenuto**: Feature fattuali con `\n`
**Formato**: `🔴 Feature 1\n🟡 Feature 2`

#### Company (B52:E53 - MERGE)
**Area di scrittura**: **B52**
**Contenuto**: Nome azienda
**Formato**: `MyKaraoke`

#### Value Proposition (B57:E58 - MERGE)
**Area di scrittura**: **B57**
**Contenuto**: Statement value proposition
**Formato**: `Sistema votazione interattivo + Analytics per locali`

### CUSTOMER SIDE (Destra)

#### Emotional Drivers (N10:Q27 - CELLA UNICA)
**Area di scrittura**: **N10** (cella merged N10:Q27)
**Contenuto**: Driver emozionali con `\n`
**Formato**: `🔴 Driver 1\n🔴 Driver 2`

#### Dark Side (R10:U47 - CELLA UNICA)
**Area di scrittura**: **R10** (cella merged R10:U47)
**Contenuto**: Paure/concerns con `\n`
**Formato**: `🔴 Fear 1\n🟡 Fear 2`

#### Rational Needs (N30:Q47 - CELLA UNICA)
**Area di scrittura**: **N30** (cella merged N30:Q47)
**Contenuto**: Bisogni razionali con `\n`
**Formato**: `🔴 Need 1\n🟡 Need 2`

#### Substitutes (N54:U63 - MERGE)
**Area di scrittura**: **N54**
**Contenuto**: Alternative non ovvie con `\n`
**Formato**: `Excel per gestione playlist\nSelezione manuale tradizionale`

---

## Sheet 6: Value Proposition Canvas II

### Metadata
- **J4**: Nome progetto
- **N4**: Designer/Team
- **U4**: Versione

**Nota**: Questo è un layout alternativo dello stesso canvas. Usa Value Proposition Canvas i preferibilmente.

---

## Regole Generali

### Priorità Colorate
- 🔴 = Alta priorità (critico/bloccante)
- 🟡 = Media priorità (importante)
- 🟢 = Bassa priorità (nice-to-have)

### Text Wrapping
**SEMPRE** abilita text wrapping per tutte le celle con contenuto:
```python
cell.alignment = Alignment(wrap_text=True, vertical='top')
```

### Merged Cells
**IMPORTANTE**: Scrivi sempre nella cella top-left dell'area merged. Se provi a scrivere in una MergedCell riceverai errore "read-only".

### Numero di Item per Sezione
- **Minimo**: 3 item per sezione principale
- **Massimo**: 7 item per sezione principale
- **Ottimale**: 4-5 item per sezione

### Formato Testo
Mantieni testo **sintetico**:
- 1 riga = 1 concetto
- Max 60-80 caratteri per riga
- NO paragrafi lunghi
