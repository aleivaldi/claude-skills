---
name: Generating Requirements from Brief
description: Transform rough project brief notes into formal MVP/PoC requirements document. Generates 8-section document with clear assumptions, scope, and success metrics. Supports software, hardware, and mixed projects.
---

# Generating Requirements from Brief

## Your Task

Transform the user's project brief (usually in `brief.md`) into a formal MVP/PoC requirements document through an iterative, file-based workflow.

Process in **3 phases**:

1. **Phase 1 (Parse & Question)**: Leggi brief.md, identifica carenze e poni domande all'utente spinegendolo a modificare brief.md fino a quando sarà sufficientemente chiaro.
2. **Phase 2 (Restructure)**: Crea brief-structured.md riscrivendo in modo più formale e completo di quanto indicato in brief.md
3. **Phase 3 (Generate)**: Crea un documento formale requirements.md with 8 sections

## Language Rule

**Match the language of the brief.md file:**
- If brief.md is in Italian → respond in Italian
- If brief.md is in English → respond in English
- If brief.md is in other language → respond in that language

Only respond in a different language if the user explicitly requests it.

---

## Project Files Naming Convention

Durante il workflow, questi file vengono creati/modificati:

### 1. brief.md (utente crea e modifica)
- **Created by**: User (input iniziale)
- **Modified by**: User (Phase 1 da domande su terminale e l'utente agisce modificandolo)
- **Purpose**: Punto di partenza con un idea. Possono essere appunti o trascrizioni di riunione
- **Lifecycle**: Modified until all questions answered

### 2. brief-structured.md (skill crea in Phase 2)
- **Created by**: Skill (Phase 2)
- **Modified by**: Skill basato su brief.md ed assunzioni
- **Purpose**: Documento ordinato e completo che aggiunge dettagli a quanto indicato in brief.md
- **Lifecycle**: Modificato fino a quando l'utente non lo ritiene corretto

### 3. requirements.md (skill crea in Phase 3)
- **Created by**: Skill (Phase 3)
- **Modified by**: Skill based on user feedback
- **Purpose**: Documento con specifiche, esaustivo e utilizzabile per analisi e progettazione future.
- **Versioning**: v1.0, v2.0, etc in document header and name
- **Lifecycle**: Final deliverable, can be iterated

---

## Phase 1: Parse and Question

### When to Use
L'utente chiede di iniziare, fornisce un file brief.md o effettua modifiche a quello già analizzato

### Tools to Use
1. **Read** tool → read brief.md

### Process

1. **Read brief.md** using Read tool

**If User aspks to go directly to Phase 2**: Skip to Phase 2 directly
   - Output: "OK, procedo con la fase 2 come richiesto."
   - Do NOT add questions to brief.md
   - Go directly to Phase 2

2. **Evaluate if Phase 1 is needed**:

   Ask yourself:
   - Is the problem clearly stated?
   - Are users and their needs described?
   - Are constraints (timeline, team, budget) mentioned?
   - Is the MVP scope clear enough to proceed?

   **If YES to all above**: Skip to Phase 2 directly
   - Output: "Il brief è sufficientemente dettagliato. Procedo con Phase 2."
   - Do NOT add questions to brief.md
   - Go directly to Phase 2

   **If NO to some**: Continua con Phase 1 come indicato in ./phase_1.md

---

## Phase 2: Restructure Brief

### When to Use
Quando brief.md è sufficientemente chiaro e non servoo domande di approfondimento o l'utente lo ha già modificato rispondendo alle domande poste.

### Tools to Use
1. **Read** tool → read updated brief.md
2. **Write** tool → create brief-structured.md
3. **AskUserQuestion** tool → confirm or ask for changes

### Process

1. **Read updated brief.md** with user answers

2. **Create brief-structured.md** using Write tool as a **stand-alone, consistent document**:

   **CRITICAL RULES**:
   - ✅ Write as complete, readable document (not a diff)
   - ✅ Integrate answers and assumptions seamlessly
   - ✅ Use narrative paragraphs, professional tone
   - ❌ NO markers ([CONFERMATO], [AGGIUNTO], [MODIFICATO])
   - ❌ NO references to "Q[N]", "answer to question", "defaults.md"
   - ❌ NO "Based on brief.md" language

   **Structure** (8 sections):
   1. Problema - Complete problem statement
   2. Utenti e Contesto - User types with workflows
   3. Obiettivi - MVP goals (primary + secondary)
   4. Vincoli - Technical, organizational, business constraints
   5. Assunzioni - Assumptions with rationale refs
   6. Elenco funzionalità principali e descrizione
   7. Elenco workflow principali
   8. Scope MVP - Included / NOT included lists
   9. Open Questions - Unresolved decisions

   **Example assumption format**:
   - **Authentication**: Email/password standard. Rationale: Simple to implement, adequate for 1-5 pilot locations.

   See `phase_1.md` Case 0 for complete example.

3. **Track changes internally for your chat output**, but keep brief-structured.md clean:

   As you write brief-structured.md, track:
   - What came from original brief (confirmed)
   - What came from user answers (added/modified)
   - What came from defaults (assumed)

   But DON'T put these markers in the file.

4. **Output to user** (in chat, with change summary):
   ```markdown
   # Phase 2: Brief Strutturato Creato

   Ho creato **brief-structured.md** - il secondo documento di progetto.

   ## Cosa contiene
   - Problema e contesto utenti integrati dalle tue risposte
   - [N] assunzioni esplicitate per MVP
   - Scope chiaro (cosa è incluso / non incluso)
   - Vincoli e obiettivi strutturati

   ## Principali integrazioni dalle tue risposte
   - [Chiarimento 1]: [breve descrizione]
   - [Chiarimento 2]: [breve descrizione]
   - [Assunzione 1]: [breve descrizione]

   ## Prossimo passo
   Per favore rivedi **brief-structured.md**.
   È un documento stand-alone che può essere condiviso con stakeholder.
   ```

5. **Use AskUserQuestion** to confirm:
   - "Il brief strutturato riflette correttamente il progetto?"
   - "Vuoi modifiche o chiarimenti prima di passare ai requisiti formali?"

6. **If changes requested**:
   - Use Edit tool to update brief-structured.md
   - In chat output, explain what you changed and why
   - Ask for confirmation again
   - **Loop until approved**

7. **When approved**, announce ready for Phase 3

---

## Phase 3: Generate Requirements Document

### When to Use
After brief-structured.md is approved

### Tools to Use
1. **Read** tool → read brief-structured.md
2. **Write** tool → create requirements.md
3. **Edit** tool → for iterations (if user requests changes)

### Process

1. **Read brief-structured.md**

2. **Create requirements.md** using Write tool with 8 sections:
   1. **Overview** - Problem statement, success definition for MVP
   2. **Users & Context** - Users, workflows, why they need it
   3. **Core Requirements** - Features (functional), non-functional (performance, scale, security, platform, data, integrations), hardware (if applicable)
   4. **Scope** - MVP v1 includes, explicitly NOT includes, future phases
   5. **Constraints** - Team, timeline, budget, technical, organizational
   6. **Assumptions & Open Questions** - Key assumptions, what to validate, open decisions
   7. **Success Metrics** - How we measure MVP success
   8. **Next Steps** - Who does what, timeline, risks

3. **Use template structure from `template.md`**

4. **Output to user**:
   ```markdown
   # Phase 3: Requirements Document Created

   Ho creato requirements.md (v1.0) con 8 sezioni:

   1. Overview - [brief summary]
   2. Users & Context - [brief summary]
   3. Core Requirements - [N functional features, non-functional aspects]
   4. Scope - [what's in/out]
   5. Constraints - [key constraints]
   6. Assumptions & Open Questions - [N assumptions]
   7. Success Metrics - [N metrics]
   8. Next Steps - [timeline, risks]

   Lunghezza: ~[N] parole

   Per favore revedi requirements.md e fammi sapere se vuoi modifiche.
   ```

### Iterations

If user requests changes:

1. **Read requirements.md**
2. **Edit requirements.md** (use Edit tool for specific changes)
3. **Update version** in document header (v1.1, v2.0, etc)
4. **Output** (in chat) summary of changes:
   - What was modified
   - What was added
   - What was removed

   Keep the document itself clean - no markers in the body.

---

## Reference Materials

### For Phase 1 Parsing
See `phase_1.md` for:
- Parsing algorithm (extract clear/unclear/implied)
- Question generation patterns
- Edge cases (hardware, regulatory, very short briefs)
- Conflict detection patterns

### For Pragmatic MVP Defaults
See `defaults.md` for:
- Software defaults (platform, scale, security, performance)
- Hardware defaults (components, power, connectivity, manufacturing)
- When to override each default
- How to format suggestions in questions

### For Output Structure
See `template.md` for:
- Complete 8-section template structure
- How to structure each section
- What level of detail for each section

### For Project File Management
See `docs/workflow.md` for detailed documentation on:
- File lifecycle and state transitions
- Naming conventions and versioning
- Gitignore recommendations

---

## Key Rules

**Iterative Process**:
- Phase 1: Modify brief.md (add questions), or skip if complete
- Phase 2: Create stand-alone brief-structured.md, loop until approved
- Phase 3: Create requirements.md, iterate if needed
- Track changes in chat, keep documents clean (no markers in body)

**Tool Usage** (⚠️ CRITICAL SEQUENCE):
- ✅ **ALWAYS** Read before Edit/Write (prevents stale data errors)
- ✅ Edit for existing files, Write for new files
- ✅ AskUserQuestion for confirmations
- ❌ **NEVER** Write on existing files (use Edit)
- ❌ **NEVER** Edit without Reading first
- ❌ **NEVER** proceed without user confirmation when asked

**Pragmatic MVP**:
- Propose sensible defaults (see `defaults.md`)
- Simpler is better: off-shelf, web, no integrations initially
- User can always override

**Transparency**:
- State assumptions with rationale
- Show reasoning for defaults
- Flag conflicts explicitly

**Efficiency**:
- Ask 0-8 questions (only necessary ones)
- Reference files, don't repeat
- Tight feedback loops

**Special Cases**: Hardware (see `phase_1.md`), regulatory (compliance questions), huge scope (narrow to 3-5 features)

---

## Document Format

Output `requirements.md` as clean Markdown:
- 2000-3500 words typical
- Readable by non-technical stakeholders
- Specific enough for design/dev teams
- Include tables where helpful (requirements, metrics, risks)
- Clear section headers and hierarchies

---

## Error Handling

### Tool Failures

**If Read fails**:
- Check file path is correct
- Ask user: "Cannot find [file]. Does it exist? Should I check a different location?"

**If Edit fails** ("old_string not found"):
- Verify old_string matches file exactly (check spacing, line breaks)
- If file changed since last read: Re-read file, try Edit again
- If still fails: Use Write to recreate file (warn user first)

**If Write fails** (permissions, directory):
- Check parent directory exists
- Ask user: "Cannot write to [path]. Do you have permissions? Should I use different location?"

**If AskUserQuestion gets no answer**:
- Wait for user response
- Don't proceed without confirmation when required

### Recovery Strategy

1. **Always Read before Edit/Write** - Prevents stale data
2. **If uncertain**: Ask user, don't guess
3. **If blocked**: Explain what you need to proceed

---

## Starting the Workflow

When user invokes this skill, check for brief.md:

1. **If brief.md exists**: Start Phase 1 automatically
2. **If no brief.md**: Ask user to create it first with basic project notes
3. **If user provides text in chat**: Ask if they want you to create brief.md with that content

Always confirm which phase to start with if unclear.
