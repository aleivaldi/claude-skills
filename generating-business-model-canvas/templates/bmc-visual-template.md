# Template: Business Model Canvas - Versione Tabellare Visuale

Questo template definisce il **layout tabellare visuale** classico del Business Model Canvas, da generare come **business-model-canvas-visual.md**.

## Caratteristiche

- **Layout tabellare** con i 9 blocchi disposti secondo lo schema canonico BMC
- **Ultra-sintetico** - Solo punti chiave (3-5 bullet per blocco)
- **Copy/paste ready** per slide deck
- **Visivamente allineato** al canvas originale di Strategyzer

---

## Layout Classico BMC

Lo schema canonico del Business Model Canvas è:

```
+----------------------+----------------------+----------------------+----------------------+
|                      |                      |                      |                      |
|   KEY PARTNERS       |   KEY ACTIVITIES     |   VALUE              |   CUSTOMER           |
|                      |                      |   PROPOSITIONS       |   RELATIONSHIPS      |
|                      +----------------------+                      +----------------------+
|                      |                      |                      |                      |
|                      |   KEY RESOURCES      |                      |   CHANNELS           |
|                      |                      |                      |                      |
+----------------------+----------------------+----------------------+----------------------+
|                                             |                                             |
|          COST STRUCTURE                     |          REVENUE STREAMS                    |
|                                             |                                             |
+----------------------+----------------------+----------------------+----------------------+
                                              |                                             |
                                              |       CUSTOMER SEGMENTS                     |
                                              |                                             |
                                              +----------------------+----------------------+
```

**Nota**: Customer Segments è posizionato a destra, come nel canvas originale.

---

## Struttura business-model-canvas-visual.md

```markdown
# [NOME PROGETTO] - Business Model Canvas

> [1 frase riassuntiva del business model]

---

## 🎯 Canvas Visuale

| Key Partners | Key Activities | Value Propositions | Customer Relationships |
|--------------|----------------|-------------------|------------------------|
| **🤝 Con chi collaboriamo** | **⚙️ Cosa facciamo** | **💎 Valore unico** | **🤝 Come interagiamo** |
| | | | |
| • [Partner 1] | • [Attività 1] | **Per [Segmento]:** | • **Acquisizione**: [strategia] |
| • [Partner 2] | • [Attività 2] | • [Beneficio 1] | • **Retention**: [strategia] |
| • [Partner 3] | • [Attività 3] | • [Beneficio 2] | • **Upsell**: [strategia] |
| | | • [Differenziatore] | |
| | **Key Resources** | | **Channels** |
| | **🛠️ Di cosa abbiamo bisogno** | | **📢 Come raggiungiamo** |
| | | | |
| | • Team: [composizione] | | • **Awareness**: [canali] |
| | • Tech: [stack] | | • **Acquisition**: [processo] |
| | • Budget: €X per N mesi | | • **Distribution**: [come] |
| | | | • **Support**: [come] |

| Cost Structure | Revenue Streams |
|----------------|-----------------|
| **💸 Costi principali** | **💰 Come guadagniamo** |
| | |
| • Team: €X/mese | **Pricing Model:** |
| • Infra/Tools: €Y/mese | • Free: €0 ([features]) |
| • Marketing: €Z/mese | • [Piano 1]: €X/mese ([features]) |
| **TOTAL: €T/mese** | • [Piano 2]: €Y/mese ([features]) |
| **Break-even: €T MRR a ~N mesi** | **Proiezione MVP: €X MRR a 6 mesi** |

| Customer Segments |
|-------------------|
| **🎯 Chi sono i clienti** |
| |
| • **[Segmento 1]**: [descrizione 1 riga, dimensione mercato] |
| • **[Segmento 2]**: [descrizione 1 riga, dimensione mercato] *(se presente)* |

---

## 📊 Key Metrics

| Metrica | Target MVP |
|---------|------------|
| **CAC** | €X |
| **LTV/CAC** | >3:1 |
| **Churn** | <X% |
| **Conversion** | X-Y% |

---

## ⚠️ Assumptions & Risks

**Assumptions**: [2-3 chiave]
• [Assumption 1]
• [Assumption 2]

**Risks**: [2-3 chiave]
• [Risk 1] → Mitigation: [soluzione]
• [Risk 2] → Mitigation: [soluzione]

---

*Versione tabellare visuale del Business Model Canvas*
```

---

## Linee Guida per Compilazione

### ✅ FARE

- **3-5 bullet per blocco** - Ultra-sintetico
- **Allineamento visuale** - Mantieni struttura tabellare pulita
- **Emoji nei titoli** - Per visual appeal (opzionale)
- **Dati concreti** - No generici
- **1 riga per bullet** - Massima sintesi

### ❌ NON FARE

- ❌ **NO più di 5 punti** per blocco nella tabella
- ❌ **NO bullet lunghi** - Max 1 riga (80 caratteri)
- ❌ **NO paragrafi narrativi** - Solo bullet
- ❌ **NO dettagli** - Questa è versione ultra-sintetica per visualizzazione

---

## Differenze con business-model-canvas.md

| Aspetto | business-model-canvas.md | business-model-canvas-visual.md |
|---------|--------------------------|----------------------------------|
| **Formato** | Bullet + tabelle separate per sezioni | Una grande tabella con layout canvas |
| **Dettaglio** | 150-300 righe, 3-7 punti per blocco | ~100-150 righe, 3-5 punti per blocco |
| **Uso** | Documento stand-alone leggibile | Visual reference per pitch/workshop |
| **Layout** | Lineare, sezioni sequenziali | Layout canvas canonico (partner sx, customer dx) |

**Entrambi i file sono generati** dalla skill:
1. `business-model-canvas.md` - Versione completa sintetica (150-300 righe)
2. `business-model-canvas-visual.md` - Versione tabellare visuale ultra-sintetica (~100-150 righe)

---

## Esempio Compilato

```markdown
# Karaoke Queue Manager - Business Model Canvas

> Sistema self-service per gestione code e prenotazioni brani nei locali karaoke

---

## 🎯 Canvas Visuale

| Key Partners | Key Activities | Value Propositions | Customer Relationships |
|--------------|----------------|-------------------|------------------------|
| **🤝 Con chi collaboriamo** | **⚙️ Cosa facciamo** | **💎 Valore unico** | **🤝 Come interagiamo** |
| | | | |
| • Stripe (pagamenti) | • Sviluppo MVP | **Per Gestori Locali:** | • **Acquisizione**: Free trial 14gg |
| • SendGrid (email) | • Support <24h | • 70% riduzione tempo gestione code | • **Retention**: Email support |
| • Vercel (hosting) | • Product iteration | • Riduzione conflitti/lamentele | • **Upsell**: Usage prompts |
| | | • 10x più economico vs custom | |
| | **Key Resources** | | **Channels** |
| | **🛠️ Di cosa abbiamo bisogno** | | **📢 Come raggiungiamo** |
| | | | |
| | • Team: 1 dev, 1 designer | | • **Awareness**: Google Ads, LinkedIn |
| | • Tech: React, PostgreSQL, Vercel | | • **Acquisition**: Landing → Trial → Signup |
| | • Budget: €40k per 6 mesi | | • **Distribution**: Web app responsive |
| | | | • **Support**: Email <24h, KB |

| Cost Structure | Revenue Streams |
|----------------|-----------------|
| **💸 Costi principali** | **💰 Come guadagniamo** |
| | |
| • Team: €5k/mese | **Pricing Model:** |
| • Infra/Tools: €500/mese | • Free: €0 (1 locale, 10 clienti/sera) |
| • Marketing: €1k/mese | • Basic: €15/mese (2 locali, 50 clienti) |
| **TOTAL: €6.5k/mese** | • Pro: €45/mese (unlimited) |
| **Break-even: €6.5k MRR a ~12 mesi** | **Proiezione MVP: €1.5k MRR a 6 mesi** |

| Customer Segments |
|-------------------|
| **🎯 Chi sono i clienti** |
| |
| • **Gestori Karaoke 10-50 clienti/sera**: Gestione code manuale, frustrazione clienti, ~2k in Italia |
| • **Clienti Karaoke**: Prenotazione brani più facile, no attese inutili |

---

## 📊 Key Metrics

| Metrica | Target MVP |
|---------|------------|
| **CAC** | €50 |
| **LTV/CAC** | >3:1 |
| **Churn** | <5% |
| **Conversion** | 10-15% |

---

## ⚠️ Assumptions & Risks

**Assumptions**:
• Conversione 10% free → paid (benchmark SaaS)
• Gestori accettano self-service clienti

**Risks**:
• Competitor abbassa prezzo → Mitigation: Differenziazione UX, non prezzo
• Adozione lenta settore tradizionale → Mitigation: Free tier generoso, testimonials

---

*Versione tabellare visuale del Business Model Canvas*
```

---

## Note Implementazione

### Generazione delle Tabelle

Usa markdown tables con `|` per separare celle:

```markdown
| Colonna 1 | Colonna 2 | Colonna 3 |
|-----------|-----------|-----------|
| Contenuto | Contenuto | Contenuto |
```

### Formatting Tips

1. **Titoli sezioni con emoji** - Aiutano visual identification
2. **Bold per categorie** - Es. "**Per [Segmento]:**"
3. **Bullet compatti** - Max 1 riga per bullet
4. **Allineamento** - Mantieni celle bilanciate per leggibilità

### Quando Generare

La versione visuale viene generata **insieme** alla versione completa:
1. Prima genera `business-model-canvas.md` (completo)
2. Poi genera `business-model-canvas-visual.md` (visuale) riassumendo il primo
3. Output entrambi i file all'utente

---

## Test Qualità

Prima di considerare versione visuale completa:

- [ ] Layout tabellare mantiene disposizione canvas canonico
- [ ] Ogni blocco ha 3-5 punti (NO più di 5)
- [ ] Ogni bullet è 1 riga (max 80 caratteri)
- [ ] Documento totale è ~100-150 righe
- [ ] Tabelle sono bilanciate (celle non troppo sbilanciate)
- [ ] File può essere copy/paste in slide pitch deck

Se qualsiasi check è ❌ → Correggi prima di output all'utente.
