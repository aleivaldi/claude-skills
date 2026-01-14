---
name: generating-business-plan
description: Genera Business Plan finanziario completo in Excel (P&L, Balance Sheet, Cash Flow) + Markdown esplicativo. Workflow interattivo con validazione dati. Supporta input flessibili e genera ipotesi giustificate per dati mancanti. Usa quando l'utente chiede "business plan", "financial model", "proiezioni finanziarie" o ha brief/quotazioni da trasformare in modello finanziario.
---

# Generating Business Plan

## Il Tuo Compito

Genera Business Plan finanziario **Excel** completo (3-5 anni) + **Markdown** esplicativo con assunzioni e analisi.

**Output**:
1. `business-plan.xlsx` - Modello finanziario completo con 4 fogli:
   - **Input**: Tutti gli input e assunzioni
   - **Output**: P&L, Balance Sheet, Cash Flow (vista mensile/annuale)
   - **Financial Statements**: Prospetti consolidati annuali
2. `business-plan.md` - Documentazione dettagliata che spiega assunzioni, ipotesi e analisi

---

## Workflow (7 Step)

### A. Analizza Input Esistenti
1. Raccogli tutti i documenti disponibili:
   - Brief strutturato o raw
   - Requirements document
   - Competitor analysis
   - Quotazioni tecniche (es. POC, sviluppo)
   - Altri documenti finanziari
2. Estrai dati rilevanti per il business plan:
   - Costi di sviluppo (R&D, PoC, MVP)
   - Prezzi di vendita previsti
   - Target market size
   - Canali di distribuzione
   - Team previsto
3. **Output step**: Lista dati estratti con fonte per ogni dato

### B. Identifica Gap e Genera Ipotesi
1. Confronta dati estratti con input richiesti (vedi sezione Input Richiesti)
2. Per ogni dato mancante:
   - **Se estrapolabile**: Genera ipotesi basata su:
     - Informazioni dai documenti (es. se c'è quotazione PoC €50k, ipotizza Capex iniziale)
     - Best practices di settore (es. LTV/CAC 3-5x per SaaS)
     - Benchmark competitor (se disponibile competitor analysis)
   - **Se non estrapolabile**: Segna come "da chiedere all'utente"
3. **Output step**: Tabella con:
   - Dato richiesto | Valore proposto | Fonte/Giustificazione | Confidence (Alta/Media/Bassa)

### C. Chiedi Conferma e Integrazioni (interattivo)
1. Presenta tabella generata allo step B
2. Per dati con confidence Alta/Media: "Ho ipotizzato X basandomi su Y. Confermi o vuoi modificare?"
3. Per dati "da chiedere": Poni domanda specifica con:
   - Contesto (perché serve il dato)
   - Range sensato (se applicabile)
   - Esempio pratico
4. **Validazione intelligente**:
   - Se risposta utente sembra incongrua (es. COGS > Prezzo vendita), evidenzialo:
     - "⚠️ Il COGS di €X supera il prezzo di vendita €Y, con margine negativo del Z%. Confermi o vuoi rivedere?"
     - Suggerisci valore alternativo sensato
     - Chiedi conferma esplicita per procedere
5. **Loop**: Ripeti fino a conferma completa dataset

### D. Genera JSON Strutturato
1. Organizza tutti i dati validati in formato JSON (vedi sezione JSON Format)
2. Calcola valori derivati (es. monthly inflation da annual)
3. **Write**: Salva in `/tmp/bp_data.json`
4. **Output step**: Conferma "Dataset validato e strutturato"

### E. Genera Excel con Script Python
1. **Bash**: Copia template Excel da skill folder
   ```bash
   cp ~/.claude/skills/generating-business-plan/template/business-plan-template.xlsx business-plan.xlsx
   ```
2. **Bash**: Esegui script Python
   ```bash
   python3 ~/.claude/skills/generating-business-plan/scripts/populate_excel.py business-plan.xlsx /tmp/bp_data.json
   ```
3. **Bash**: Ricalcola formule con LibreOffice
   ```bash
   python3 ~/.claude/skills/generating-business-plan/scripts/recalc.py business-plan.xlsx
   ```
4. **Bash**: Rimuovi JSON temporaneo
   ```bash
   rm /tmp/bp_data.json
   ```
5. **Output step**: "Business plan Excel generato in business-plan.xlsx"

### F. Verifica Excel (loop)
1. Annuncia completamento con path assoluto file
2. Chiedi all'utente di aprire e verificare
3. Se modifiche richieste:
   - Ascolta feedback
   - Aggiorna JSON e rigenera (Step D-E)
   - Loop
4. Quando approvato → procedi a Step G

### G. Genera Markdown Esplicativo
1. **Write**: Crea `business-plan.md` con:
   - **Executive Summary**: Sintesi risultati finanziari chiave (3-5 anni)
   - **Assunzioni Chiave**: Tutte le ipotesi principali con giustificazione
   - **Analisi Finanziaria**:
     - Revenue model e crescita
     - Cost structure e break-even
     - Cash flow e fabbisogno finanziario
     - Key metrics (Gross Margin, EBITDA, Burn Rate, Runway)
   - **Scenari e Sensitivity**: Cosa succede se variabili chiave cambiano
   - **Note e Caveat**: Limitazioni del modello, aree di incertezza
2. **Output step**: Annuncia path assoluto Markdown

### H. Verifica Markdown (loop)
1. Chiedi review del documento Markdown
2. Se modifiche richieste:
   - **Read** `business-plan.md` PRIMA di Edit
   - **Edit** con modifiche specifiche
   - Loop
3. Quando approvato → skill completata

---

## Uso Tool (⚠️ SEQUENZA CRITICA)

### Step D: JSON Generation
1. ✅ **Write** per creare `/tmp/bp_data.json` (file temporaneo)

### Step E: Excel Generation
1. ✅ **Bash** per copiare template (operazione sistema)
2. ✅ **Bash** per eseguire populate_excel.py
3. ✅ **Bash** per eseguire recalc.py (MANDATORY)
4. ✅ **Bash** per cleanup JSON

### Step G: Markdown Creation
1. ✅ **Write** per creare `business-plan.md` (file nuovo)

### Step H: Markdown Iteration
1. ✅ **SEMPRE Read** prima di Edit (CRITICO)
2. ✅ **Edit** per modificare Markdown esistente (MAI Write su file esistente)

### Best Practices Tool
- ❌ **MAI** Edit senza Read prima (dati obsoleti)
- ❌ **MAI** Write su file esistenti (corrompe contenuto)
- ✅ Bash SOLO per script system (Python, git, rm)
- ✅ AskUserQuestion per conferme validazioni

---

## Input Richiesti

**Dettaglio completo**: Vedi `questions/` directory per guide interattive.

**Summary rapido**:

### 1. Periodo e Macro
- **Periodo di proiezione**: Data inizio, durata (mesi), granularità (mensile/trimestrale)
- **Annual inflation rate**: Default 2% (adattabile per paese/periodo)

### 2. Revenue Model
#### Amazon (se applicabile)
- **Price (VAT excluded)**: Prezzo vendita per unità
- **Quantity**: Volume vendite per periodo
- **Growth rate**: Crescita mensile/trimestrale volumi (opzionale)

#### Distribution (se applicabile)
- **Price (VAT excluded)**: Prezzo B2B per distributori
- **Quantity**: Volume vendite per periodo
- **Growth rate**: Crescita vendite (opzionale)

#### Altri canali
- Specificare se SaaS subscription, licensing, servizi, etc.

### 3. Cost of Goods Sold (COGS)
- **Product COGS per unit**: Costo produzione unitario
- **Amazon referral fee %**: Default 15% (verificare per categoria)
- **Packaging cost per unit**: Costo packaging
- **Shipping costs**:
  - Factory → Warehouse
  - Warehouse → Distributor
  - Warehouse → Amazon FBA
  - Direct to customer (se D2C)

### 4. Marketing
- **LTV/CAC target**: Default 3-5x (SaaS best practice)
- **CAC per customer**: Costo acquisizione cliente (se noto)
- Oppure: **Marketing budget %** of revenue

### 5. Personnel
Per ogni ruolo:
- **Salary** (lordo mensile)
- **FTE** (Full Time Equivalent): numero persone per periodo
- **Hiring plan**: quando assumere (opzionale)

Ruoli standard:
- C-Level (Founder/CEO)
- Finance
- Sales
- Marketing
- Product/Engineering
- Operations

Altri dati:
- **Pension provision rate**: Default 6.91% (Italia, adattare per paese)
- **Capitalization rate**: % di costi R&D capitalizzabili (se applicabile)

### 6. General & Administrative (G&A)
- **Warehouse/Office rent**: Affitto mensile
- **SaaS per employee**: Tool e software per dipendente (~€200/mese)
- **CPA/Accounting**: Costi commercialista mensili
- **HR Consultant cost per employee**: ~€30/mese
- **Other costs %**: Catch-all per imprevisti (default 15% di G&A)

### 7. Taxes
- **IRES**: Corporate tax rate (Italia 24%, verificare paese)
- **IRAP**: Regional tax (Italia 3.9%, specificare se applicabile)
- **VAT**: IVA (Italia 22%, adattare per paese/prodotto)

### 8. Financing
- **Equity injection**: Capitale iniziale, timing round successivi
- **Debt**: Prestiti, interest rate
- **Grants**: Contributi a fondo perduto (specificare timing)

### 9. Capital Expenditure (Capex)
#### Intangible Assets (Software, IP, R&D)
- **Tech & Product development**: Costi iniziali (es. PoC €50k, MVP €150k)
- **Ongoing R&D**: Costi ricorrenti
- **Amortization rate**: Default 20% yearly (5 anni)

#### Tangible Assets (Hardware, Office Equipment)
- **Capex per employee**: ~€1000-2000 (laptop, desk, etc.)
- **Production equipment**: Macchinari, hardware specifico
- **Depreciation rate**: Default 33.33% yearly (3 anni)

---

## JSON Format

**Riferimento completo**: Vedi `json-format-reference.md` per struttura dettagliata.

**Regole chiave**:
- Importi in unità base (EUR, USD)
- Percentuali decimali (15% = 0.15)
- Arrays temporali: Se più corto, ultimo valore ripetuto
- Validare con: `python3 -m json.tool /tmp/bp_data.json`

---

## Script Python

### `scripts/populate_excel.py`
Popola template Excel con dati da JSON.

**Usage**:
```bash
python3 populate_excel.py <excel_file> <data_json>
```

### `scripts/recalc.py`
Ricalcola formule Excel usando LibreOffice (MANDATORY dopo populate).

**Usage**:
```bash
python3 recalc.py <excel_file>
```

**Output**:
```json
{
  "status": "success",
  "total_errors": 0,
  "total_formulas": 523,
  "error_summary": {}
}
```

Se errori trovati, fixare e ricorrere fino a `total_errors: 0`.

---

## File di Riferimento

- `template/business-plan-template.xlsx` - Template Excel base (pulito, senza dati esempio)
- `scripts/populate_excel.py` - Script principale popolamento
- `scripts/recalc.py` - Ricalcolo formule con LibreOffice
- `json-format-reference.md` - Struttura JSON completa con esempi
- `validation-rules.md` - Regole validazione (3 livelli: CRITICAL, WARNING, INFO)
- `questions/` - Guide interattive per raccolta dati (revenue, costs, financing)
- `examples/validation-examples.md` - Esempi concreti di validazioni e warning

---

## Regole Chiave

### Esecuzione
- ❌ **MAI** chiedere permesso per creare/modificare file
- ✅ Usa script Python pre-installati (no codice inline)
- ✅ Un solo JSON temporaneo in `/tmp/`
- ✅ SEMPRE ricalcolare formule con `recalc.py` dopo populate
- ✅ Verificare zero errori formule prima di procedere

### Validazione Dati
- ✅ **Validazione proattiva**: Se dato utente sembra scorretto, evidenzialo immediatamente
- ✅ **Suggerimenti concreti**: Proponi valori alternativi sensati
- ✅ **Conferma esplicita**: Per valori incongrui, richiedi conferma prima di procedere
- ✅ **Educazione utente**: Spiega perché un valore potrebbe essere problematico

Esempi validazioni critiche:
- COGS > Prezzo vendita → margine negativo
- LTV/CAC < 1 → insostenibile economicamente
- Burn rate > runway → fallimento pre-break-even
- Salari troppo bassi/alti per ruolo e paese
- Growth rate irrealistico (>20% mensile senza giustificazione)

### Ipotesi e Trasparenza
- ✅ Ogni ipotesi deve avere fonte/giustificazione chiara
- ✅ Distinguere dati certi vs ipotizzati nel Markdown
- ✅ Confidence level per ipotesi (Alta/Media/Bassa)
- ✅ Documentare assunzioni chiave che impattano risultati

### Lingua
- ✅ Segui lingua del brief/documenti utente
- ✅ Coerenza tra Excel labels e Markdown

---

## Gestione Errori

### Input Phase
- Documenti mancanti → chiedi come fornire
- Documenti ambigui → chiedi clarificazione specifica
- Dati contrastanti tra documenti → evidenzia e chiedi priorità

### Excel Generation
- Template non trovato → verifica path skill
- Script error → mostra errore completo, proponi fix
- Formula errors dopo recalc → analizza error_summary, fixa e riprova

### Validation Phase
- Utente conferma dato palesemente errato → procedi ma documenta rischio nel Markdown
- Dati insufficienti per validazione → chiedi info addizionali contestuali

---

## Esempi

Vedi `examples/validation-examples.md` per casi completi di:
- Margine lordo negativo (CRITICAL)
- LTV/CAC borderline (WARNING)
- Growth rate aggressivo (WARNING)
- Runway insufficiente (CRITICAL)
- Ipotesi generate da documenti (Step B)

---

## Checklist Finale (prima di consegnare)

- [ ] Excel apre senza errori
- [ ] `recalc.py` ritorna `total_errors: 0`
- [ ] Tutti i fogli popolati correttamente (Input, Output, Financial Statements)
- [ ] Formule calcolano valori sensati (no #REF!, #DIV/0!, #VALUE!)
- [ ] Markdown contiene:
  - [ ] Executive Summary con key metrics
  - [ ] Tutte le assunzioni documentate con fonte
  - [ ] Analisi finanziaria completa
  - [ ] Scenari e sensitivity analysis
  - [ ] Caveat e limitazioni
- [ ] Ogni ipotesi ha giustificazione chiara
- [ ] Warning per dati incongrui documentati
- [ ] Utente ha confermato tutti i dati critici
