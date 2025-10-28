# Template: Brief Strutturato

Questo template definisce la struttura per il documento **brief-structured.md** creato nella Fase 2.

## Caratteristiche del Documento

Il documento deve essere:
- Completo e leggibile autonomamente
- Condivisibile con stakeholder
- Privo di riferimenti al processo di creazione
- Scritto con tono professionale narrativo

---

## Struttura (9 Sezioni)

```markdown
# [NOME PROGETTO] - Brief Strutturato

## 1. Problema

[Descrizione completa del problema che il progetto risolve]
[Chi è affetto da questo problema]
[Gravità e impatto del problema]
[Situazione attuale e pain points]

## 2. Utenti e Contesto

### Utenti Primari
Per ognuno:
[Tipo di utente, ruolo, competenze tecniche]
[Ambiente, eventuali strumenti utilizzati]
[Quanti utenti (ordine di grandezza)]
[Contesto d'uso (dove, quando, come)]

### Utenti Secondari (se applicabile)
Per ognuno:
[Altri stakeholder o utenti indiretti]

## 3. Obiettivi

### Obiettivo Primario
[Cosa si vuole ottenere con questo MVP/PoC]

### Obiettivi Secondari
- [Obiettivo 2]
- [Obiettivo 3]

### Criteri di Successo
[Come misuriamo se abbiamo raggiunto gli obiettivi]

## 4. Vincoli

### Vincoli Tecnici
[Tecnologie richieste o da evitare]
[Sistemi esistenti con cui integrarsi]
[Piattaforme target]

### Vincoli Organizzativi
[Team disponibile, competenze]
[Processi aziendali da rispettare]
[Stakeholder e approvazioni necessarie]

### Vincoli di Business
[Timeline e deadline]
[Budget disponibile]
[Priorità aziendali]

## 5. Assunzioni

Le seguenti assunzioni sono state fatte per definire l'MVP:

- **[Aspetto 1]**: [Assunzione fatta]. Rationale: [Perché questa assunzione è ragionevole per MVP]
- **[Aspetto 2]**: [Assunzione fatta]. Rationale: [Perché questa assunzione è ragionevole per MVP]
- **[Aspetto 3]**: [Assunzione fatta]. Rationale: [Perché questa assunzione è ragionevole per MVP]

[Nota: Usa defaults.md per scegliere assunzioni pragmatiche per MVP]

## 6. Funzionalità Principali

### Funzionalità 1: [Nome]
[Descrizione dettagliata della funzionalità]
[Come l'utente la usa]
[Perché è importante]

### Funzionalità 2: [Nome]
[Descrizione dettagliata della funzionalità]
[Come l'utente la usa]
[Perché è importante]

### Funzionalità 3: [Nome]
[Descrizione dettagliata della funzionalità]
[Come l'utente la usa]
[Perché è importante]

[Tipicamente almeno 2-5 funzionalità core per MVP]

## 7. Workflow Principali

### Workflow 1: [Nome]
1. [Step 1]
2. [Step 2]
3. [Step 3]
4. [Risultato]

### Workflow 2: [Nome]
1. [Step 1]
2. [Step 2]
3. [Step 3]
4. [Risultato]

[Descrivere almeno 2-4 workflow principali che coprono i casi d'uso più comuni]

## 8. Scope MVP

### Incluso in MVP v1
- [Funzionalità/capability inclusa]
- [Funzionalità/capability inclusa]
- [Funzionalità/capability inclusa]

### Esplicitamente NON Incluso in v1
- [Funzionalità esclusa] → [perché: future phase / workaround manuale accettabile / dipende da feedback v1]
- [Funzionalità esclusa] → [perché]
- [Funzionalità esclusa] → [perché]

### Fasi Future (dopo v1)
**v2 (basato su apprendimento v1)**:
- [Enhancement possibile]
- [Integrazione possibile]

**v3+**:
- [Nice-to-have dallo scoping originale]

## 9. Domande Aperte

[Lista di decisioni ancora da prendere o aspetti da validare]
[Solo se ci sono decisioni veramente posticipabili dopo MVP]
[Se non ce ne sono, scrivere: "Nessuna domanda aperta critica per MVP v1"]
```

---

## Linee Guida di Scrittura

### ✅ FARE
- Scrivere come documento completo e leggibile autonomamente
- Integrare risposte e assunzioni in modo seamless
- Usare paragrafi narrativi con tono professionale
- Rendere il documento condivisibile con stakeholder
- Scrivere come se fosse il primo e unico documento del progetto

### ❌ NON FARE
- NO markers tipo [CONFERMATO], [AGGIUNTO], [MODIFICATO], [ASSUNTO]
- NO riferimenti a "Q[N]", "risposta alla domanda N", "come da Q3"
- NO riferimenti a "defaults.md", "template.md", o altri file tecnici
- NO linguaggio tipo "Basato su brief.md", "Come indicato in brief.md"
- NO riferimenti al processo di creazione del documento
- NO linguaggio "diff-like" che mostra cosa è cambiato
