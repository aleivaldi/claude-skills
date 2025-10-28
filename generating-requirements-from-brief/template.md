# Template e Struttura Output

## Template Documento Requirements

Usa questa struttura quando generi requirements.md nella Fase 3.

```markdown
# Requirements: [PROJECT NAME]

**Phase**: MVP / PoC / Beta
**Version**: 1.0 (or 2.0 after iteration)
**Last Updated**: [Date]
**Status**: Draft / In Review / Approved

---

## 1. Overview

### Problem & Opportunity

[2-3 sentences: What problem does this solve? Why does it matter?]

[Who benefits? Market/user base?]

### Success Definition for This Phase

[What does "done and valuable" look like for MVP/PoC?]
[Specific, measurable if possible]

---

## 2. Users & Context

### Primary Users

**Role/Type**: [description of who uses this]
**Count**: [order of magnitude: 10, 100, 1000?]
**Technical Skill**: [non-technical, some, advanced?]
**Environment**: [desktop at office, mobile in field, either?]

### User Scenarios

**Main Workflow**:
1. User [action]
2. System [response]
3. User [action]
4. System [result]

### Why They Need This

[What pain does it solve? How much time/effort does it save?]

---

## 3. Core Requirements

### Functional Requirements (What It Must Do)

**Feature 1: [Name]**
- **What**: [Clear, simple description]
- **Why**: [Solves what problem?]
- **User Experience**: [How user experiences this]

**Feature 2: [Name]**
- **What**: [Clear description]
- **Why**: [Solves what problem?]
- **User Experience**: [How user experiences this]

**Feature 3: [Name]**
[Same structure]

[Usually 3-5 core features for MVP]

### Non-Functional Requirements (How It Behaves)

| Aspect | Requirement | Why |
|--------|-------------|-----|
| **Performance** | [e.g., Page loads <2 seconds] | [Why: user needs responsiveness] |
| **Availability** | [e.g., 9am-6pm business hours] | [Why: adequate for MVP] |
| **Scale** | [e.g., 50 agencies, 5 users each] | [Why: realistic MVP size] |
| **Platform** | [e.g., Web + mobile responsive] | [Why: faster to market] |
| **Data** | [e.g., GDPR compliant, EU servers] | [Why: legal requirement] |
| **Integrations** | [e.g., None in v1, email export] | [Why: focus on core features] |

---

## 3.1 Hardware Requirements (If Applicable)

*Include this section only if your project has physical hardware components.*

### Device Specifications

**Device Type**: [e.g., "IoT sensor", "Wearable", "Mobile device", "Industrial device"]

**Form Factor**: [Size, weight, materials, industrial design notes]

**Power**: [Battery, charging, power consumption, battery life target]

**Connectivity**: [WiFi, Bluetooth, cellular, wired, offline capability]

**Environmental Requirements**: [Operating temperature, humidity, durability, IP rating]

### Component Priorities (for MVP)

**Must Have**:
- [Core hardware component 1]
- [Core hardware component 2]
- [Firmware/software to operate it]

**Nice to Have**:
- [Enhancement component or feature]

**Future**:
- [Advanced components or sensor types]

### Integration Points

- **Software ↔ Hardware**: [How does the app/firmware control the device?]
- **Cloud Integration**: [Does device send data to cloud? How often?]
- **User Interaction**: [How does user control it? Physical buttons, app, voice?]

### Manufacturing/Supply

- **Sourcing**: [Where will you source components? Lead times?]
- **Assembly**: [Internal or outsourced?]
- **Cost Target**: [BOM cost estimate, unit economics]
- **Initial Volume**: [MVP production volume? 10 units? 100? 1000?]

---

## 4. Scope

### MVP v1 Includes

- [Feature/capability included]
- [Feature/capability included]
- [Feature/capability included]

### Explicitly NOT Included (v1)

- [Won't have X] → future phase
- [Won't have Y] → manual workaround acceptable
- [Won't have Z] → depends on v1 feedback

### Future Phases

**v2 (based on v1 learning)**:
- [Enhancement requested by users]
- [Integration users wanted]

**v3+**:
- [Nice-to-have from original scoping]

---

## 5. Constraints

### Resources

- **Team**: [e.g., "3-person: 1 fullstack + 1 designer + 1 PM"]
- **Timeline**: [e.g., "3 months to beta"]
- **Budget**: [if relevant: "lean budget, cost-conscious"]

### Technical

- [External dependencies/must-haves]
- [Platform requirements]
- [Infrastructure preferences]

### Organizational

- [Team skill gaps?]
- [External approval needed?]

---

## 6. Assumptions & Open Questions

### Key Assumptions Made for MVP

These are bets we're making. If any prove wrong, we adapt in v2.

| Assumption | If Wrong | How We'll Know |
|-----------|----------|-----------------|
| [Assumption 1] | [Impact if incorrect] | [Signal/metric to watch] |
| [Assumption 2] | [Impact if incorrect] | [Signal/metric to watch] |

### To Validate Early

These questions impact the roadmap:

- [ ] [Question that affects direction?]
- [ ] [Question that affects priority?]

### Open Decisions

- **[Topic]**: [What we're deferring to v2 or later]
- **[Topic]**: [What we're deferring]

---

## 7. Success Metrics

How we know this MVP worked:

| Metric | Measurement | Target |
|--------|-------------|--------|
| [What] | [How we measure] | [Target number] |
| [What] | [How we measure] | [Target number] |

---

## 8. Next Steps

### Immediate Actions

- [ ] Stakeholder approval of this document
- [ ] Share with design team
- [ ] Share with dev team
- [ ] [Other action]

### Timeline

| When | What | Owner |
|------|------|-------|
| Week 1-2 | Design/UX work | [Owner] |
| Week 3-4 | Technical architecture | [Owner] |
| Week 5-X | Development | [Owner] |

### Known Risks & Mitigation

| Risk | Likelihood | Impact | Mitigation |
|------|-----------|--------|-----------|
| [Risk] | [L/M/H] | [scope/timeline/quality] | [How we address] |

---

## Appendix

### Glossary
[If domain-specific terms, define them]

### Document History
| Version | Date | Change |
|---------|------|--------|
| 1.0 | [Date] | Initial |

```

---

## Linee Guida per Sezioni

### 1. Overview
**Lunghezza**: ~200-300 parole
**Tono**: Chiaro, accessibile a stakeholder non-tecnici
**Focus**: Problema risolto, perché è importante, cosa significa successo per QUESTA fase

### 2. Utenti e Contesto
**Lunghezza**: ~300-400 parole
**Includere**: Chi (ruolo/persona), quanti, livello tecnico, ambiente, workflow principale
**Evitare**: Nomi individuali (usa ruoli), dettagli eccessivi sul background utente

### 3. Requisiti Core
**Lunghezza**: ~800-1200 parole (sezione più grande)
**Funzionali**: 3-5 funzionalità core per MVP, ognuna con Cosa/Perché/UX
**Non-Funzionali**: Formato tabella, 6-8 aspetti (performance, scala, piattaforma, etc)
**Hardware** (se applicabile): Specifiche dispositivo, componenti, produzione, integrazione

### 4. Scope
**Lunghezza**: ~300-400 parole
**Essere espliciti**: Cosa c'è in v1, cosa esplicitamente NON c'è in v1, cosa è futuro
**Evitare**: Affermazioni vaghe come "potremmo aggiungere dopo" - essere specifici

### 5. Vincoli
**Lunghezza**: ~200-300 parole
**Includere**: Dimensione team, timeline, budget, vincoli tecnici, limiti organizzativi
**Essere realistici**: Non nascondere i vincoli - informano il design

### 6. Assunzioni e Domande Aperte
**Lunghezza**: ~300-400 parole
**Formato**: Tabella per assunzioni (assunzione/se sbagliata/segnale)
**Scopo**: Rendere le scommesse esplicite, identificare cosa validare presto

### 7. Metriche di Successo
**Lunghezza**: ~150-200 parole
**Formato**: Tabella (metrica/misurazione/target)
**Essere specifici**: Target misurabili, non obiettivi vaghi

### 8. Prossimi Passi
**Lunghezza**: ~200-300 parole
**Includere**: Azioni immediate (checklist), timeline (tabella), rischi (tabella)
**Essere attuabili**: Chi fa cosa e quando

---

## Linee Guida Lunghezza Documento

- **Progetto piccolo**: 2000-2500 parole
- **Progetto medio**: 2500-3500 parole
- **Progetto complesso**: 3500-4500 parole

Raramente più di 4500 parole (già dettagliato per fase MVP).

---

## Suggerimenti di Scrittura

1. **Usa il linguaggio dell'utente** - Li fa sentire ascoltati, più facile da capire
2. **Rendi le tabelle leggibili** - Più facili da scansionare dei paragrafi
3. **Evidenzia chiaramente le assunzioni** - Usa tabelle e marker
4. **Sii specifico**: "5 utenti concorrenti" non "scalabile"
5. **Mostra i tradeoff**: "Abbiamo scelto X invece di Y perché fase MVP"
6. **Mantieni linguaggio semplice** - Stakeholder non-tecnici leggono questo
7. **Usa voce attiva** - "L'utente clicca il pulsante" non "il pulsante viene cliccato"
8. **Evita jargon** - Oppure definiscilo nel Glossario

---

## Errori Comuni da Evitare

❌ **Troppo tecnico**: Non specificare implementazione (React, PostgreSQL, AWS)
✅ **Livello giusto**: Specifica requisiti (piattaforma web, DB relazionale, hosting cloud)

❌ **Troppo vago**: "Il sistema dovrebbe essere veloce"
✅ **Specifico**: "Caricamento pagina in <2 secondi su banda standard"

❌ **Solo lista funzionalità**: Elencare solo funzionalità senza contesto
✅ **Funzionalità + Perché**: Ogni funzionalità spiega il problema che risolve

❌ **Nessun confine di scope**: Tutto è "fasi future"
✅ **Confini espliciti**: Chiaro cosa c'è in v1, NON in v1, e futuro

❌ **Assunzioni nascoste**: Assumere cose senza dichiararle
✅ **Assunzioni esplicite**: Tabella di assunzioni con scenari se-sbagliata

---

## Esempi

Per esempi completi, vedi file di esempio progetto separati:
- Esempio progetto software: Piattaforma Fatturazione Freelancer
- Esempio progetto hardware: Monitor Piante IoT
- Esempio progetto misto: Sistema Sicurezza Smart Home

Questi sono mantenuti in file separati per evitare di appesantire il prompt della skill.
