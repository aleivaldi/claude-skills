# Best Practices per Claude Skills

Documentazione completa delle best practices ufficiali per creare skills Claude di alta qualità.

---

## 1. Struttura e Organizzazione

### File SKILL.md Obbligatorio

Ogni skill DEVE avere un file `SKILL.md` nella root directory con:

```markdown
---
name: Skill Name
description: Brief description of what the skill does
---

# Rest of the skill prompt
```

### Frontmatter Obbligatorio

**name** (obbligatorio):
- Max 50 caratteri
- Descrittivo e specifico
- NO "Claude" o "Skill" nel nome (è implicito)
- Esempi buoni: "Generate API Documentation", "Analyze Code Performance"
- Esempi cattivi: "Claude Skill for Docs", "My Skill"

**description** (obbligatorio):
- 100-200 caratteri idealmente (max 280)
- Deve rispondere a:
  - Cosa fa la skill?
  - Quali sono gli input?
  - Quali sono gli output?
  - Quando usarla?
- Esempi buoni: "Analyzes Python code for performance bottlenecks, suggests optimizations, and generates detailed report with metrics. Input: .py files. Output: analysis.md"
- Esempi cattivi: "Helps with code", "A useful skill for developers"

### Organizzazione File

**Skill Semplice** (single-task, lineare):
```
skill-name/
  SKILL.md
```

**Skill Media** (multi-step, require template):
```
skill-name/
  SKILL.md
  templates/
    template.md
```

**Skill Complessa** (multi-fase, documentazione estesa):
```
skill-name/
  SKILL.md              # Overview e orchestrazione
  phase_1.md            # Fase 1 dettagliata
  phase_2.md            # Fase 2 dettagliata
  templates/
    template-1.md
    template-2.md
  docs/                 # Documentazione riferimento
    reference.md
  defaults.md           # Default values e assumptions
  examples/             # Esempi concreti
    example-1.md
```

**Principi**:
- SKILL.md è sempre l'entry point
- File ausiliari per dettagli, non per overview
- Template separati dal prompt
- Documentation separata da instructions

---

## 2. Writing Effective Prompts

### Principio Fondamentale: Specificità

❌ **Vago**: "Process the input appropriately"
✅ **Specifico**: "Read input.json with Read tool, parse JSON, validate schema against schema.json"

❌ **Vago**: "Handle errors gracefully"
✅ **Specifico**: "If Read fails: verify path exists, check permissions, ask user for alternative location"

### Struttura Prompt Efficace

```markdown
# Skill Name

## Il Tuo Compito / Your Task

[1-2 paragrafi introduttivi che spiegano:
- Cosa fa la skill
- Perché esiste
- Overview del processo se multi-step]

---

## [Workflow/Fase Name]

### Quando Usarlo/Usarla / When to Use

[Lista specifica di situazioni]
- User asks to [specific action]
- User provides [specific input]
- [Specific condition] is met

### Processo / Process

[Passi numerati, actionable, specifici]

1. **[Step Name]**: [Specific action] using [specific tool]
   - [Sub-action if needed]
   - [Conditional: if X then Y, else Z]

2. **[Step Name]**: [Specific action]
   - Output: [Exactly what this produces]

### Regole / Rules

[Lista ✅ DO e ❌ DON'T chiara]
- ✅ ALWAYS [specific action]
- ✅ Use [tool] for [purpose]
- ❌ NEVER [anti-pattern]
- ❌ DON'T [common mistake]

---

## Output Finale / Final Output

[Descrizione chiara e specifica del deliverable]
```

### Imperativo e Diretto

✅ **Buono**:
- "Read the file with Read tool"
- "Create documentation.md with Write tool"
- "Ask user to clarify scope using AskUserQuestion"

❌ **Cattivo**:
- "You should probably read the file"
- "Consider creating documentation"
- "Maybe ask the user about scope"

### Condizioni Esplicite

✅ **Buono**:
```markdown
If brief.md exists:
  - Read it with Read tool
  - Analyze content
  - Proceed to Phase 2
Else:
  - Ask user to create it
  - Wait for confirmation
  - Then proceed
```

❌ **Cattivo**:
```markdown
Handle the brief file appropriately
```

---

## 3. Tool Usage

### Regola d'Oro: Esplicità Assoluta

**SEMPRE specificare**:
- Quale tool usare
- Con quali parametri
- In quale ordine
- Perché

### Pattern Corretti

#### Read Before Edit (CRITICO)

✅ **Sempre**:
```markdown
1. Read existing_file.md with Read tool
2. Edit existing_file.md with Edit tool (replace old_string with new_string)
```

❌ **Mai**:
```markdown
Edit the file if it exists
```

**Rationale**: Edit senza Read causa errori con dati obsoleti o old_string non trovato.

#### Write for New, Edit for Existing

✅ **Corretto**:
```markdown
If file is new:
  - Use Write tool to create it
Else:
  - Use Read tool to read current content
  - Use Edit tool to modify it
```

❌ **Sbagliato**:
```markdown
- Use Write tool to update the file
```

**Rationale**: Write sovrascrive completamente, Edit preserva contenuto non modificato.

#### AskUserQuestion for Confirmations

✅ **Corretto**:
```markdown
Before proceeding, use AskUserQuestion to confirm:
- Question: "Should I proceed with deletion?"
- Options: ["Yes, delete", "No, keep it"]

Wait for user response. Do not proceed without confirmation.
```

❌ **Sbagliato**:
```markdown
Ask if user wants to proceed
```

#### Bash for System Operations ONLY

✅ **Corretto**:
```markdown
Use Bash tool for:
- git operations: git status, git commit
- package management: npm install, pip install
- system commands: mkdir, cd
```

❌ **Sbagliato**:
```markdown
Use Bash tool for:
- Reading files: cat file.txt (use Read tool instead)
- Writing files: echo "content" > file.txt (use Write/Edit instead)
- Searching: grep "pattern" *.js (use Grep tool instead)
```

### Tool Sequencing

**Operazioni Indipendenti** → Parallelo:
```markdown
Read file1.md and file2.md in parallel
```

**Operazioni Dipendenti** → Sequenziale:
```markdown
1. Read config.json (need content first)
2. Based on config, Edit settings.json (depends on step 1)
3. Validate with Bash: npm run validate (depends on step 2)
```

### Error Handling per Tool

Ogni tool usage deve avere error handling:

```markdown
## Gestione Errori / Error Handling

### If Read fails
- Verify file path is correct
- Check if file exists using Bash: ls [path]
- Ask user: "Cannot find [file]. Does it exist? Should I check a different location?"

### If Edit fails (old_string not found)
- Re-read the file (it may have changed)
- Verify old_string matches exactly (check whitespace, newlines)
- If still fails: explain to user what you're trying to replace and ask for guidance

### If Write fails (permissions)
- Check parent directory exists
- Verify write permissions
- Ask user: "Cannot write to [path]. Should I use a different location?"

### If AskUserQuestion gets no response
- Wait for user response
- Do not proceed with critical actions without confirmation
- Remind user what decision is needed
```

---

## 4. Examples and Anti-Patterns

### Usa Esempi Concreti

✅ **Buono**:
```markdown
<example>
User: "Create API documentation for my Express.js endpoints"