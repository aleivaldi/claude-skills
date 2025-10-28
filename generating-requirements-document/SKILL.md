---
name: Generating Requirements Document
description: Genera documento completo di requisiti tecnici da brief strutturato. Supporta input flessibili (brief-structured + opzionalmente competitor-analysis, research tecnico, altri documenti). Include executive summary, visione, competitive landscape, target market, architettura con diagramma, dettaglio elementi sistema (web/backend/hardware/landing con strutture differenziate), sottoprogetti parallelizzabili con criticità/priorità/dipendenze, PoC critici. Requisiti dettagliati adattati alla fase (PoC focus fattibilità vs MVP focus valore vs Production requisiti completi). Output: requirements.md (4000-15000 parole).
---

# Generating Requirements Document

## Il Tuo Compito

Genera un documento completo di requisiti tecnici (**requirements.md**) partendo da brief strutturato e opzionalmente altri documenti di supporto.

**Input**:
- **brief-structured.md** (obbligatorio) - Documento strutturato con problema, utenti, obiettivi, funzionalità, scope MVP
- **competitor-analysis.md** (opzionale) - Analisi competitor approfondita
- **Research tecnico** (opzionale) - Documenti di ricerca, PoC precedenti, validazioni tecniche
- **Altri documenti** (opzionale) - Qualsiasi documento rilevante da integrare

**Output**: requirements.md completo (4000-15000 parole) con:
- Executive summary e visione
- Competitive landscape
- Target market
- Architettura sistema con diagramma
- Dettaglio elementi (web app, backend, hardware, landing page - strutture differenziate)
- Sottoprogetti parallelizzabili (criticità, priorità, dipendenze)
- PoC critici da validare
- Requisiti adattati alla fase corrente (PoC/MVP/Beta/Production)

---

## Quando Usare Questa Skill

- Hai **brief-structured.md** completo e approvato
- Serve **documentazione tecnica completa** per progetto
- Necessiti **architettura dettagliata** con elementi sistema
- Devi identificare **sottoprogetti parallelizzabili** per team
- Hai **PoC critici** da validare
- Vuoi **requisiti adattati alla fase** (PoC vs MVP vs Production)

---

## Input Flessibile

Questa skill supporta **input multipli** per generare requirements più completo:

### Input Obbligatorio
- **brief-structured.md**: Deve esistere ed essere completo

### Input Opzionali
- **competitor-analysis.md**: Se presente, integrato in sezione Competitive Landscape
- **research/** directory: Documenti di ricerca tecnica integrati dove rilevante
- **Altri .md files**: Qualsiasi documento pertinente indicato dall'utente

### Workflow Integrazione
1. Leggi brief-structured.md (base)
2. Verifica presenza documenti opzionali
3. Integra informazioni da tutti i documenti disponibili
4. Genera requirements.md completo

---

## Output: requirements.md

Documento completo con struttura adattabile:

**Sezioni Sempre Presenti**:
1. Executive Summary e Visione
2. Target Market
3. Requisiti per Fase Corrente (adattati a PoC/MVP/Production)
4. Architettura Sistema (con diagramma)
5. Scope
6. Vincoli
7. Metriche di Successo
8. Next Steps

**Sezioni Opzionali** (se applicabili):
- Dettaglio Elementi Sistema (se sistema complesso)
- Sottoprogetti e Parallelizzazione (se progetto grande)
- PoC e Validazioni Critiche (se PoC da validare)
- Competitive Landscape (sempre basic, approfondito se competitor-analysis.md presente)

**Lunghezza**: 4000-15000 parole (dipende da complessità progetto)

---

## Processo Rapido

1. **Leggi brief-structured.md** (obbligatorio)
2. **Verifica documenti opzionali** (competitor-analysis.md, research/, etc)
3. **Identifica fase corrente** (PoC/MVP/Beta/Production)
4. **Genera requirements.md** usando template
5. **Adatta requisiti alla fase** (es. PoC → focus fattibilità, no performance)
6. **Review completezza**
7. **Chiedi conferma** all'utente con AskUserQuestion
8. **Itera se necessario**

**Per dettagli completi del processo**: Vedi `requirements-generation.md`

---

## Adattamento Requisiti per Fase

**PoC (Proof of Concept) - Focus Fattibilità**:
- Performance: "Non rilevante per PoC"
- Availability: "Best effort"
- Security: "Basic auth sufficiente"
- Scale: "5-10 utenti di test"

**MVP - Focus Validazione Valore**:
- Performance: "<2 sec page load"
- Availability: "Business hours (9-6)"
- Security: "Standard (HTTPS, auth)"
- Scale: "50-100 utenti"

**Production - Requisiti Completi**:
- Performance: "<1 sec page load, P95 <2 sec"
- Availability: "99.9% uptime"
- Security: "Production-grade, audit log"
- Scale: "10k+ utenti concorrenti"

---

## Materiali di Riferimento

**Processi Dettagliati**:
- `requirements-generation.md` - Processo completo step-by-step, integrazione multi-documento, adattamento fase

**Template**:
- `templates/requirements-template.md` - Template completo con 12 sezioni, strutture differenziate elementi, linee guida

**Supporto**:
- `defaults.md` - Default pragmatici MVP (architettura, scala, sicurezza, performance, hardware IoT)

**Skill Correlate**:
- `generating-structured-brief` - Per creare brief-structured.md iniziale
- `competitor-market-analysis` - Per analisi competitor approfondita da integrare

---

## Regole Chiave

### Input Multipli
- brief-structured.md è **obbligatorio**
- Altri documenti sono **opzionali** ma integrati se presenti
- Chiedi all'utente se ci sono documenti da considerare

### Requisiti Adattati
- **Identifica sempre la fase corrente** (chiedi se non chiaro)
- Adatta requisiti non-funzionali alla fase
- Es. PoC non necessita requisiti production-grade

### Architettura Dettagliata
- Diagramma ASCII obbligatorio (semplice ma chiaro)
- Dettaglio elementi solo se sistema complesso
- Strutture differenziate: web app ≠ backend ≠ hardware ≠ landing page

### Sottoprogetti
- Identifica parallelizzazione possibile
- Marca criticità (🔴 Alta / 🟡 Media / 🟢 Bassa)
- Marca priorità (P0 Bloccante / P1 Importante / P2 Nice-to-have)
- Evidenzia dipendenze

### Completezza vs Pragmatismo
- Documento **completo** ma non eccessivo
- Include solo sezioni **pertinenti al progetto**
- Es. Sottoprogetti solo se progetto grande
- Es. PoC solo se validazioni critiche

---

## Uso Tool (⚠️ SEQUENZA CRITICA)

- ✅ **SEMPRE** Read prima di Edit/Write
- ✅ Verifica presenza documenti opzionali con Read
- ✅ AskUserQuestion per conferme
- ❌ **MAI** procedere senza conferma utente

---

## Gestione Errori

**Se brief-structured.md non esiste**:
- Chiedi utente: "Non trovo brief-structured.md. Vuoi crearlo prima con skill `generating-structured-brief`?"

**Se documenti opzionali menzionati ma non trovati**:
- Chiedi utente: "Hai menzionato [documento] ma non lo trovo. Devo cercarlo altrove?"

**Se fase corrente non chiara**:
- Chiedi utente con AskUserQuestion: "Qual è la fase corrente del progetto? (PoC/MVP/Beta/Production)"

---

## Output Finale

Il deliverable di questa skill è **requirements.md**: un documento tecnico completo, professionale, utilizzabile per:
- Architettura e design
- Planning sottoprogetti
- Comunicazione con team development
- Decisioni tecniche
- Validazioni PoC
- Onboarding team
