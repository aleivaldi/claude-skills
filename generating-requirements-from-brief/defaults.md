# MVP/PoC Pragmatic Defaults Reference

When the brief doesn't specify something, use these defaults unless the user tells you otherwise.

## Architecture & Deployment

| Default | Why MVP-Friendly | Override When |
|---------|------------------|---------------|
| **Single-tenant SaaS** (vs multi-tenant) | Saves 2-3 weeks (no data isolation, billing complexity) | Multiple orgs managing own data |
| **Web + mobile responsive** (vs native apps) | 50% faster to market, all devices | Needs offline-first or app store |
| **Cloud managed services** (vs on-premise) | Lower ops burden, auto-scaling | Data residency/security requirements |

---

## Hardware & IoT Defaults

| Default | Why MVP-Friendly | Override When |
|---------|------------------|---------------|
| **Single device type** (vs multiple SKUs) | Validates market fit first, iterate after | Market demands variants from day 1 |
| **Off-shelf components** (vs custom PCB) | Faster prototype, lower NRE, easier sourcing | Specific performance/size/cost needs |
| **WiFi connectivity** (vs cellular/LoRa) | Standard, user-managed, low cost | Needs standalone or Bluetooth for cost |
| **USB charging** (vs proprietary/wireless) | Ubiquitous, cheap, users have cables | Wearable/always-on (then optimize battery) |
| **Unregulated device** (vs FCC/CE/medical) | Avoids 3-6mo certification cost | Medical, safety-critical, or radioactive |
| **Simple firmware** (vs RTOS) | Faster dev, easier debug, quicker iteration | Hard real-time or extreme reliability needs |
| **Cloud backend** (vs offline-only) | Learn from data, update without recalls | Privacy/security requires fully local |
| **Manual updates** (vs automatic) | Acceptable for MVP small user base | Device at scale, manual infeasible |
| **50-200 units** (vs 1000+) | Validate with real users first | Market demands high volume from launch |

---

## Scale & Performance

| Default | Why MVP-Friendly | Override When |
|---------|------------------|---------------|
| **<2sec response** (vs <500ms) | Acceptable web standard, matches expectations | Real-time or time-critical operations |
| **Tens-hundreds users** (vs thousands+) | Realistic MVP scale, easier validation | Enterprise/platform ambitions from day 1 |
| **Single-digit concurrent** (vs hundreds) | MVP load light, scale later | High-traffic operations or campaigns |
| **Business hours (9am-6pm)** (vs 24/7 SLA) | MVP doesn't justify 24/7 ops cost | Multi-timezone requiring continuous access |

---

## Security & Compliance

| Default | Why MVP-Friendly | Override When |
|---------|------------------|---------------|
| **GDPR if EU users** | Legal requirement | Different jurisdiction requirements |
| **Standard security** (HTTPS, DB encryption vs HSM) | Managed cloud handles well | Financial/healthcare/regulated data |
| **Email/password** (vs SSO/OAuth/SAML) | Simplest to implement | Enterprise with existing SSO |
| **No backup SLA** (vs RPO<1h, RTO<15m) | MVP doesn't warrant DR cost | Critical business data, loss catastrophic |

---

## Features & Integrations

| Default | Why MVP-Friendly | Override When |
|---------|------------------|---------------|
| **No integrations v1** | Each adds 1-2 weeks, focus core first | Integration core to solution |
| **Manual data entry** (vs bulk import) | Small data volume for MVP | Large existing dataset to migrate |
| **Email/CSV export** (vs APIs/webhooks) | Simple, covers 90% MVP cases | Downstream system integration needed |
| **Polling** (vs WebSocket/real-time) | Simpler, acceptable latency for MVP | Instant sync across devices/users needed |

---

## Platform Compatibility

| Default | Why MVP-Friendly | Override When |
|---------|------------------|---------------|
| **Modern browsers** (Chrome/Firefox/Safari/Edge 90+, vs IE11) | Avoid dev complexity, MVP users have modern browsers | Specific legacy customer base |
| **Desktop-first** (vs mobile-first) | MVP users work at desks, responsive sufficient | Primary use genuinely mobile (field work) |
| **No native app** (vs iOS/Android) | Web saves months of development | Needs offline, app store, platform features |

---

## Data & Storage

| Default | Why MVP-Friendly | Override When |
|---------|------------------|---------------|
| **Relational DB** (PostgreSQL/MySQL vs NoSQL) | Structured data, ACID, well-understood | Unstructured data or extreme scale |
| **Cloud file storage** (S3/GCS vs DB BLOBs/CDN) | Simpler, auto-scales | High-speed media delivery globally |
| **Daily backups** (vs real-time replication) | Adequate for MVP, lower cost | Can't tolerate 24h data loss |

---

## DevOps & Deployment

| Default | Why MVP-Friendly | Override When |
|---------|------------------|---------------|
| **Managed cloud** (AWS/GCP/Heroku vs K8s/self-managed) | Lower ops burden, auto-scaling, cost-effective | Specific cloud reqs or vendor lock-in concerns |
| **Weekly deploys** (vs CD/multiple daily) | Reduced ops complexity for MVP | Needs rapid feedback loop or A/B testing |
| **Standard logging/monitoring** (vs custom) | Managed services provide basic monitoring | Specific operational requirements |

---

## Cost & Operations

| Default | Why MVP-Friendly | Override When |
|---------|------------------|---------------|
| **$100-500/mo infrastructure** (vs enterprise) | MVP doesn't warrant expensive infra | Higher scale expectations from start |
| **Email support only** (vs phone/chat/24-7) | Reduces ops cost, adequate for MVP | B2B enterprise expecting premium support |
| **Minimal documentation** (vs comprehensive API/training) | MVP is learning phase, docs evolve | Integrates with many external systems |

---

## When to Override

- **User explicitly states**: Always honor (e.g., "need real-time" → WebSocket)
- **Constraint makes impossible**: Adapt (e.g., "HIPAA" → not standard security)
- **Conflict with core need**: Choose MVP goal (e.g., "QuickBooks sync" → integration IS core)
- **Industry norms**: Respect domain (e.g., financial → encryption, audit trails)

---

## How to Use in Questions

Integrate defaults into question suggestions:
```
1. Che cosa intendi per "piattaforma"?
   Suggerimento: Web responsive
   Perché: Più veloce da sviluppare rispetto ad app native

2. Che cosa intendi per "molti utenti"?
   Suggerimento: Decine o centinaia per MVP (non migliaia)
   Perché: Scala realistica per validare prodotto
```

User can accept with "OK" or provide different answer.

---

## Checklist: Defaults Covered

When presenting Phase 1 output, verify you've considered:

- [ ] Platform (web, mobile, desktop?)
- [ ] Scale (how many users/transactions?)
- [ ] Architecture (single vs multi-tenant?)
- [ ] Performance (response time expectations)
- [ ] Availability (24/7 or business hours?)
- [ ] Security (standard or custom?)
- [ ] Compliance (GDPR, industry-specific?)
- [ ] Integrations (any required for v1?)
- [ ] Data (structure, storage, backups?)
- [ ] Cost (infrastructure budget?)
- [ ] Deployment (how often? where?)

