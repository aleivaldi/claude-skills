# Generazione Business Model Canvas (SINTETICO)

## Obiettivo

Creare **business-model-canvas.md** come documento **sintetico, visuale e professionale** che:
- ⚠️ **SINTETICO** - 150-300 righe totali (BMC tradizionale sta in 1-2 pagine)
- **Bullet points** - NO paragrafi narrativi lunghi
- **3-7 punti chiave per blocco** - Solo l'essenziale
- **Formato tabellare** dove appropriato (Revenue, Channels, Partners, Cost)
- **Contiene i 9 blocchi del BMC** compilati con dati concreti dal brief
- È **condivisibile con stakeholder/investitori** con formattazione professionale
- È **realistico per fase MVP** - Revenue e cost coerenti con scope

⚠️ **SE SUPERI 300 RIGHE → STAI SBAGLIANDO**. Sintetizza.

---

## Overview del Processo

**Generazione BMC in 9 passi**:
1. **Passo 1** - Leggere input files (brief-structured.md + competitor-analysis.md opzionale)
2. **Passo 2** - Generare business-model-canvas.md (**150-300 righe**, 9 blocchi SINTETICI)
3. **Passo 2.1** - Review Anti-Verbosità business-model-canvas.md
4. **Passo 2.2** - Generare business-model-canvas-visual.md (~100-150 righe, layout tabellare)
5. **Passo 3** - Tracciare modifiche internamente (per output chat)
6. **Passo 4** - Output riepilogo all'utente in chat (entrambi i file)
7. **Passo 5** - Chiedere conferma con AskUserQuestion
8. **Passo 6** - Gestire modifiche richieste (aggiorna entrambi i file)
9. **Passo 7-8** - Loop fino ad approvazione e annunciare completamento

---

## Tools da Usare

1. **Read** tool → leggere brief-structured.md (obbligatorio) e competitor-analysis.md (opzionale)
2. **Write** tool → creare business-model-canvas.md e business-model-canvas-visual.md (prima volta)
3. **Edit** tool → modificare entrambi i file (iterazioni successive, SEMPRE Read prima)
4. **AskUserQuestion** tool → conferme e richiesta modifiche

---

## Processo Dettagliato

### Passo 1: Leggere Input Files

Usa **Read tool** per leggere i file di input:

1. **brief-structured.md** (obbligatorio):
   - Se non esiste: Blocca e chiedi utente di crearlo con skill `generating-structured-brief`

2. **competitor-analysis.md** (opzionale):
   - Verifica esistenza prima di Read
   - Se non esiste: Procedi senza, non bloccare

**Estrai informazioni chiave** (per poi SINTETIZZARE):
- **Dal brief**:
  - Problema e utenti target → Customer Segments (SINTETIZZA in 1-2 segmenti, 1 riga ciascuno)
  - Obiettivi e funzionalità → Value Propositions (SINTETIZZA in 3-5 bullet)
  - Scope MVP → Revenue Streams e Cost Structure (SOLO categorie aggregate)
  - Vincoli → Key Resources e Key Partners (SOLO i critici)

- **Da competitor-analysis** (se presente):
  - Pricing competitor → Revenue Streams (per benchmark)
  - Differenziatori → Value Propositions (1-2 punti chiave)

⚠️ **MINDSET**: Non copiare tutto dal brief → **Sintetizza drasticamente**. Se brief ha 20 righe su un blocco → riduci a 3-5 punti chiave.

---

### Passo 2: Generare business-model-canvas.md

Usa **Write tool** per creare business-model-canvas.md come **documento SINTETICO**.

#### REGOLE CRITICHE (⚠️ MOLTO IMPORTANTE)

**✅ FARE**:
- **150-300 righe TOTALI** (target: ~200 righe)
- **3-7 punti per blocco** - Solo essenziale
- **Bullet points** - NO paragrafi narrativi
- **Tabelle markdown** per: Revenue Streams, Channels, Key Partners, Cost Structure
- **Dati concreti** dal brief (NO generici)
- **1 riga per bullet** - Max 2 righe se necessario
- **Emoji nei titoli** (opzionale, per visual appeal)

**❌ NON FARE**:
- ❌ **NO paragrafi lunghi narrativi**
- ❌ **NO più di 7 punti per blocco**
- ❌ **NO dettagli eccessivi** - BMC è executive summary
- ❌ **NO markers** tipo [CONFERMATO], [AGGIUNTO]
- ❌ **NO riferimenti** a brief.md o competitor-analysis.md
- ❌ **NO sezioni "Appendix" o "Details"**

#### Struttura business-model-canvas.md SINTETICA

**Vedi template completo**: `templates/bmc-template.md`

**Target righe per blocco** (totale 150-300):

| Blocco | Righe | Formato |
|--------|-------|---------|
| Customer Segments | 5-10 | Bullet (1-2 segmenti) |
| Value Propositions | 10-20 | Bullet (3-5 per segmento) |
| Channels | 10-15 | **Tabella** (4 fasi) |
| Customer Relationships | 8-12 | Bullet (acquisizione, retention, upsell) |
| Revenue Streams | 15-25 | **Tabella** pricing + proiezione |
| Key Resources | 8-12 | Bullet (team, tech, budget) |
| Key Activities | 8-12 | Bullet (3 categorie) |
| Key Partners | 10-15 | **Tabella** (3-5 partner) |
| Cost Structure | 15-25 | **Tabella** costi + break-even |
| Key Metrics | 8-12 | **Tabella** (4-6 metriche) |
| Assumptions & Risks | 10-15 | Bullet (2-3 ciascuno) |

**TOTAL**: ~120-180 righe core + spazi = **150-300 righe totali**

---

### Passo 2 - Linee Guida SINTETICHE per Blocco

#### 1. Customer Segments (5-10 righe)

**Formato**:
```
- **[Segmento 1]**: [1 riga descrizione + dimensione mercato]
- **[Segmento 2]**: [1 riga descrizione + dimensione mercato] (opzionale)
```

**Esempio**:
```
- **PMI Retail 10-50 dip**: Processo inventario manuale (2-3h/giorno), ~15k in Italia
```

**Fonte**: Sezione "Utenti" da brief → sintetizza in 1 riga per segmento

---

#### 2. Value Propositions (10-20 righe)

**Formato**:
```
**Per [Segmento]**:
- [Beneficio 1 con metrica]
- [Beneficio 2]
- [Differenziatore vs alternative]
```

**Esempio**:
```
**Per PMI Retail**:
- 70% riduzione tempo gestione inventario (da 2-3h/giorno a 30min)
- Alert predittivi stock-out evitano perdita vendite
- 10x più economico di soluzioni enterprise (€15 vs €200/mese)
```

**Fonte**: Sezioni "Problema", "Obiettivi", "Funzionalità" da brief → estrai 3-5 benefici chiave con metriche

---

#### 3. Channels (10-15 righe con TABELLA)

**Formato TABELLA**:
```
| Fase | Canali |
|------|--------|
| **Awareness** | [Canale 1], [Canale 2], [Canale 3] |
| **Acquisition** | [Processo breve] |
| **Distribution** | [Come ricevono prodotto] |
| **Support** | [Come ricevono aiuto] |
```

**Esempio**:
```
| Fase | Canali |
|------|--------|
| **Awareness** | Google Ads, LinkedIn Ads, Content SEO |
| **Acquisition** | Landing → Free trial 14gg → Self-signup |
| **Distribution** | Web app responsive (mobile-first) |
| **Support** | Email <24h + Knowledge base self-service |
```

**Fonte**: Dedotto da Customer Segments + defaults.md per MVP typical

---

#### 4. Customer Relationships (8-12 righe)

**Formato**:
```
- **Acquisizione**: [strategia 1 riga]
- **Retention**: [strategia 1 riga]
- **Upsell**: [strategia 1 riga]
```

**Esempio**:
```
- **Acquisizione**: Free trial 14gg no CC + onboarding automatico + welcome email sequence
- **Retention**: Email support <24h + product updates mensili + usage analytics dashboard
- **Upsell**: Usage prompts 80% limite + annual discount -20% + feature discovery
```

**Fonte**: Dedotto da Value Prop + defaults.md per SaaS MVP typical

---

#### 5. Revenue Streams (15-25 righe con TABELLA + proiezione)

**Formato TABELLA**:
```
| Piano | Prezzo | Target | Features chiave |
|-------|--------|--------|-----------------|
| Free | €0 | Acquisizione | [Limitate] |
| [Piano 1] | €X/mese | [Segmento] | [Principali] |
| [Piano 2] | €Y/mese | [Segmento] | [Avanzate] |

**Proiezione MVP** (primi 6 mesi):
- Mese 3-4: €X MRR ([N] clienti)
- Mese 5-6: €Y MRR ([N] clienti)
- Break-even: €Z MRR a ~[N] mesi
```

**Fonte**: Dedotto da Value Prop + competitor-analysis (se presente) + defaults.md pricing ranges

---

#### 6. Key Resources (8-12 righe)

**Formato**:
```
- **Team**: [Ruolo 1], [Ruolo 2], [Ruolo 3]
- **Tech**: [Stack essenziale 1 riga]
- **Budget**: €X per [N] mesi MVP
```

**Esempio**:
```
- **Team**: 1 Full-stack Dev, 1 Product Designer, Founder (sweat equity)
- **Tech**: React + Next.js, PostgreSQL (Supabase), Vercel hosting
- **Budget**: €40k per 6 mesi MVP
```

**Fonte**: Sezione "Vincoli" brief + defaults.md per team/stack typical MVP

---

#### 7. Key Activities (8-12 righe)

**Formato**:
```
- **Production** (X%): [Att.1], [Att.2], [Att.3]
- **Problem Solving** (X%): [Att.1], [Att.2]
- **Customer Dev** (X%): [Att.1], [Att.2]
```

**Esempio**:
```
- **Production** (50%): Sviluppo MVP, Design UI/UX, Testing/QA
- **Problem Solving** (30%): Support email <24h, Product iteration, Bug fixing
- **Customer Dev** (20%): Interviste 2-3/week, Content marketing, Newsletter
```

**Fonte**: Dedotto da Value Prop e Key Resources

---

#### 8. Key Partners (10-15 righe con TABELLA)

**Formato TABELLA**:
```
| Partner | Cosa forniscono | Perché critici |
|---------|----------------|----------------|
| [Partner 1] | [Servizio] | [Rationale breve] |
| [Partner 2] | [Servizio] | [Rationale breve] |
| [Partner 3] | [Servizio] | [Rationale breve] |
```

**Esempio**:
```
| Partner | Cosa forniscono | Perché critici |
|---------|----------------|----------------|
| Stripe | Payment processing + subscriptions | No PCI compliance, billing automatico |
| SendGrid | Email transazionali + marketing | Deliverability >95%, scale senza ops |
| Vercel | Hosting + CDN + CI/CD | Zero-config deploy, 99.9% uptime |
```

**Fonte**: Dedotto da Key Activities + defaults.md typical SaaS partners

---

#### 9. Cost Structure (15-25 righe con TABELLA)

**Formato TABELLA**:
```
| Categoria | Costo/mese | Note |
|-----------|------------|------|
| **Team** | €X | [Composizione] |
| **Infra/Tools** | €Y | [Dettaglio] |
| **Marketing** | €Z | [Canali] |
| **TOTAL** | **€T** | **Break-even: €T MRR = [N] clienti** |

**Timeframe break-even**: [N]-[N] mesi post-MVP
```

**Fonte**: Key Resources + defaults.md cost ranges MVP

---

### Passo 2.1: Review Anti-Verbosità (CRITICO)

**Prima di procedere**, conta le righe del documento generato:

**Checklist**:
- [ ] Documento è 150-300 righe totali? (Se >300 → SINTETIZZA)
- [ ] Ogni blocco ha 3-7 punti chiave? (Se >7 → RIDUCI)
- [ ] Bullet points, NO paragrafi narrativi? (Se paragrafi → CONVERTI a bullet)
- [ ] Tabelle usate dove appropriato? (Revenue, Channels, Partners, Cost)
- [ ] Ogni punto è 1 riga (max 2)? (Se >2 righe → ACCORCIA)

**Se qualsiasi check è ❌**: Usa Edit tool per correggere **PRIMA** di procedere al Passo 2.2.

---

### Passo 2.2: Generare business-model-canvas-visual.md

Usa **Write tool** per creare business-model-canvas-visual.md come **versione tabellare visuale**.

**Obiettivo**: Layout canvas canonico in tabella markdown, ultra-sintetico per pitch deck.

#### REGOLE CRITICHE

**✅ FARE**:
- **~100-150 righe TOTALI** (target: ~120 righe)
- **3-5 punti per blocco** - Ultra-essenziale
- **Tabella unica** con layout classico BMC (vedi template)
- **Layout canonico**: Key Partners sx, Customer Segments dx
- **Copy/paste ready** per slide pitch deck

**❌ NON FARE**:
- ❌ **NO più di 5 punti per blocco** (versione visual è ultra-sintetica)
- ❌ **NO bullet lunghi** - Max 1 riga (80 caratteri)
- ❌ **NO paragrafi** - Solo bullet compatti

**Template**: Vedi `templates/bmc-visual-template.md` per struttura completa.

**Come generare**:
1. Usa dati da business-model-canvas.md appena creato
2. **Sintetizza ulteriormente**: Se blocco ha 7 punti nel file completo → scegli i 3-5 PIÙ IMPORTANTI per visual
3. **Riassumi bullet**: Se bullet è 2 righe → riduci a 1 riga
4. **Mantieni layout tabellare** secondo schema canonico BMC

**Esempio layout tabella principale**:
```markdown
| Key Partners | Key Activities | Value Propositions | Customer Relationships |
|--------------|----------------|-------------------|------------------------|
| [3-5 bullet] | [3-5 bullet]   | [3-5 bullet]      | [3-5 bullet]           |
|              | **Key Resources** |                |                        |
|              | [3-5 bullet]   |                   | **Channels**           |
|              |                |                   | [3-5 bullet]           |
```

**Dopo generazione**: Verifica che file visual sia ~100-150 righe. Se >150 → sintetizza ulteriormente.

---

### Passo 3: Tracciare Modifiche Internamente

Mentre scrivi business-model-canvas.md, **traccia mentalmente** (per il tuo output in chat):

- **Dal brief**: Quali dati vengono direttamente da brief-structured.md
- **Da competitor**: Quali insights da competitor-analysis.md (se presente)
- **Assunto dalla skill**: Quali scelte da defaults.md (channels, pricing ranges, costs)

⚠️ **IMPORTANTE**: Queste info vanno comunicate SOLO in chat, NON nel documento BMC.

---

### Passo 4: Output all'Utente in Chat

Dopo aver creato **entrambi i file**, comunica all'utente in chat (NON nei file):

```markdown
# Business Model Canvas Creato (2 formati)

Ho creato **2 file complementari** per il Business Model Canvas:

## 1. business-model-canvas.md (~[N] righe)
**Versione completa sintetica** - Documento di lavoro

- **Formato**: Bullet points + tabelle markdown
- **Lunghezza**: [N] righe (target 150-300)
- **Dettaglio**: 3-7 punti per blocco
- **Uso**: Documento stand-alone, allineamento team, planning

## 2. business-model-canvas-visual.md (~[N] righe)
**Versione tabellare visuale** - Layout canvas canonico

- **Formato**: Tabella unica con disposizione classica BMC
- **Lunghezza**: [N] righe (target 100-150)
- **Dettaglio**: 3-5 punti essenziali per blocco
- **Uso**: Copy/paste pitch deck, workshop, presentazioni

## Highlights

**Revenue Model**:
- [Descrizione breve - es. "Freemium + 2 tier subscription (€15/€45)"]
- Break-even: ~[N] mesi con [N] clienti

**Cost Structure**:
- €[X]/mese per MVP (team + infra + marketing)

**Differenziatori** *(se competitor-analysis presente)*:
- [Differenziatore 1]
- [Differenziatore 2]

## Assunzioni fatte per MVP (da defaults.md)

[Solo 2-3 assunzioni più significative]
- **[Aspetto X]**: Assunto [cosa]. Rationale: [perché]

## Prossimo passo

Per favore rivedi **business-model-canvas.md**.
È un documento sintetico (1-2 pagine) condivisibile con stakeholder/investitori.

Il Business Model Canvas riflette correttamente il progetto?
```

---

### Passo 5: Chiedere Conferma e Metodo di Feedback

Usa **AskUserQuestion** tool per chiedere:

```
Domanda: "Il Business Model Canvas riflette correttamente il progetto? Come vuoi procedere?"

Opzioni:
- "Sì, è perfetto così"
- "Voglio modificarlo direttamente nel file (Metodo A)"
- "Voglio aggiungere commenti inline da discutere (Metodo B)"
- "Voglio dare feedback testuale in chat (Metodo C)"
```

**In base alla risposta**:
- **"Sì, è perfetto così"** → Procedi a Passo 8 (Annunciare completamento)
- **Metodo A, B, o C** → Procedi a Passo 6 con la sottosezione corrispondente

---

### Passo 6: Gestire Modifiche Richieste

(Stesso processo di generating-structured-brief - 3 metodi supportati)

#### Passo 6A: Gestire Modifica Diretta del File

1. Comunica: "Modifica `business-model-canvas.md` nel tuo editor. Quando hai finito, dimmi 'rivedi'."
2. Aspetta conferma utente
3. Read file aggiornato
4. Mostra riepilogo modifiche rilevate
5. AskUserQuestion per conferma finale

#### Passo 6B: Gestire Commenti Inline

1. Comunica: "Aggiungi marker `<!-- FEEDBACK: ... -->` dove hai dubbi. Quando hai finito, dimmi 'leggi i feedback'."
2. Aspetta conferma utente
3. Read file, parsa tutti marker
4. Per ogni feedback: discuti, applica Edit, rimuovi marker
5. Mostra riepilogo modifiche
6. AskUserQuestion per conferma finale

#### Passo 6C: Gestire Feedback Testuale in Chat

1. Comunica: "Dimmi quali modifiche vuoi. Es: 'Sezione Revenue: cambia €19 in €15'"
2. Ascolta modifiche in chat
3. Per ogni modifica:
   - Read business-model-canvas.md → Edit → mostra diff
   - Read business-model-canvas-visual.md → Edit per riflettere modifiche → mostra diff
4. AskUserQuestion per conferma

**Nota**: SEMPRE Read prima di ogni Edit. **SEMPRE aggiorna ENTRAMBI i file** quando si fanno modifiche.

---

### Passo 7: Loop Fino ad Approvazione

Continua ciclo Passo 5-6 fino a:
- Utente conferma che business-model-canvas.md è corretto
- Utente approva esplicitamente

---

### Passo 8: Annunciare Completamento Skill

Quando utente approva:

```markdown
# Business Model Canvas Completato ✓

Ottimo! I 2 file Business Model Canvas sono completi e approvati:

## File generati

1. **business-model-canvas.md** (~[N] righe)
   - Versione completa sintetica per lavoro quotidiano

2. **business-model-canvas-visual.md** (~[N] righe)
   - Versione tabellare visuale per pitch/presentazioni

Questa skill ha terminato il suo compito. Hai ora un BMC completo in 2 formati complementari, professionali e condivisibili.

## Usi

- **business-model-canvas.md**: Documento di lavoro, allineamento team, planning
- **business-model-canvas-visual.md**: Copy/paste in pitch deck, workshop, presentazioni stakeholder

## Prossimi passi (opzionali)

Se desideri **documento di requisiti tecnici** (requirements.md) con architettura, elementi sistema, sottoprogetti:

**`generating-requirements-document`**

Questa skill prenderà brief-structured.md come input e genererà un requirements.md completo.
```

---

## Checklist: Generazione BMC SINTETICO Completata

Prima di considerare generazione completa, verifica:

### Documenti BMC Creati
- [ ] **business-model-canvas.md** creato con Write tool
  - [ ] **150-300 righe totali** (SE >300 → ERRORE, troppo lungo)
  - [ ] **3-7 punti per blocco** (SE >7 → ERRORE, troppo dettaglio)
  - [ ] **Bullet points** usati (NO paragrafi narrativi lunghi)
  - [ ] **Tabelle markdown** per: Revenue, Channels, Partners, Cost
  - [ ] Tutti i 9 blocchi presenti

- [ ] **business-model-canvas-visual.md** creato con Write tool
  - [ ] **~100-150 righe totali** (SE >150 → ERRORE, troppo lungo)
  - [ ] **3-5 punti per blocco** (SE >5 → ERRORE, versione visual è ultra-sintetica)
  - [ ] **Layout tabellare** con disposizione canvas canonico
  - [ ] Tutti i 9 blocchi presenti nella tabella

- [ ] **Entrambi i file**:
  - [ ] Dati concreti dal brief (NO generici)
  - [ ] Tono professionale (NO markers, NO riferimenti processo)

### Qualità Contenuto
- [ ] Customer Segments: 1-2 segmenti, 1 riga ciascuno
- [ ] Value Props: 3-5 bullet per segmento con metriche
- [ ] Channels: Tabella 4 fasi concisa
- [ ] Revenue: Tabella pricing + proiezione 3-5 righe
- [ ] Cost: Tabella breakdown + break-even
- [ ] Tutti blocchi realistici per MVP

### Processo Seguito
- [ ] brief-structured.md letto
- [ ] competitor-analysis.md letto (se presente) o verificato assente
- [ ] Defaults.md usato per scelte (comunicato in chat, NO nel doc)
- [ ] Output riepilogo fornito in chat
- [ ] AskUserQuestion usato per conferma
- [ ] Utente ha approvato

---

## Errori Comuni da Evitare

### ❌ Errore 1: Documento Troppo Lungo (>300 righe)

**Problema**: BMC dovrebbe stare in 1-2 pagine, non 10 pagine.

**Fix**:
- Riduci ogni blocco a 3-7 punti essenziali
- Elimina dettagli non critici
- Aggrega informazioni simili
- Usa tabelle per condensare (es. pricing tiers)

### ❌ Errore 2: Paragrafi Narrativi Lunghi

**Problema**: BMC è strumento visuale, non essay.

**Sbagliato**:
```
Il nostro segmento di clienti primario consiste in piccole e medie imprese operanti nel settore del retail fisico, tipicamente con una dimensione organizzativa compresa tra 10 e 50 dipendenti...
```

**Corretto**:
```
- **PMI Retail 10-50 dip**: Processo inventario manuale (2-3h/giorno), ~15k in Italia
```

### ❌ Errore 3: Troppi Punti per Blocco (>7)

**Problema**: Se hai 10+ punti, non stai sintetizzando.

**Fix**: Seleziona i 3-5 punti **PIÙ IMPORTANTI** e scarta il resto.

### ❌ Errore 4: Dettagli Eccessivi

**Problema**: BMC è executive summary, non requirements.md.

**Fix**: Se utente vuole dettagli → suggerisci brief-structured.md o requirements.md, **NO BMC lungo**.

---

## Test Finale

Prima di considerare BMC completo, fai questo test mentale:

1. ✅ **BMC può essere presentato in pitch deck?** (max 1-2 slide)
2. ✅ **BMC può essere stampato in 1-2 pagine A4 leggibili?**
3. ✅ **Stakeholder capisce business model in 5-10 minuti?**
4. ✅ **BMC è <= 300 righe totali?**

Se anche solo UNO è ❌ → **troppo lungo, sintetizza ulteriormente**.

---

## Riferimento a defaults.md

⚠️ **Usa `defaults.md` per scelte pragmatiche, comunica in CHAT, NON scrivere tutto nel documento**

Consulta `defaults.md` per:
- Revenue models typical (freemium, subscription, usage-based)
- Pricing ranges benchmark (B2B SaaS, B2C, marketplace)
- Channels MVP typical (web, marketing digital, direct sales)
- Cost structure MVP ranges (team, infra, marketing)
- Key partners typical SaaS (Stripe, SendGrid, hosting)

**Come usare defaults.md**:
1. Usa per prendere decisioni dove brief non specifica
2. Comunica scelte nella sezione "Assunzioni fatte per MVP" nell'output chat (Passo 4)
3. **NON scriverle** come dettagli nel BMC (BMC è sintetico, solo risultati)
4. **NON copiare** interi paragrafi da defaults.md nel BMC

---

## Riepilogo Tool

1. **Read tool**: brief-structured.md + competitor-analysis.md (opzionale)
2. **Write tool**:
   - business-model-canvas.md (prima volta, **150-300 righe**)
   - business-model-canvas-visual.md (prima volta, **~100-150 righe**)
3. **Edit tool**: Modifiche successive a ENTRAMBI i file (SEMPRE Read prima)
4. **AskUserQuestion tool**: Conferma e richiesta modifiche

**NON usare**:
- ❌ Write su file esistente (usa Edit)
- ❌ Edit senza Read prima
- ❌ Modificare solo un file (aggiorna SEMPRE entrambi per consistenza)
- ❌ Procedere senza conferma utente
