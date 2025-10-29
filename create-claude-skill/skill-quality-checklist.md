# Skill Quality Checklist

Usa questa checklist per validare qualità e completezza di una skill Claude.

---

## 1. Frontmatter (OBBLIGATORIO)

- [ ] **File SKILL.md esiste** nella root directory della skill
- [ ] **Frontmatter presente** con delimitatori `---`
- [ ] **Campo `name` presente**
  - [ ] Max 50 caratteri
  - [ ] Descrittivo e specifico
  - [ ] NO "Claude" o "Skill" nel nome
- [ ] **Campo `description` presente**
  - [ ] 100-200 caratteri idealmente (max 280)
  - [ ] Spiega cosa fa la skill
  - [ ] Specifica input attesi
  - [ ] Specifica output generati
  - [ ] Indica quando usarla

**Esempi Frontmatter Valido**:
```markdown
---
name: Generate API Documentation
description: Analyzes Express.js routes and generates comprehensive API documentation in Markdown. Input: route files. Output: docs/api.md with endpoints, parameters, responses.
---
```

---

## 2. Struttura e Organizzazione

- [ ] **Header H1 principale** presente (stesso testo del `name`)
- [ ] **Sezione "Il Tuo Compito"** spiega obiettivo skill
- [ ] **Workflow/Fasi chiaramente identificati** (se multi-step)
- [ ] **Separatori `---`** usati tra sezioni principali
- [ ] **Gerarchia headers corretta** (H1 > H2 > H3, nessun salto)
- [ ] **Liste numerate** per processi sequenziali
- [ ] **Liste puntate** per features/opzioni non sequenziali

---

## 3. Chiarezza Istruzioni

- [ ] **Ogni step è actionable** (verbo imperativo chiaro)
- [ ] **Nessuna istruzione vaga** (no "handle appropriately", "process as needed")
- [ ] **Condizioni esplicite** (if-then-else ben definiti)
- [ ] **Nessuna assunzione implicita** (tutto è documentato)
- [ ] **Sezione "Quando Usarlo/Usarla"** per ogni workflow
- [ ] **Output atteso specificato** per ogni fase

**Test**: Ogni step può essere eseguito da Claude senza ambiguità?

---

## 4. Tool Usage (CRITICO)

- [ ] **Ogni tool specificato esplicitamente** (no "get the content")
- [ ] **Tool usage pattern corretti**:
  - [ ] Read PRIMA di Edit (sempre)
  - [ ] Write per file nuovi, Edit per esistenti
  - [ ] AskUserQuestion per conferme critiche
  - [ ] Bash SOLO per git/npm/sistema (NO cat/grep/echo)
- [ ] **Sequencing corretto**:
  - [ ] Operazioni indipendenti eseguite in parallelo
  - [ ] Operazioni dipendenti eseguite sequenzialmente
- [ ] **Sezione "Uso Tool"** presente con best practices
- [ ] **Parametri tool specificati** quando rilevante

**Anti-Pattern da Evitare**:
- ❌ "Modify the file" (quale tool?)
- ❌ "Get file content" (Read? Bash cat?)
- ❌ "Update configuration" (come? dove?)

---

## 5. Error Handling

- [ ] **Sezione "Gestione Errori" presente**
- [ ] **Error handling per ogni tool usato**:
  - [ ] Cosa fare se Read fallisce
  - [ ] Cosa fare se Write fallisce
  - [ ] Cosa fare se Edit fallisce (old_string not found)
  - [ ] Cosa fare se Bash comando fallisce
  - [ ] Cosa fare se AskUserQuestion non riceve risposta
- [ ] **Fallback paths specificati** (non lasciare utente bloccato)
- [ ] **Recovery actions actionable** (passi specifici, non vaghi)

---

## 6. Edge Cases

- [ ] **Situazioni non standard anticipate**:
  - [ ] File mancanti
  - [ ] File esistenti quando atteso nuovo
  - [ ] Permessi insufficienti
  - [ ] Input malformato/invalido
  - [ ] Directory non esistenti
- [ ] **Gestione per ogni edge case** è chiara e specifica
- [ ] **Path alternativi documentati**

---

## 7. Esempi e Anti-Pattern

- [ ] **Esempi concreti presenti** per casi complessi
- [ ] **Formato `<example>` usato** quando appropriato
- [ ] **Anti-pattern documentati** (cosa NON fare)
- [ ] **Esempi mostrano tool usage corretto**

---

## 8. Scope e Boundaries

- [ ] **Sezione scope** definisce cosa FA la skill
- [ ] **Sezione scope** definisce cosa NON FA
- [ ] **Riferimenti ad altre skills** quando appropriato
- [ ] **Scope non infinito** (skill non fa troppo)
- [ ] **Responsabilità chiare** e delimitate

---

## 9. Validazione e Feedback

- [ ] **AskUserQuestion usato** per decisioni critiche
- [ ] **Conferme richieste** prima azioni irreversibili
- [ ] **User può intervenire** nei punti chiave
- [ ] **Feedback loop presente** quando appropriato

---

## 10. File Ausiliari (se skill complessa)

Per skills medie/complesse:

- [ ] **Templates separati** in `templates/` directory
- [ ] **Fasi dettagliate** in file `phase_N.md`
- [ ] **Defaults documentati** in `defaults.md`
- [ ] **Reference docs** in `docs/` directory
- [ ] **Esempi complessi** in `examples/` directory
- [ ] **SKILL.md referenzia** file ausiliari correttamente

---

## 11. Output e Deliverable

- [ ] **Sezione "Output Finale" presente**
- [ ] **Deliverable specificato chiaramente**:
  - [ ] Nome file(s) prodotto
  - [ ] Formato e struttura
  - [ ] Contenuto atteso
  - [ ] Dimensione approssimativa se rilevante
- [ ] **Criteri di completamento chiari** (quando skill è finita?)

---

## 12. Linguaggio e Stile

- [ ] **Tono imperativo e diretto** ("Leggi", "Crea", "Valida")
- [ ] **Lingua consistente** (italiano O inglese, non misto)
- [ ] **Sezione "Regola Linguistica"** se multi-lingua
- [ ] **Emoji usati appropriatamente** (✅ ❌ ⚠️ solo per categorizzazione)
- [ ] **Terminologia tecnica corretta** e consistente

---

## 13. Testing e Validazione

- [ ] **Skill testata** con caso reale
- [ ] **Mental simulation eseguita**:
  - [ ] Input realistici → output corretti
  - [ ] Tool sequence funziona
  - [ ] Edge cases gestiti
  - [ ] Nessun dead-end
- [ ] **Test case documentato** (opzionale ma raccomandato)

---

## 14. Maintainability

- [ ] **Struttura modulare** per skills complesse
- [ ] **File non troppo lunghi** (split se > 1000 righe)
- [ ] **Sezioni ben organizzate** e facili da trovare
- [ ] **Changelog presente** se skill è stata modificata (opzionale)
- [ ] **Facile identificare** cosa modificare per aggiornamenti futuri

---

## Score e Valutazione

### Critico (Must-Have) ⚠️

Questi DEVONO essere tutti ✅ per skill funzionante:

1. Frontmatter completo (name + description)
2. Tool usage esplicito
3. Read before Edit pattern
4. Error handling base presente
5. Scope definito

**Se anche solo UNO è ❌ → skill NON è production-ready**

### Importante (Should-Have) 📋

Questi dovrebbero essere ✅ per skill di qualità:

1. Esempi concreti
2. Edge cases gestiti
3. Validazione utente per azioni critiche
4. Output specificato chiaramente
5. Anti-pattern documentati

**Percentuale target: 80%+ ✅**

### Nice-to-Have (Could-Have) ⭐

Questi migliorano qualità ma non essenziali:

1. Changelog/versioning
2. Test cases documentati
3. Examples directory
4. Reference documentation estesa
5. Multiple language support

**Percentuale target: 50%+ ✅**

---

## Azioni Post-Checklist

### Se Score Critico < 100%
→ **NON procedere con deployment**
→ **Fixa issue critici immediatamente**
→ **Re-valida dopo fix**

### Se Score Importante < 80%
→ **Migliora prima di considerare "completa"**
→ **Documenta gap noti**
→ **Pianifica iterazione miglioramenti**

### Se Score Nice-to-Have < 50%
→ **OK per uso interno/testing**
→ **Considera miglioramenti per production**
→ **Itera basandosi su feedback utenti**

---

## Quick Validation

Domande rapide per validation veloce:

1. ❓ **Posso eseguire questa skill senza fare domande?** (tutto è chiaro?)
2. ❓ **So esattamente quali tool usare in ogni step?**
3. ❓ **So cosa fare se qualcosa fallisce?**
4. ❓ **So cosa aspettarmi come output?**
5. ❓ **Ci sono situazioni in cui sarei bloccato?**

Se risposta è "NO" a qualsiasi domanda → skill ha problemi di qualità.

---

## Esempio Validation Report

```markdown
# Validation Report: [Skill Name]

**Data**: 2024-01-15
**Validatore**: [Nome]

## Score Summary

- Critico: 5/5 ✅ (100%)
- Importante: 4/5 ⚠️ (80%)
- Nice-to-Have: 2/5 📋 (40%)

## Issue Critici

Nessuno ✅

## Issue Importanti

- ❌ Manca gestione edge case per file già esistente
- ⚠️ AskUserQuestion non usato per conferma sovrascrittura

## Raccomandazioni

1. **Alta Priorità**: Aggiungere AskUserQuestion prima di sovrascrivere file
2. **Media Priorità**: Documentare edge case file esistente
3. **Bassa Priorità**: Considerare aggiungere examples/ directory

## Verdict

✅ **Approvata per uso con minor fixes** (fixare issue importanti raccomandato)
```
