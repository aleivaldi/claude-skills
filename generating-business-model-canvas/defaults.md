# Default Pragmatici per Business Model Canvas MVP

Questo documento fornisce **default sensati** per compilare il Business Model Canvas quando il brief non specifica dettagli sufficienti.

**Principio**: Questi defaults sono **pragmatici per MVP**, non visione enterprise. Focus su semplice, economico, validabile velocemente.

---

## Come Usare Questo File

1. **Consulta questo file** quando brief-structured.md non fornisce dettagli sufficienti per blocco BMC
2. **Usa i defaults** come baseline ragionevole per MVP
3. **Comunica in chat** le assunzioni fatte (non scriverle nel documento BMC)
4. **L'utente può sempre fare override** se ha requisiti diversi

**⚠️ IMPORTANTE**: Questi defaults vanno comunicati solo in chat durante generazione BMC, NON vanno scritti come assunzioni nel documento business-model-canvas.md.

---

## 1. Customer Segments - Defaults

### Se progetto B2B (business-to-business)

**Segmento MVP tipico**:
- **PMI 10-50 dipendenti** (evita enterprise per MVP - cicli vendita lunghi)
- **Mercato verticale specifico** (es. retail, hospitality, manufacturing) no "generic business"
- **Decision maker**: Manager o titolare (evita multi-stakeholder approval chains)
- **Dimensione mercato MVP**: 5.000-50.000 potenziali clienti nella geografia target

**Rationale**: PMI hanno cicli di vendita più brevi, decision making più rapido, budget accessibile per testare MVP.

### Se progetto B2C (business-to-consumer)

**Segmento MVP tipico**:
- **Demografia**: 25-45 anni, comfort con technology
- **Comportamento**: Early adopters, willingness to pay per soluzioni che risolvono pain significativo
- **Geografia MVP**: Mercato locale/regionale (es. Italia) per ridurre complessità
- **Dimensione mercato MVP**: 100k-1M potenziali utenti

**Rationale**: Early adopters 25-45 anni sono tech-savvy, hanno potere d'acquisto, danno feedback costruttivo.

### Se progetto Marketplace (two-sided)

**Lati del marketplace**:
- **Supply side**: Fornitori/venditori/creators (es. PMI, freelance, prosumer)
- **Demand side**: Acquirenti/consumatori (es. PMI, consumers)

**Chicken-egg problem MVP**: Focus prima su supply side (più facile acquisire) o demand side (dipende dal progetto).

**Rationale**: Marketplace richiedono critical mass entrambi lati. MVP validare valore su 1 lato alla volta.

---

## 2. Value Propositions - Defaults

### Struttura value prop MVP

**Problema risolto** (pain reliever):
- **Quantificabile**: "Riduce X da 3 ore a 30 min" no "migliora efficienza"
- **Significativo**: Problema costa >€100/mese o >10 ore/mese
- **Frequente**: Problema si verifica almeno settimanalmente

**Valore offerto** (gain creator):
- **Primario**: Risparmio tempo o denaro (quantificabile)
- **Secondario**: Riduzione stress, migliore qualità, scalabilità

**Differenziatore**:
- Se competitor esistono: **10x miglioramento** su 1 dimensione (prezzo, velocità, facilità)
- Se mercato nuovo: **Alternativa attuale** è processo manuale/inefficiente

**Metrica successo**:
- **ROI cliente**: Payback <3 mesi (idealmente <1 mese)
- **Time to value**: Cliente vede valore in <1 giorno (idealmente <1 ora)

**Rationale**: Value prop MVP deve essere immediatamente chiara e dimostrabile. ROI rapido riduce friction all'acquisto.

---

## 3. Channels - Defaults per MVP

### Awareness (Come ci scoprono)

**B2B MVP**:
- **Google Ads**: Keywords long-tail specifici (€300-500/mese budget test)
- **LinkedIn Ads**: Target decision makers (€200-300/mese budget test)
- **Content marketing**: Blog SEO su pain points target (1-2 post/mese)
- **Direct outreach**: Cold email/LinkedIn (manuale, founder-driven per MVP)

**B2C MVP**:
- **Google Ads**: Keywords problema specifico (€500-1k/mese budget test)
- **Social ads**: Facebook/Instagram se demographics chiara (€300-500/mese test)
- **Content marketing**: Blog + SEO (1-2 post/mese)
- **Referral/word-of-mouth**: Incentivized referrals (post primii clienti)

**Rationale**: Channels paid permettono validazione rapida. Organic (SEO, content) prende mesi ma importante per long-term.

### Acquisition (Come diventano clienti)

**B2B e B2C MVP**:
- **Landing page** con demo video/screenshots + CTA chiara
- **Free trial 14 giorni** senza carta credito (massima riduzione friction)
- **Self-service signup** (no sales call required per MVP - scala meglio)
- **Onboarding automatico** con tutorial in-app + email sequence

**Rationale**: Friction bassa = conversion rate alta. Free trial senza CC converte 2-3x meglio.

### Distribution (Come ricevono valore)

**Default MVP**:
- **Web app responsive** (mobile-first se uso primario su mobile)
- **NO app nativa** iOS/Android per MVP (costo alto, iterate lento)
- **NO desktop app** per MVP (distribuzione complessa)

**Rationale**: Web app permette iterate veloce, deploy istantaneo, reach cross-platform. App native solo post-MVP se traction.

### Support (Come ottengono aiuto)

**MVP B2B/B2C**:
- **Email support**: <24h response time SLA (business days)
- **Knowledge base**: FAQ + tutorial self-service
- **In-app help**: Tooltips + contextual help
- **NO phone support** per MVP (non scala, costoso)
- **NO live chat** per MVP (richiede 24/7 coverage o slow response)

**Rationale**: Email support scala bene per MVP (<100 clienti). Phone/chat solo post-MVP se necessario.

---

## 4. Customer Relationships - Defaults

### Acquisizione

**Default MVP**:
- **Free trial 14 giorni** (benchmark SaaS: 7-30 giorni, 14 giorni sweet spot)
- **No carta credito required** per trial (converte 2-3x meglio)
- **Onboarding automatico**: 5-7 step guided tour
- **Welcome email sequence**: 5 email in 14 giorni (day 1, 3, 7, 10, 14)

### Retention

**Default MVP**:
- **Email support** <24h (sufficiente per MVP)
- **Product updates** mensili via email
- **Usage analytics** per cliente (mostra ROI, aumenta retention)
- **Churn prevention**: Alert quando usage scende <50% avg

### Upsell

**Default MVP**:
- **Usage-based prompts**: Alert quando cliente a 80% limite piano
- **Feature discovery**: Suggerimenti basati su usage patterns
- **Annual plan discount**: -15-20% se passa da mensile ad annuale

**Rationale**: Relationship type per MVP è **self-service + automated** (no high-touch sales). Scala meglio, costi inferiori.

---

## 5. Revenue Streams - Defaults per MVP

### Modello Pricing Raccomandato per MVP

**Default: Freemium + Subscription Tiers**

**Perché Freemium**:
- Riduce friction acquisizione (no risk per cliente testare)
- Permette validare valore prima di chiedere pagamento
- Conversion rate typical: 10-15% free → paid per B2B SaaS

**Struttura tier**:
- **Free Plan**: Limitato per validare valore (non abuse), uso demo/onboarding
- **Tier 1** (Small/Starter): €15-29/mese - Target small business o prosumer
- **Tier 2** (Pro/Business): €49-99/mese - Target mid-market con needs più avanzati

**Annual discount**: -15-20% (incentiva commitment, riduce churn, cash upfront)

### Pricing Range per Categoria

**B2B SaaS (per utente/azienda mensile)**:
- **Micro business** (1-5 dipendenti): €10-25/mese
- **Small business** (5-20 dipendenti): €25-75/mese
- **Mid-market** (20-100 dipendenti): €75-300/mese
- ❌ Enterprise (100+ dipendenti): Evita per MVP (custom pricing, lunghi cicli vendita)

**B2C SaaS (per utente mensile)**:
- **Freemium → Basic**: €5-15/mese
- **Premium/Pro**: €15-30/mese
- ❌ >€30/mese: Rare per B2C, richiede valore molto alto

**Marketplace/Platform (take rate)**:
- **Typical take rate**: 10-20% del transaction value
- **Lower bound**: 5-10% (commodity, alta competition)
- **Upper bound**: 20-30% (alto valore aggiunto, network effects forti)

**Hardware + Software**:
- **Hardware**: Costo produzione + 30-50% markup (BOM * 1.3-1.5)
- **Software subscription**: €5-20/mese per device (se revenue ricorrente)

### Altri Modelli Pricing

**Usage-based** (pay per use):
- Buono per: API, infra services, variabilità alta utilizzo
- Esempio: €0.01-0.10 per API call, €0.001-0.01 per email sent

**One-time** (perpetual license):
- Raro per SaaS MVP (no recurring revenue)
- Possibile per: Software tools standalone, hardware

**Hybrid** (subscription + usage overages):
- Subscription base + usage oltre soglia
- Esempio: €29/mese (include 1000 API calls) + €10 per 1000 extra calls

**Rationale**: Freemium + subscription è modello più validato per SaaS MVP. Permette acquisition low-friction e recurring revenue predictable.

### Revenue Proiezione MVP (primi 6 mesi)

**Benchmark realistici**:
- **Mese 1-2**: €0 MRR (beta gratuita, 10-30 utenti test)
- **Mese 3-4**: €300-1k MRR (primi paying customers, conversion 10-15% di beta)
- **Mese 5-6**: €1-2k MRR (crescita organic + primii marketing spend)
- **Mese 12**: €5-10k MRR (se traction buona)

**Rationale**: Growth iniziale è lento. Serve validare product-market fit prima di scalare marketing.

---

## 6. Key Resources - Defaults per MVP

### Human Resources

**Team MVP minimo**:
- **1 Full-stack Developer**: €2.5-4k/mese (part-time o contractor)
- **1 Product Designer**: €1.5-3k/mese (part-time o contractor)
- **Founder/CEO**: €0/mese sweat equity (o salary minimo)

**Alternative lean**:
- **1 Full-stack founder + No-code tools** (Webflow, Bubble, Airtable)
- **2 co-founder** (tech + business split)

**Rationale**: Team piccolo riduce burn rate. Meglio 2 persone dedicate che 5 persone part-time con context switching.

### Technological Resources

**Stack MVP default**:

**Frontend**:
- **Framework**: React + Next.js (o Vue/Svelte se preferenza)
- **Hosting**: Vercel (zero-config, global CDN) o Netlify
- **Styling**: Tailwind CSS + component library (Shadcn/Radix)

**Backend**:
- **Option A (Full-stack framework)**: Next.js API routes + Serverless
- **Option B (Separate backend)**: Node.js + Express (o FastAPI per Python)
- **Hosting**: Vercel, Railway, Render (Managed, €0-50/mese MVP)

**Database**:
- **Relational**: PostgreSQL managed (Supabase, Neon, Railway) - €0-25/mese MVP
- **Alternative**: SQLite (Turso) per ultra-lightweight MVP

**Auth**:
- **Managed**: Supabase Auth, Clerk, Auth0 (€0-25/mese MVP)
- **Alternative**: NextAuth.js self-hosted

**Storage (files/images)**:
- **S3-compatible**: AWS S3, Cloudflare R2, Supabase Storage
- **CDN**: Cloudflare (free tier sufficiente MVP)

**Email**:
- **Transactional**: SendGrid, Mailgun, Resend (€0-15/mese MVP <10k email)
- **Marketing**: Loops, EmailOctopus (€0-30/mese MVP <1k contacts)

**Analytics**:
- **Product analytics**: Mixpanel (free tier fino 100k events), PostHog (self-hosted o cloud)
- **Web analytics**: Vercel Analytics, Plausible (privacy-focused)

**Payment**:
- **Processor**: Stripe (1.4% + €0.25 EU, best DX)
- **Alternative**: Paddle (merchant of record, gestisce VAT)

**Rationale**: Stack moderno, managed services, zero-ops. Permette iterate veloce e focus su product non infra.

### Intellectual Resources

**Default per MVP**:
- **IP**: Nessun brevetto per MVP (costoso, lento)
- **Algoritmi proprietari**: Solo se differenziatore core (altrimenti off-shelf)
- **Dati**: Early adopters feedback è IP principale per MVP

**Rationale**: IP e brevetti sono post-MVP concern. Focus su execution e learning dal mercato.

### Financial Resources

**Budget MVP range** (6 mesi):
- **Bootstrapped lean**: €10-20k (1 founder sweat equity + contractor part-time)
- **Small team**: €30-50k (2-3 persone part-time)
- **Small seed**: €80-150k (team full-time 2-3 persone + marketing)

**Breakdown typical** (€40k per 6 mesi):
- Team: 70-75% (€28-30k)
- Infra/Tools: 3-5% (€1.2-2k)
- Marketing: 15-20% (€6-8k)
- Buffer: 5-10% (€2-4k)

**Rationale**: Maggior costo è sempre team. Infra MVP è cheap (<€200/mese). Marketing importante post product-market fit.

---

## 7. Key Activities - Defaults per MVP

### Time Allocation Typical MVP

**Production** (50-60% tempo):
- Sviluppo software: 40%
- Design e UX: 10%
- Testing/QA: 10%

**Problem Solving** (20-30% tempo):
- Customer support: 10%
- Product iteration: 10%
- Bug fixing: 10%

**Platform/Network** (10-20% tempo):
- Customer development: 10%
- Content marketing: 5%
- Community building: 5%

**Rationale**: MVP focus su build product e iterate basato su feedback. Marketing intenso solo post product-market fit.

### Attività Non-MVP (da evitare)

- ❌ **Scaling infra** (premature optimization)
- ❌ **Integrazioni enterprise** (complesse, poco valore per MVP)
- ❌ **App mobile nativa** (se web app sufficiente)
- ❌ **Internazionalizzazione** (focus un mercato per MVP)
- ❌ **Team building/hiring** (team piccolo per MVP)

**Rationale**: Questi diventano priorità solo dopo product-market fit validato.

---

## 8. Key Partners - Defaults per MVP

### Technology Partners (Quasi sempre necessari)

**Payment processing**:
- **Stripe** (first choice per SaaS B2B/B2C)
- Alternative: Paddle (merchant of record), PayPal (B2C)

**Email sending**:
- **Transactional**: SendGrid, Resend, Mailgun
- **Marketing**: Loops, EmailOctopus, ConvertKit

**Hosting/Infra**:
- **Web hosting**: Vercel, Netlify, Railway
- **Database**: Supabase, Neon, PlanetScale (managed PostgreSQL)
- **CDN**: Cloudflare (free tier ottimo)

**Auth** (se non build in-house):
- **Supabase Auth**, Clerk, Auth0

**Analytics**:
- **Product**: Mixpanel (free tier), PostHog
- **Web**: Plausible, Vercel Analytics

**Rationale**: Questi partner riducono drasticamente time-to-market e ops overhead. Costi MVP sono bassi (€50-150/mese total).

### API & Data Partners (se needed)

**Common APIs MVP**:
- **Maps/Geolocation**: Google Maps API, Mapbox (pay per use)
- **SMS/Phone**: Twilio (pay per SMS)
- **AI/ML**: OpenAI API, Anthropic Claude (pay per token)
- **Data enrichment**: Clearbit, FullContact (pay per lookup)

**Rationale**: Build vs buy - per MVP quasi sempre "buy" APIs. Time-to-market > costo API.

### Strategic Partners (Nice-to-have, non critici per MVP)

**Distribution partners**:
- Associazioni di categoria (co-marketing)
- Influencer/creators (sponsorships, affiliates)
- Complementary products (integrations, co-selling)

**Rationale**: Strategic partners accelerano growth ma non bloccano MVP. Focus prima su direct channels.

---

## 9. Cost Structure - Defaults per MVP

### Fixed Costs per MVP (mensile)

**Team** (biggest cost - 70-75% total):
- 1 Full-stack Developer: €2.5-4k/mese part-time
- 1 Designer: €1.5-3k/mese part-time
- Founder: €0 sweat equity
- **Total team**: €4-7k/mese

**Tools & SaaS** (3-5% total):
- GitHub: €0-20/mese (free tier ok per MVP)
- Figma: €0-45/mese (professional)
- Analytics: €0/mese (free tiers)
- Project mgmt: €0-20/mese (Linear, Notion)
- Communication: €0/mese (Slack free)
- Email workspace: €10-20/mese (Google Workspace)
- **Total tools**: €50-150/mese

**Marketing** (15-20% total):
- Google Ads: €300-500/mese
- LinkedIn/Social Ads: €200-400/mese
- Content creation: €0-300/mese (founder-driven o freelance)
- **Total marketing**: €500-1.2k/mese

### Variable Costs per MVP (mensile, @ 50-100 utenti)

**Infrastructure** (scala con utenti):
- Hosting: €50-150/mese (Vercel/Netlify Pro)
- Database: €25-50/mese (Supabase Pro, Neon)
- CDN: €0/mese (Cloudflare free)
- Email: €15-50/mese (SendGrid, Mailgun)
- Payment processing: 1.4% + €0.25/transaction (Stripe)
- **Total infra**: €100-300/mese @ 50-100 users

**Customer Acquisition** (variabile):
- Ad spend: Vedi marketing fixed
- CAC target: €30-100 per B2B customer, €5-30 per B2C user
- Payback period target: <6 mesi

### Total Cost Structure MVP

**Lean MVP** (1 founder + contractors):
- Fixed: €5-8k/mese
- Variable: €100-300/mese
- **Total**: €5.1-8.3k/mese
- **6 mesi burn**: €30-50k

**Standard MVP** (small team):
- Fixed: €8-12k/mese
- Variable: €200-500/mese
- **Total**: €8.2-12.5k/mese
- **6 mesi burn**: €50-75k

**Rationale**: Team è 70% costo. Infra MVP è economica (<€300/mese). Marketing spend può variare molto (€0 per lean, €1k+ per growth mode).

### Break-even Calculation

**Formula**:
```
Break-even MRR = Total Fixed Costs + Avg Variable Costs
```

**Esempio** (Total costs €6k/mese):
- Break-even MRR: €6k/mese
- @ €30 ARPU: 200 paying customers
- @ 10% conversion free → paid: 2000 free users needed
- @ 1% visitor → signup: 200k visitors needed

**Timeframe realistico break-even**: 12-24 mesi post-MVP per early-stage SaaS

**Rationale**: Break-even operativo è milestone importante ma non immediato. VC-backed startups spesso non puntano a break-even pre Series A.

---

## When to Override These Defaults

Usa defaults diversi quando:

### Customer Segments
- **Brief specifica target diverso**: Usa quello (es. "enterprise" anche se non raccomandato per MVP)
- **Mercato molto specifico**: Adatta demographics/firmographics
- **Geography non-standard**: Brief specifica mercato non-Italia/EU

### Value Propositions
- **ROI cliente già quantificato** nel brief: Usa quello
- **Differenziatore unico evidente**: Enfatizza quello vs generic "10x better"

### Channels
- **Brief specifica channel strategy**: Usa quella (es. "partnership con X" come primary channel)
- **B2B enterprise target**: Direct sales necessario (no self-service)
- **Virality built-in product**: Referral/word-of-mouth può essere primary channel

### Revenue Streams
- **Brief specifica pricing**: Usa quello
- **Competitor pricing molto diverso**: Benchmark competitor se competitor-analysis.md presente
- **Modello business non-SaaS**: Marketplace, hardware, transaction-based richiedono modelli diversi

### Key Resources
- **Vincoli tecnologici nel brief**: Tech stack specifico richiesto
- **Team già esistente**: Adatta Key Resources a team attuale
- **Budget molto diverso**: Scale up o down risorse

### Cost Structure
- **Budget esplicito nel brief**: Usa quello
- **Team size/composition specificata**: Adatta cost structure
- **Geography team diversa**: Salary varies (US/UK più alto, EU centrale, Eastern EU/Asia più basso)

---

## Benchmark External

### SaaS B2B (per reference)

**Metrics**:
- **CAC**: €100-500 per SMB customer
- **LTV/CAC**: 3:1+ (healthy)
- **Churn rate**: 3-7% monthly (SMB), <2% (enterprise)
- **Rule of 40**: Growth rate % + Profit margin % ≥ 40%
- **Payback period**: 6-12 mesi target

**Pricing**:
- **SMB seat**: €10-50/user/mese
- **Mid-market**: €50-200/user/mese
- **Enterprise**: €200+/user/mese + custom

### SaaS B2C (per reference)

**Metrics**:
- **CAC**: €5-50 per user
- **LTV/CAC**: 3:1+ (healthy)
- **Churn rate**: 5-10% monthly typical
- **Free → Paid conversion**: 1-5% (broad), 10-20% (niche/high-value)

**Pricing**:
- **Consumer basic**: €5-15/mese
- **Consumer premium**: €15-30/mese
- **Prosumer/creator**: €30-100/mese

### Marketplace (per reference)

**Metrics**:
- **Take rate**: 10-20% typical
- **CAC**: Varia molto (supply vs demand side)
- **Gross margin**: 50-70% (high take rate marketplace)

**Critical mass**:
- **Minimum viable marketplace**: ~50-100 supply side, ~500-1000 demand side

---

## Summary: Most Common MVP Defaults

Se brief non specifica, usa questi come starting point:

1. **Customer Segments**: PMI 10-50 dipendenti (B2B) o Early adopters 25-45 anni (B2C)
2. **Value Prop**: ROI <3 mesi, time to value <1 giorno
3. **Channels**: Google Ads + LinkedIn Ads + Content (B2B), Google Ads + Social (B2C)
4. **Customer Relationships**: Self-service + automated (no high-touch)
5. **Revenue**: Freemium + 2 tier subscription (€15-29, €49-99)
6. **Key Resources**: 1 dev + 1 designer part-time, modern web stack, managed services
7. **Key Activities**: 50% production, 30% problem solving, 20% customer dev
8. **Key Partners**: Stripe, SendGrid, Vercel/Netlify, Supabase
9. **Costs**: €5-8k/mese (lean) a €8-12k/mese (standard)

**Break-even target**: 12-18 mesi post-MVP

**Rationale**: Questi defaults sono validati da centinaia di MVP SaaS successful. Permettono iterate veloce, costi contenuti, validazione rapida product-market fit.
