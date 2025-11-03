# Template: Business Model Canvas (SINTETICO)

⚠️ **CRITICO**: Il Business Model Canvas è uno strumento **visuale e sintetico**, NON un documento narrativo lungo.

## Caratteristiche del Documento

Il documento deve essere:
- **SINTETICO** - 150-300 righe totali (BMC tradizionale sta in 1-2 pagine stampate)
- **Bullet points** - NO paragrafi narrativi lunghi
- **3-7 punti chiave per blocco** - Solo l'essenziale
- **Formato tabellare/visuale** - Usa tabelle markdown dove possibile
- **Completo** - Tutti i 9 blocchi compilati
- **Basato su dati concreti** - Dal brief-structured.md, non generici
- **Condivisibile** - Formattazione professionale per stakeholder/investitori

---

## Struttura Business Model Canvas SINTETICA

```markdown
# [NOME PROGETTO] - Business Model Canvas

> [1 frase che riassume il business model]

---

## 🎯 Customer Segments
**Chi sono i nostri clienti?**

- **[Segmento 1]**: [descrizione 1 riga, dimensione mercato]
- **[Segmento 2]**: [descrizione 1 riga, dimensione mercato] *(opzionale)*

---

## 💎 Value Propositions
**Quale valore unico offriamo?**

**Per [Segmento 1]**:
- [Beneficio chiave 1 con metrica - es. "70% riduzione tempo X"]
- [Beneficio chiave 2]
- [Differenziatore vs alternative - es. "10x più economico"]

**Per [Segmento 2]** *(se presente)*:
- [Beneficio chiave]
- [Differenziatore]

---

## 📢 Channels
**Come raggiungiamo e distribuiamo valore?**

| Fase | Canali |
|------|--------|
| **Awareness** | [Canale 1], [Canale 2], [Canale 3] |
| **Acquisition** | [Processo - es. "Landing → Free trial 14gg → Self-signup"] |
| **Distribution** | [Come ricevono prodotto - es. "Web app responsive"] |
| **Support** | [Come ricevono aiuto - es. "Email <24h + Knowledge base"] |

---

## 🤝 Customer Relationships
**Come interagiamo con i clienti?**

- **Acquisizione**: [Strategia chiave - es. "Free trial 14gg no CC + onboarding automatico"]
- **Retention**: [Strategia chiave - es. "Email support <24h + product updates mensili"]
- **Upsell**: [Strategia chiave - es. "Usage prompts + annual discount -20%"]

---

## 💰 Revenue Streams
**Come guadagniamo?**

| Piano | Prezzo | Target | Features chiave |
|-------|--------|--------|-----------------|
| **Free** | €0/mese | Acquisizione | [Feature limitate] |
| **[Piano 1]** | €X/mese | [Segmento] | [Features principali] |
| **[Piano 2]** | €Y/mese | [Segmento] | [Features avanzate] |

**Proiezione MVP** (primi 6 mesi):
- Mese 3-4: €X MRR ([N] clienti)
- Mese 5-6: €Y MRR ([N] clienti)
- Break-even: €Z MRR a ~[N] mesi

---

## 🛠️ Key Resources
**Di cosa abbiamo bisogno?**

- **Team**: [Ruolo 1], [Ruolo 2], [Ruolo 3]
- **Tech**: [Stack chiave - es. "React + Next.js, PostgreSQL, Vercel hosting"]
- **Budget**: €X per [N] mesi MVP

---

## ⚙️ Key Activities
**Cosa facciamo per creare valore?**

- **Production** (50%): [Attività 1], [Attività 2], [Attività 3]
- **Problem Solving** (30%): [Attività 1], [Attività 2]
- **Customer Dev** (20%): [Attività 1], [Attività 2]

---

## 🤝 Key Partners
**Con chi collaboriamo?**

| Partner | Cosa forniscono | Perché critici |
|---------|----------------|----------------|
| **[Partner 1]** | [Servizio] | [Rationale - es. "No ops overhead"] |
| **[Partner 2]** | [Servizio] | [Rationale] |
| **[Partner 3]** | [Servizio] | [Rationale] |

---

## 💸 Cost Structure
**Quali sono i costi principali?**

| Categoria | Costo/mese | Note |
|-----------|------------|------|
| **Team** | €X | [Composizione - es. "1 dev + 1 designer part-time"] |
| **Infra/Tools** | €Y | [Dettaglio - es. "Hosting + SaaS tools"] |
| **Marketing** | €Z | [Canali - es. "Google Ads + LinkedIn"] |
| **TOTAL** | **€T** | **Break-even: €T MRR = [N] clienti** |

**Timeframe break-even**: [N]-[N] mesi post-MVP

---

## 📊 Key Metrics

| Metrica | Target MVP |
|---------|------------|
| **CAC** (Customer Acquisition Cost) | €X per cliente |
| **LTV/CAC** | >3:1 |
| **Churn rate mensile** | <X% |
| **Conversion free → paid** | X-Y% |

---

## ⚠️ Key Assumptions & Risks

**Assumptions**:
- [Assumption 1 critica - es. "Conversion 10% free → paid (benchmark SaaS)"]
- [Assumption 2 critica]

**Risks**:
- [Risk 1 - es. "Competitor abbassa prezzo"] → Mitigation: [soluzione]
- [Risk 2] → Mitigation: [soluzione]

---

*Documento generato da brief-structured.md [+ competitor-analysis.md se presente]*
```

---

## Linee Guida di Scrittura

### ✅ FARE (CRITICO)

- **3-7 punti per blocco** - Solo essenziale, no dettagli eccessivi
- **Bullet points** - NO paragrafi narrativi
- **Tabelle markdown** - Per Revenue Streams, Channels, Key Partners, Cost Structure
- **Metriche quantitative** - "70% riduzione" no "significativa riduzione"
- **Prezzi specifici** - "€15/mese" no "pricing competitivo"
- **1 riga per punto** - Max 2 righe se assolutamente necessario
- **Icone emoji** (opzionale) - Per visual appeal dei titoli sezioni

### ❌ NON FARE (CRITICO)

- ❌ **NO paragrafi narrativi lunghi** - BMC è strumento visuale
- ❌ **NO più di 7 punti per blocco** - Se hai più, sintetizza
- ❌ **NO spiegazioni dettagliate** - Usa brief-structured.md o requirements.md per dettagli
- ❌ **NO sezioni "Appendix" o "Details"** - BMC è executive summary
- ❌ **NO proiezioni revenue oltre 6-12 mesi** - BMC è per MVP, no business plan 5 anni
- ❌ **NO markers** tipo [CONFERMATO], [AGGIUNTO]
- ❌ **NO riferimenti a process**o - No "basato su brief.md"

---

## Esempi di Linguaggio

### ✅ Buono (Sintetico, Bullet, Specifico)

**Customer Segments**:
```
- **PMI Retail 10-50 dip**: Processo inventario manuale (2-3h/giorno), ~15k in Italia
- **E-commerce Small**: 100-1000 SKU, sync multi-canale manuale, ~5k in Italia
```

**Revenue Streams**:
```
| Piano | Prezzo | Target | Features |
|-------|--------|--------|----------|
| Free | €0 | Acquisizione | 10 items, 1 location |
| Starter | €15/mese | PMI 5-10 dip | 100 items, 2 locations, reports |
| Pro | €45/mese | PMI 10-50 dip | Unlimited, API, priority support |

Break-even: €6k MRR (150 Starter + 80 Pro) a ~12 mesi
```

**Key Activities**:
```
- **Production** (50%): Sviluppo MVP, Design UI/UX, Testing/QA
- **Problem Solving** (30%): Support email <24h, Product iteration, Bug fixing
- **Customer Dev** (20%): Interviste 2-3/week, Content marketing, Newsletter
```

### ❌ Sbagliato (Narrativo, Lungo, Vago)

**Customer Segments** (SBAGLIATO):
```
Il nostro segmento di clienti primario consiste in piccole e medie imprese operanti nel settore del retail fisico, tipicamente con una dimensione organizzativa compresa tra 10 e 50 dipendenti. Queste aziende affrontano quotidianamente sfide significative nella gestione del proprio inventario, dovendo dedicare mediamente 2-3 ore al giorno a questa attività attraverso processi manuali che spesso coinvolgono l'utilizzo di fogli di calcolo Excel o addirittura carta e penna...

[CONTINUA PER ALTRE 5 RIGHE...]
```

**Revenue Streams** (SBAGLIATO):
```
Adotteremo un modello di pricing subscription-based con diversi tier pensati per adattarsi alle esigenze di diverse tipologie di clienti. Il nostro piano gratuito permetterà agli utenti di testare il prodotto...

[CONTINUA CON PARAGRAFI LUNGHI...]
```

---

## Target Lunghezza per Blocco

**Guideline righe per blocco** (totale documento 150-300 righe):

| Blocco | Righe target | Note |
|--------|--------------|------|
| **Customer Segments** | 5-10 | 1-2 segmenti, 2-4 righe ciascuno |
| **Value Propositions** | 10-20 | Per segmento: 3-5 bullet points |
| **Channels** | 10-15 | Tabella 4 fasi + brevi note |
| **Customer Relationships** | 8-12 | 3 strategie (acquisizione, retention, upsell) |
| **Revenue Streams** | 15-25 | Tabella pricing + proiezione 3-5 righe |
| **Key Resources** | 8-12 | 3-4 categorie, sintetiche |
| **Key Activities** | 8-12 | 3 categorie, 2-3 attività per categoria |
| **Key Partners** | 10-15 | Tabella con 3-5 partner chiave |
| **Cost Structure** | 15-25 | Tabella costi + break-even 3-5 righe |
| **Key Metrics** | 8-12 | Tabella 4-6 metriche chiave |
| **Assumptions & Risks** | 10-15 | 2-3 assumptions, 2-3 risks |
| **Header + Overview** | 5-10 | Titolo + 1 frase riassuntiva |

**TOTAL**: **~120-180 righe core** + formattazione/spazi = **150-300 righe totali**

⚠️ Se superi 300 righe → **stai sbagliando**, troppo dettaglio. Sintetizza.

---

## Differenze BMC vs Altri Documenti

| Documento | Scopo | Lunghezza | Dettaglio |
|-----------|-------|-----------|-----------|
| **BMC** | Visual strategy, executive summary | 150-300 righe | Bullet points, essenziale |
| **brief-structured.md** | Product vision, scope MVP | 1000-3000 righe | Strutturato, completo |
| **requirements.md** | Technical specs | 4000-15000 righe | Molto dettagliato |

**Gerarchia informazioni**:
1. **BMC** = "What" (cosa facciamo, business model)
2. **Brief** = "Why + What" (perché esiste, cosa risolve, scope)
3. **Requirements** = "How" (come implementiamo, architettura, tech)

**Se utente vuole dettagli** → Suggerisci brief-structured.md o requirements.md, **NO BMC lungo**

---

## Quando Usare Tabelle Markdown

**USA TABELLE** per questi blocchi (migliora leggibilità):

1. **Channels** - 4 fasi in righe
2. **Revenue Streams** - Pricing tiers comparison
3. **Key Partners** - Partner + cosa forniscono + rationale
4. **Cost Structure** - Breakdown costi per categoria
5. **Key Metrics** - Metriche + target values

**NO TABELLE** per questi blocchi (bullet better):

1. **Customer Segments** - Bullet list più chiara
2. **Value Propositions** - Bullet list migliore per benefici
3. **Key Resources** - Bullet list categorie
4. **Key Activities** - Bullet list attività
5. **Customer Relationships** - Bullet list strategie

---

## Note Finali

**Il BMC è uno strumento di SINTESI**, non di dettaglio:
- Usa brief-structured.md come fonte, ma **sintetizza drasticamente**
- Se un blocco dal brief è lungo 20 righe → riduci a 3-5 punti chiave
- Se ci sono 10 funzionalità → seleziona le 3-4 più rilevanti per business model
- Se cost structure è dettagliata → aggrega in categorie principali

**Mindset corretto**:
- ✅ "Quali sono i 3-5 punti **ESSENZIALI** che stakeholder deve sapere?"
- ❌ "Come trasferisco TUTTO dal brief nel BMC?"

**Test finale**:
- ✅ BMC può essere presentato in slide deck? (max 1-2 slide)
- ✅ BMC può essere stampato in 1-2 pagine A4 leggibili?
- ✅ Stakeholder capisce business model in 5-10 minuti lettura?

Se risposta è NO → **troppo lungo, sintetizza ulteriormente**.
