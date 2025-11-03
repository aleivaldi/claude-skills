---
name: generating-business-model-canvas
description: Genera Business Model Canvas completo da brief strutturato e analisi competitor opzionale. Crea business-model-canvas.md con i 9 blocchi standard (Customer Segments, Value Propositions, Channels, Customer Relationships, Revenue Streams, Key Resources, Key Activities, Key Partners, Cost Structure). Sistema di feedback flessibile (modifica diretta file, commenti inline, feedback chat). Output stand-alone condivisibile con stakeholder. Supporta progetti software, hardware e misti.
---

# Generating Business Model Canvas

## Il Tuo Compito

Genera un Business Model Canvas completo in **2 formati** partendo dal brief strutturato e opzionalmente dall'analisi competitor.

**Input**:
- **brief-structured.md** (obbligatorio) - Brief strutturato con problema, utenti, obiettivi, funzionalità
- **competitor-analysis.md** (opzionale) - Analisi competitor per insights e differenziazione

**Output** (2 file generati):

1. **business-model-canvas.md** (150-300 righe) - Versione completa sintetica
   - Formato: Bullet points + tabelle per sezioni chiave
   - Uso: Documento stand-alone leggibile

2. **business-model-canvas-visual.md** (~100-150 righe) - Versione tabellare visuale
   - Formato: Layout canvas canonico in tabella markdown
   - Uso: Visual reference per pitch deck, workshop

**I 9 blocchi del BMC** (in entrambi i file):
1. Customer Segments (Chi)
2. Value Propositions (Cosa)
3. Channels (Come raggiungiamo)
4. Customer Relationships (Come interagiamo)
5. Revenue Streams (Quanto guadagniamo)
6. Key Resources (Di cosa abbiamo bisogno)
7. Key Activities (Cosa facciamo)
8. Key Partners (Con chi collaboriamo)
9. Cost Structure (Quanto costa)

---

## Regola Linguistica

**Adatta la lingua al file brief-structured.md:**
- Se brief-structured.md è in italiano → rispondi in italiano
- Se brief-structured.md è in inglese → rispondi in inglese
- Se brief-structured.md è in altra lingua → rispondi in quella lingua

Rispondi in una lingua diversa solo se l'utente lo richiede esplicitamente.

---

## Esempi di Utilizzo

<example>
Context: Utente ha brief-structured.md completo e vuole creare BMC
User: "Genera il Business Model Canvas per il progetto"
Assistant: Leggo brief-structured.md con Read tool per analizzare il contenuto...

[Dopo lettura]

Ho analizzato il brief strutturato. Verifico se esiste anche competitor-analysis.md...

[Dopo verifica]

Procedo a generare business-model-canvas.md con i 9 blocchi del BMC.

[Crea business-model-canvas.md con Write tool]

Ho creato business-model-canvas.md. Il documento include:
- 3 Customer Segments identificati
- Value Proposition unica e differenziante
- 4 Channels per raggiungere i clienti
- Revenue model chiaro (subscription + freemium)
- Cost structure realistica per MVP

Il Business Model Canvas riflette correttamente il progetto?
</example>

<example>
Context: Utente vuole modificare BMC dopo creazione
User: "Il documento è buono ma vorrei modificare la sezione Revenue Streams"
Assistant: Come vuoi procedere con le modifiche?
[Usa AskUserQuestion con 3 metodi: Modifica Diretta / Commenti Inline / Feedback Chat]

User: "Preferisco feedback in chat"
Assistant: Perfetto. Dimmi quali modifiche vuoi fare alla sezione Revenue Streams.

User: "Cambia subscription mensile da €29 a €19 per MVP"
Assistant: [Legge file con Read, applica modifica con Edit]

Ho cambiato il prezzo subscription da €29 a €19. Altre modifiche?

User: "No, perfetto così"
Assistant: Ottimo! business-model-canvas.md è completo e approvato. Questa skill ha terminato il suo compito.
</example>

---

## Convenzione Nomi File

Durante il workflow, questi file vengono utilizzati:

### 1. brief-structured.md (input obbligatorio)
- **Creato da**: Skill `generating-structured-brief`
- **Letto da**: Questa skill
- **Scopo**: Fonte primaria per generare BMC (problema, utenti, obiettivi, funzionalità, scope)

### 2. competitor-analysis.md (input opzionale)
- **Creato da**: Skill `competitor-market-analysis` o manualmente
- **Letto da**: Questa skill (se presente)
- **Scopo**: Insights su competitor per differenziazione e posizionamento

### 3. business-model-canvas.md (output - versione completa)
- **Creato da**: Questa skill
- **Modificato da**: Skill o utente (iterazioni)
- **Formato**: 150-300 righe, bullet points + tabelle
- **Scopo**: Documento stand-alone completo e leggibile con i 9 blocchi del BMC.
- **Uso**: Documento di lavoro, condivisibile con stakeholder/investitori/team
- **Ciclo di vita**: Modificato fino a quando l'utente non lo approva.

### 4. business-model-canvas-visual.md (output - versione tabellare)
- **Creato da**: Questa skill (generato insieme al file completo)
- **Modificato da**: Skill (si aggiorna automaticamente quando si modifica il file completo)
- **Formato**: ~100-150 righe, layout tabellare canvas canonico
- **Scopo**: Visual reference con disposizione classica BMC (Partners sx, Customer dx)
- **Uso**: Copy/paste per pitch deck slide, workshop, presentazioni
- **Ciclo di vita**: Aggiornato automaticamente quando si modifica business-model-canvas.md

---

## Processo Principale

### Quando Usare Questa Skill
- Hai **brief-structured.md** completo
- Necessiti di **Business Model Canvas** per strategia business
- Vuoi documento condivisibile con **stakeholder/investitori**
- Devi validare **sostenibilità economica** del progetto
- Opzionalmente hai **competitor-analysis.md** per insights

### Processo Rapido

1. **Leggi input** con Read tool:
   - brief-structured.md (obbligatorio)
   - competitor-analysis.md (se presente)
2. **Genera 2 file** con Write tool:
   - business-model-canvas.md (150-300 righe, completo sintetico)
   - business-model-canvas-visual.md (~100-150 righe, layout tabellare)
3. **Chiedi conferma e metodo feedback** all'utente con AskUserQuestion
4. **Gestisci feedback con metodo scelto**:
   - **Metodo A (Modifica Diretta)**: Utente modifica file, skill rileva e valida
   - **Metodo B (Commenti Inline)**: Utente aggiunge marker `<!-- FEEDBACK: ... -->`, skill parsa e applica
   - **Metodo C (Feedback Chat)**: Utente descrive modifiche in chat, skill applica
5. **Itera fino ad approvazione** (aggiorna entrambi i file)
6. **Annuncia completamento**

### Regola Critica

**business-model-canvas.md** (versione completa):
- ✅ **SINTETICO** - 150-300 righe totali (BMC tradizionale sta in 1-2 pagine)
- ✅ **Formato bullet points** - NO paragrafi narrativi lunghi
- ✅ **3-7 punti chiave per blocco** - Essenziale, no dettagli eccessivi
- ✅ **Tabelle markdown** per Revenue, Channels, Partners, Cost
- ✅ **Completo e autosufficiente** - Tutti i 9 blocchi del BMC compilati
- ✅ **Basato su dati concreti** - Usa info da brief-structured.md, non generici
- ✅ **Realistico per fase MVP** - Revenue e Cost coerenti con scope MVP

**business-model-canvas-visual.md** (versione tabellare):
- ✅ **ULTRA-SINTETICO** - ~100-150 righe (layout canvas canonico)
- ✅ **Tabella unica** con disposizione blocchi classica (Partners sx, Customer dx)
- ✅ **3-5 punti per blocco** - Ultra-essenziale per visualizzazione
- ✅ **Copy/paste ready** per pitch deck slide

**Entrambi i file**:
- ✅ Tono professionale, condivisibili con stakeholder/investitori
- ❌ NO markers o riferimenti al processo di creazione
- ❌ NO sezioni vuote o "TBD"
- ❌ NO narrativo lungo - BMC è strumento visuale

**Per dettagli completi del processo**: Vedi `bmc-generation.md`

---

## Materiali di Riferimento

**Processi Dettagliati**:
- `bmc-generation.md` - Generazione BMC step-by-step, 9 blocchi dettagliati, iterazioni, approvazioni

**Template**:
- `templates/bmc-template.md` - Struttura completa BMC con i 9 blocchi e linee guida

**Supporto**:
- `defaults.md` - Default pragmatici per progetti MVP (pricing, cost structure, channels tipici)

---

## Regole Chiave

### Processo Iterativo
- Genera business-model-canvas.md stand-alone
- Loop feedback fino ad approvazione (3 metodi supportati)
- Traccia modifiche in chat, mantieni documento pulito (no markers nel body)
- Suggerisci skill `generating-requirements-document` se utente vuole requirements tecnici

### Uso Tool (⚠️ SEQUENZA CRITICA)
- ✅ **SEMPRE** Read prima di Edit/Write (previene errori dati obsoleti)
- ✅ Write per business-model-canvas.md nuovo
- ✅ Edit per modifiche successive (sempre Read prima)
- ✅ AskUserQuestion per conferme
- ❌ **MAI** Write su file esistenti (usa Edit)
- ❌ **MAI** Edit senza Read prima
- ❌ **MAI** procedere senza conferma utente quando richiesta

### BMC Pragmatico
- Usa defaults sensati per MVP (vedi `defaults.md`)
- Revenue model semplice inizialmente (es. subscription, one-time, freemium)
- Cost structure realistica (team, infra, tools)
- L'utente può sempre fare override

### Trasparenza
- Dichiara assunzioni con rationale
- Mostra ragionamento per i default
- Segnala conflitti esplicitamente (es. revenue model incompatibile con target market)

### Efficienza
- Referenzia file, non ripetere contenuti
- Loop di feedback stretti
- Chiedi conferma una volta, non multiple

---

## Uso Tool (⚠️ SEQUENZA CRITICA)

### Generazione BMC
1. ✅ **Read** brief-structured.md (obbligatorio)
2. ✅ **Read** competitor-analysis.md (se presente, verifica esistenza prima)
3. ✅ **Write** business-model-canvas.md (file nuovo)
4. ✅ **AskUserQuestion** per conferma e metodo feedback

### Iterazioni (se richieste)
1. ✅ **SEMPRE Read** business-model-canvas.md prima di Edit
2. ✅ **Edit** per applicare modifiche
3. ✅ **Read** dopo Edit per verificare
4. ✅ **AskUserQuestion** per ri-conferma

### Best Practices
- ❌ **MAI** Write su file esistenti (usa Edit)
- ❌ **MAI** Edit senza Read prima (dati obsoleti)
- ✅ Verifica esistenza file opzionali prima di Read
- ✅ Gestisci fallimenti tool con fallback paths (vedi Gestione Errori)

---

## Gestione Errori

### Fallimenti Tool

**Se Read brief-structured.md fallisce**:
- Verifica percorso corretto
- Chiedi utente: "Non trovo brief-structured.md. Esiste? Hai usato skill `generating-structured-brief` per crearlo?"
- Suggerisci: "Posso aiutarti a crearlo con skill `generating-structured-brief` prima di generare il BMC"

**Se Read competitor-analysis.md fallisce** (opzionale):
- Non bloccare: "competitor-analysis.md non trovato, procedo senza analisi competitor"
- Chiedi: "Vuoi includere analisi competitor? Posso aiutarti con skill `competitor-market-analysis`"

**Se Edit fallisce** ("old_string not found"):
- Verifica old_string corrisponde esattamente (controlla spaziatura, line breaks)
- Se file cambiato da ultimo Read: Re-read file, riprova Edit
- Se ancora fallisce: Usa Write per ricreare (avvisa utente prima)

**Se Write fallisce** (permessi, directory):
- Verifica directory padre esiste
- Chiedi utente: "Non posso scrivere in [path]. Hai permessi? Devo usare posizione diversa?"

**Se AskUserQuestion non riceve risposta**:
- Attendi risposta utente
- Non procedere senza conferma quando richiesta

### Strategia di Recupero
1. **Sempre Read prima di Edit/Write** - Previene dati obsoleti
2. **Se incerto**: Chiedi utente, non indovinare
3. **Se bloccato**: Spiega cosa ti serve per procedere
4. **File opzionali**: Non bloccare generazione se mancano

---

## Avvio Workflow

Quando l'utente invoca questa skill:

1. **Verifica brief-structured.md esiste**:
   - **Se esiste**: Procedi con generazione BMC
   - **Se non esiste**: Chiedi all'utente di crearlo prima con skill `generating-structured-brief`

2. **Verifica competitor-analysis.md** (opzionale):
   - **Se esiste**: Includi insights competitor nel BMC
   - **Se non esiste**: Procedi senza, genera BMC ugualmente

3. **Genera business-model-canvas.md** e chiedi feedback

4. **Itera fino ad approvazione** usando metodo feedback scelto dall'utente

---

## Output Finale

Il deliverable di questa skill sono **2 file** complementari:

### 1. business-model-canvas.md (Versione Completa)
Documento **sintetico** (150-300 righe), stand-alone, professionale.

**Caratteristiche**:
- **Formato**: Bullet points + tabelle markdown per sezioni chiave
- **Lunghezza**: 150-300 righe totali (1-2 pagine stampate)
- **Contenuto**: 9 blocchi completi, 3-7 punti chiave per blocco
- **Dati**: Concreti dal brief strutturato (no generici)
- **Dettaglio**: Tabelle per Revenue, Channels, Partners, Cost

**Usi**:
- Documento di lavoro completo
- Allineamento team su strategia business
- Validazione sostenibilità economica
- Planning go-to-market dettagliato

### 2. business-model-canvas-visual.md (Versione Tabellare)
Layout **tabellare visuale** (~100-150 righe) con disposizione canvas canonico.

**Caratteristiche**:
- **Formato**: Tabella unica con layout classico BMC
- **Lunghezza**: ~100-150 righe (ultra-sintetico)
- **Contenuto**: 9 blocchi, 3-5 punti essenziali per blocco
- **Layout**: Partners a sx, Customer a dx (come canvas originale)
- **Copy/paste ready**: Formattato per pitch deck slide

**Usi**:
- Pitch deck per investitori (copy/paste in slide)
- Workshop strategia business (visual reference)
- Executive summary visuale
- Presentazioni stakeholder

**Entrambi i file**:
- Condivisibili con stakeholder/investitori/team
- Dati concreti, pricing realistico MVP
- Differenziazione da competitor (se competitor-analysis.md presente)

Se l'utente necessita di **requirements.md tecnico completo** (architettura, elementi sistema, sottoprogetti), suggerisci di usare la skill `generating-requirements-document`.

---

## Gestione Metodi di Feedback

La skill supporta **3 metodi** per fornire feedback su business-model-canvas.md (come `generating-structured-brief`):

### Metodo A: Modifica Diretta del File
**Quando**: Hai molte modifiche (4+) o preferisci il tuo editor

**Come funziona**:
1. Utente modifica direttamente `business-model-canvas.md`
2. Salva e dice alla skill "ho finito" o "rivedi"
3. Skill rileva modifiche, mostra riepilogo, chiede conferma

### Metodo B: Commenti Inline per Discussione
**Quando**: Hai dubbi su alcune parti e vuoi discuterle

**Come funziona**:
1. Aggiungi marker `<!-- FEEDBACK: [descrizione] -->` dove hai dubbi
2. Skill legge commenti, discute, applica modifiche concordate
3. Skill rimuove marker dopo applicazione

### Metodo C: Feedback Testuale in Chat
**Quando**: Hai 1-3 modifiche rapide e puntuali

**Come funziona**:
1. Descrivi modifiche in chat (es. "Sezione Revenue: cambia €29 in €19")
2. Skill applica con Edit tool, mostra diff
3. Skill chiede conferma

**Quale metodo scegliere?** Vedi dettagli in `bmc-generation.md` sezione "Metodi di Feedback".
