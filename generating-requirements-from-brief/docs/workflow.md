# Project Files Naming Convention

This document explains the file naming convention and lifecycle for files created during the requirements generation workflow.

---

## File Hierarchy

```
project-root/
├── brief.md                    # User creates, skill modifies (Phase 1)
├── brief-structured.md         # Skill creates (Phase 2), temporary
├── requirements.md             # Skill creates (Phase 3), final deliverable
└── [optional iterations]
    ├── brief-structured-v2.md  # If Phase 2 needs major revisions
    └── requirements-v*.md      # Archived versions if major changes
```

---

## File Descriptions

### 1. brief.md

**Created by**: User (initial), Skill modifies in Phase 1
**Modified by**: User (answers questions), Skill (adds questions)
**Purpose**: Starting point with project idea and clarifications

**Lifecycle**:
1. User creates with initial project notes
2. Skill reads it (Phase 1)
3. Skill adds "## Domande da chiarire" section
4. User answers questions directly in file
5. Skill reads updated version (Phase 2)
6. File is complete after Phase 1

**Typical Structure**:
```markdown
# Project Brief: [Project Name]

## Problem
[Description of problem being solved]

## Users
[Who will use this]

## Goals
[What success looks like]

## Constraints
[Timeline, budget, team]

## Additional Context
[Any other relevant information]

---

## Domande da chiarire
[Added by skill in Phase 1]

1. Che cosa intendi per [X]?
   Suggerimento: [Y]
   Perché: [Z]

   **Risposta**: [User answers here]

2. [More questions...]
```

**Gitignore**: NO - This is a project document, keep in git

---

### 2. brief-structured.md

**Created by**: Skill (Phase 2)
**Modified by**: Skill (if user requests changes)
**Purpose**: Stand-alone, complete second project document integrating brief + answers

**Lifecycle**:
1. Skill creates after reading updated brief.md (Phase 2)
2. User reviews it
3. If changes needed: Skill edits, user reviews again (loop)
4. When approved: Skill proceeds to Phase 3
5. After Phase 3 complete: Keep as second project document or archive

**Key Characteristics**:
- **Stand-alone**: Readable without seeing brief.md
- **Complete**: All information integrated seamlessly
- **No markers**: No [MODIFICATO], [AGGIUNTO], [CONFERMATO] in document body
- **Professional**: Can be shared with stakeholders
- **Second document**: Comes after brief.md, before requirements.md

**Typical Structure**:
```markdown
# [Project Name]: Brief Strutturato

**Data**: [Date]
**Versione**: 1.0

---

## 1. Problema

[Clear, complete problem statement]
[Narrative format, no markers or references to brief.md]

The project addresses [description of problem]. Current situation involves [pain points].
This impacts [stakeholders] by [consequences].

## 2. Utenti e Contesto

[Complete description of users, their context, workflows]

### [User Type 1]
**Chi è**: [Role/persona description]

**Cosa fa**: [Workflow, responsibilities]

**Necessità**: [What they need from the system]

### [User Type 2]
[Same structure]

## 3. Obiettivi

[What we want to achieve with MVP]

**Obiettivo primario**: [Main goal with measurable outcome]

**Obiettivi secondari**:
- [Secondary goal 1]
- [Secondary goal 2]

## 4. Vincoli

**Tecnici**: [Technical constraints]
**Organizzativi**: [Team, timeline]
**Business**: [Budget, market constraints]

## 5. Assunzioni

[List assumptions clearly with rationale, but NO references to Q[N] or defaults.md]

- **[Topic 1]**: [Assumption statement]. Rationale: [Why we assume this for MVP].
- **[Topic 2]**: [Assumption statement]. Rationale: [Why we assume this for MVP].

Example:
- **Autenticazione**: Email/password standard. Rationale: Semplice da implementare,
  adeguato per 1-5 locali pilota, può essere migliorato in v2.

## 6. Scope MVP

### Incluso in MVP
- [Feature 1 with brief description]
- [Feature 2 with brief description]

### NON incluso in MVP
- [Out of scope 1 with brief reason]
- [Out of scope 2 with brief reason]

## 7. Contesto Aggiuntivo

[Domain-specific context, special considerations]

## 8. Open Questions

[Questions to resolve before Phase 3]
- [Technical decision to make]
- [Business decision to validate]
```

**Writing Style**:
- ✅ Complete, narrative paragraphs
- ✅ Professional tone
- ✅ Can stand alone without context
- ❌ No "Based on answer to Q3"
- ❌ No [MARKERS] in document body
- ❌ No references to brief.md

**Gitignore**: NO - This is the second project document, keep in git

---

### 3. requirements.md

**Created by**: Skill (Phase 3)
**Modified by**: Skill (if user requests iterations)
**Purpose**: Final formal requirements document

**Lifecycle**:
1. Skill creates from brief-structured.md (Phase 3)
2. User reviews it
3. If changes needed: Skill edits (use Edit tool)
4. Version number updated in header (v1.0 → v1.1 → v2.0)
5. Final document when user approves

**Typical Structure**:
```markdown
# Requirements: [Project Name]

**Phase**: MVP / PoC / Beta
**Version**: 1.0
**Last Updated**: [Date]
**Status**: Draft / In Review / Approved

---

## 1. Overview
[Problem & Opportunity, Success Definition]

## 2. Users & Context
[Primary Users, User Scenarios, Why They Need This]

## 3. Core Requirements
[Functional Requirements, Non-Functional Requirements, Hardware if applicable]

## 4. Scope
[MVP v1 Includes, NOT Included, Future Phases]

## 5. Constraints
[Resources, Technical, Organizational]

## 6. Assumptions & Open Questions
[Key Assumptions, To Validate Early, Open Decisions]

## 7. Success Metrics
[How we measure MVP success]

## 8. Next Steps
[Immediate Actions, Timeline, Known Risks]

---

## Appendix
[Glossary, Document History]
```

**Gitignore**: NO - This is the main deliverable, keep in git

---

## Version Management

### brief.md
- **No versioning**: Modified in place until Phase 1 complete
- If major changes after Phase 2 starts: Ask user if they want to restart from Phase 1

### brief-structured.md
- **Light versioning**: If major revisions needed:
  - Option 1: Edit in place (for small changes)
  - Option 2: Create brief-structured-v2.md (for major revisions)
  - Delete temporary versions once requirements.md is approved

### requirements.md
- **Version in header**: Track version in document metadata
  ```markdown
  **Version**: 1.0 → 1.1 → 2.0
  ```
- **Version semantics**:
  - v1.0: Initial version
  - v1.1, v1.2: Minor iterations (clarifications, small additions)
  - v2.0: Major changes (scope change, new features, re-scoping)

- **Archive old versions** (optional):
  - Rename to `requirements-v1.0.md` before creating v2.0
  - Or rely on git history

---

## Gitignore Recommendations

```gitignore
# Skill reference files (NOT project files)
.claude/skills/requirements-from-brief/*.md

# Keep ALL project documents in git
brief.md
brief-structured.md
requirements.md
```

**Explanation**:
- Skill reference files (defaults.md, template.md, etc): Part of skill, not project
- brief.md: First project document (user's initial idea + clarifications)
- brief-structured.md: Second project document (complete, integrated brief)
- requirements.md: Third project document (formal requirements)

All three project documents should be version controlled.

---

## File State Transitions

### Phase 1: brief.md modified
```
brief.md (user created)
  ↓ [Read tool]
brief.md (skill adds questions)
  ↓ [user edits]
brief.md (with answers)
```

### Phase 2: brief-structured.md created
```
brief.md (with answers)
  ↓ [Read tool]
  ↓ [Write tool]
brief-structured.md v1
  ↓ [user reviews, requests changes]
  ↓ [Edit tool]
brief-structured.md v2
  ↓ [user approves]
```

### Phase 3: requirements.md created
```
brief-structured.md (approved)
  ↓ [Read tool]
  ↓ [Write tool]
requirements.md v1.0
  ↓ [user reviews, requests changes]
  ↓ [Edit tool]
requirements.md v1.1
  ↓ [user approves]
requirements.md v1.0 (FINAL)
```

---

## Tool Usage per File

### brief.md
- **Read**: Phase 1 start, Phase 2 start (if needed)
- **Edit**: Phase 1 to add questions
- **Never**: Write (it already exists)

### brief-structured.md
- **Write**: Phase 2 to create initial version
- **Edit**: Phase 2 iterations if user requests changes
- **Read**: Phase 3 to generate requirements.md

### requirements.md
- **Write**: Phase 3 to create initial version
- **Edit**: Phase 3 iterations if user requests changes
- **Read**: Phase 3+ if need to reference for further work

---

## Common Issues & Solutions

### Issue: User wants to change brief.md after Phase 2 starts
**Solution**:
- Ask if they want to restart Phase 1
- Or incorporate changes directly in brief-structured.md
- Document changes with [MODIFICATO] markers

### Issue: Major scope change during Phase 3
**Solution**:
- Archive current requirements.md as requirements-v1.0-archived.md
- Go back to Phase 2, update brief-structured.md
- Generate new requirements.md v2.0

### Issue: User confused about which file to edit
**Solution**:
- Always tell user explicitly which file to edit
- Provide clear instructions in chat output
- Use file references in messages (e.g., "Open brief.md")

---

## Summary

| File | Creator | Modified By | Purpose | Keep in Git? |
|------|---------|-------------|---------|--------------|
| brief.md | User | Skill (Phase 1), User (answers) | Starting point + clarifications | YES |
| brief-structured.md | Skill (Phase 2) | Skill (if changes) | Second project document: complete, stand-alone brief | YES |
| requirements.md | Skill (Phase 3) | Skill (if changes) | Third project document: formal requirements | YES |

**Key Principles**:
- Use files to maintain context between phases, not just chat history
- Each file is a stand-alone, professional document
- No diff markers or references between documents
