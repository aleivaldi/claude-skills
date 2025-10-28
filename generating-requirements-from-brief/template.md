# Output Template and Structure

## Requirements Document Template

Use this structure when generating requirements.md in Phase 3.

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

## Section Guidelines

### 1. Overview
**Length**: ~200-300 words
**Tone**: Clear, accessible to non-technical stakeholders
**Focus**: Problem being solved, why it matters, what success looks like for THIS phase

### 2. Users & Context
**Length**: ~300-400 words
**Include**: Who (role/persona), how many, technical level, environment, main workflow
**Avoid**: Named individuals (use roles), excessive detail about user background

### 3. Core Requirements
**Length**: ~800-1200 words (largest section)
**Functional**: 3-5 core features for MVP, each with What/Why/UX
**Non-Functional**: Table format, 6-8 aspects (performance, scale, platform, etc)
**Hardware** (if applicable): Device specs, components, manufacturing, integration

### 4. Scope
**Length**: ~300-400 words
**Be explicit**: What's in v1, what's explicitly NOT in v1, what's future
**Avoid**: Vague statements like "we might add later" - be specific

### 5. Constraints
**Length**: ~200-300 words
**Include**: Team size, timeline, budget, technical constraints, organizational limits
**Be realistic**: Don't hide constraints - they inform the design

### 6. Assumptions & Open Questions
**Length**: ~300-400 words
**Format**: Table for assumptions (assumption/if wrong/signal)
**Purpose**: Make bets explicit, identify what to validate early

### 7. Success Metrics
**Length**: ~150-200 words
**Format**: Table (metric/measurement/target)
**Be specific**: Measurable targets, not vague goals

### 8. Next Steps
**Length**: ~200-300 words
**Include**: Immediate actions (checklist), timeline (table), risks (table)
**Be actionable**: Who does what by when

---

## Document Length Guidelines

- **Small project**: 2000-2500 words
- **Medium project**: 2500-3500 words
- **Complex project**: 3500-4500 words

Rarely more than 4500 words (already detailed for MVP phase).

---

## Writing Tips

1. **Use user's own language** - Makes them feel heard, easier to understand
2. **Make tables readable** - Easier to scan than paragraphs
3. **Highlight assumptions clearly** - Use tables and markers
4. **Be specific**: "5 concurrent users" not "scalable"
5. **Show tradeoffs**: "We chose X over Y because MVP phase"
6. **Keep language simple** - Non-technical stakeholders read this
7. **Use active voice** - "User clicks button" not "button is clicked"
8. **Avoid jargon** - Or define it in Glossary

---

## Common Mistakes to Avoid

❌ **Too technical**: Don't specify implementation (React, PostgreSQL, AWS)
✅ **Right level**: Specify requirements (web platform, relational DB, cloud hosted)

❌ **Too vague**: "The system should be fast"
✅ **Specific**: "Page loads in <2 seconds on standard broadband"

❌ **Feature list only**: Just listing features without context
✅ **Feature + Why**: Each feature explains problem it solves

❌ **No scope boundaries**: Everything is "future phases"
✅ **Explicit boundaries**: Clear what's in v1, NOT in v1, and future

❌ **Hidden assumptions**: Assuming things without stating them
✅ **Explicit assumptions**: Table of assumptions with if-wrong scenarios

---

## Examples

For complete worked examples, see separate project example files:
- Software project example: Freelancer Invoice Platform
- Hardware project example: IoT Plant Monitor
- Mixed project example: Smart Home Security System

These are kept in separate files to avoid bloating the skill prompt.
