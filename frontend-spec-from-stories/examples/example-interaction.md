# Example Interactions

Esempi di come la skill interagisce con l'utente durante le varie fasi.

---

## Esempio 1: Proposta Sitemap con Raccomandazione

```
Claude: Ho analizzato le user stories. Identifico 3 aree principali:

**Sitemap proposta:**

/ (Public)
├─ Home
├─ Login
└─ Signup

/app (User Area)
├─ Dashboard
├─ Songs (US-001, US-002)
│  ├─ My Songs (list + player)
│  └─ Create New (wizard)
└─ Account
   └─ Settings

/admin (Admin Panel - separate app)
├─ Dashboard
├─ Users (US-015, US-016)
└─ Analytics

**Rationale:**
- User area flat (2 livelli max) per accesso rapido
- Admin separato per sicurezza + layout diverso
- Songs raggruppa creation + library (flusso comune)
- Max depth: 3 livelli (ottimale per navigazione)

**Navigation:**
- User: sidebar persistent (desktop) / bottom nav (mobile)
- Admin: top nav + sidebar (desktop-first, mobile secondary)

**Mobile specifics:**
- Songs: swipe tra list/player (riduce tap)
- Bottom nav: Dashboard, Songs, Account (3 tab - thumb-friendly)

Breadcrumb solo in Admin (> 2 livelli).

Va bene o preferisci struttura diversa?
```

**User risponde:** "Va bene così"

---

## Esempio 2: Proposta Screen con Componenti Dettagliati

```
Claude: Per la gestione utenti (US-001 a US-005), raccomando pagina unica "Admin > Users" con:

**Layout raccomandato:**
- Tabella principale + filtri in sidebar
- Azioni inline per ogni riga
- Modal per dettagli/edit (mantiene contesto vs pagina separata)

**Componenti interattivi:**
- **4 bottoni per riga:**
  - Edit (matita icon)
  - Delete (trash icon)
  - Disable/Enable (toggle)
  - View Details (eye icon)
- **3 filtri dropdown:**
  - Role (Admin/User/Guest)
  - Status (Active/Disabled)
  - Date Range (Last 7 days/30 days/All time)
- **Search bar** con autocomplete (debounce 300ms)
- **Paginazione** footer: 20 items/page, total count visibile

**Mobile:**
- Tabella → cards swipeable
- Filtri in bottom sheet (tap "Filters" button)
- Azioni in overflow menu (3-dot)

**Gestures mobile:**
- Swipe-left su card per delete (con undo 5 sec)
- Long-press per context menu (Edit/Disable/View)

**Stati:**
- **Loading:** skeleton table (perceived performance migliore vs spinner)
- **Empty:** "Add First User" CTA + "Invite via email" link
- **Error:** toast notification top-right + "Retry" button (non blocca UI)

Va bene o preferisci lista separata + dettagli in pagina dedicata?
```

**User risponde:** "Perfetto, procedi"

---

## Esempio 3: Proposta UX Approach

```
Claude: Per questo tipo di applicazione (SaaS Dashboard con gestione dati), propongo:

**Approccio raccomandato: Task-Focused Navigation**
- Navigation organizzata per task utente (non per entità database)
- Accesso rapido a task frequenti da ogni schermata
- Minimal clicks to complete common actions

**Pro:**
- Riduce cognitive load (utente pensa per "cosa vuole fare")
- Ottimizza per efficienza (task comuni = 1-2 click max)
- Scalabile (nuove features si aggiungono come nuovi task)

**Contro:**
- Richiede buona discovery UX per task meno frequenti

**Alternative:**
A) Entity-Based Navigation (organizzato per tipo di dato: Users, Projects, etc.)
   → Quando: struttura dati è semplice e intuitiva per utente

B) Role-Based Navigation (menu diverso per ogni ruolo)
   → Quando: ruoli hanno workflow completamente diversi

Raccomando Task-Focused perché le user stories mostrano workflow complessi che attraversano multiple entità (US-001 a US-008). Un utente non pensa "voglio vedere Projects" ma "voglio creare una nuova campagna".

Procedo con Task-Focused?
```

**User risponde:** "Sì, Task-Focused va bene"

---

## Esempio 4: Gap Identificato

```
Claude: ⚠️ Ho completato tutte le schermate dalle user stories. Ho identificato 3 gap critici non menzionati:

1. **Utente senza permessi** tenta accesso risorsa protetta
   → **Proposta:** Screen "403 Forbidden"
   - Messaging chiaro: "Non hai i permessi per accedere a questa risorsa"
   - CTA: "Contatta amministratore" + link a dashboard
   - Tracking: log attempt per security audit

2. **Risorsa non trovata** (URL errato o risorsa cancellata)
   → **Proposta:** Screen "404 Not Found"
   - Messaging friendly: "Questa pagina non esiste"
   - Search suggestions basate su URL errato
   - CTA: "Torna alla Dashboard" + link navigazione principale

3. **Session timeout** durante operazione
   → **Proposta:** Modal "Session Expired"
   - Auto-save draft della operazione in corso (se possibile)
   - Re-login inline nel modal (senza perdere contesto)
   - Dopo login: ripristina stato precedente

Aggiungo queste 3 schermate standard? Sono necessarie per un'applicazione production-ready.
```

**User risponde:** "Sì, aggiungile tutte e tre"

---

## Esempio 5: Iterazione da Commenti nel File

```
Claude: Ho letto il file frontend-specifications.md. Ho trovato 3 commenti:

1. Riga 45: "<!-- Dashboard troppo complessa, dividere? -->"
   → **Proposta:** Split in 2 tab:
   - "Overview" tab: metriche chiave + recent activity (quick glance)
   - "Analytics" tab: grafici dettagliati + deep insights
   → **Rationale:** Separa info immediate (check daily) da deep dive (weekly review)

2. Riga 78: "<!-- Manca export users -->"
   → **Proposta:** Aggiungo bottone "Export CSV"
   - Position: top-right toolbar, accanto a search
   - Behavior: esporta users con filtri correnti applicati
   - Columns: tutte quelle visibili in tabella + email (anche se nascosta)

3. Riga 92: "<!-- Mobile: serve offline mode? -->"
   → **Domanda per te:** Offline mode è necessario (critical feature, aumenta scope ~30%) o nice-to-have (post-MVP)?
   - Se critical: aggiungo screen + sync strategy
   - Se nice-to-have: documento in "Future Enhancements" section

Applico modifiche 1 e 2 subito. Mi confermi per 3?
```

**User risponde:** "Post-MVP è ok"

```
Claude: Perfetto. Ho applicato le modifiche:

1. ✅ Dashboard split in 2 tab (Overview + Analytics)
2. ✅ Aggiunto Export CSV button in Admin > Users
3. ✅ Offline mode documentato in sezione "Future Enhancements"

Rileggo il file per verificare... Tutto applicato correttamente.

Altre modifiche o il documento è pronto?
```

---

## Esempio 6: Modifica via Chat

```
User: La schermata "My Songs" deve avere anche un filtro per genere musicale

Claude: Perfetto. Leggo il file corrente...

[Read file]

Attualmente "My Songs" ha:
- Search bar
- Sort by (Date, Title, Plays)

Aggiungo:
- **Filter dropdown: "Genre"**
  - Options: All, Pop, Rock, Jazz, Classical, Electronic, Hip-Hop, Other
  - Position: accanto a Sort dropdown
  - Behavior: filtra in real-time, combinabile con search
  - Mobile: in bottom sheet "Filters & Sort" insieme a sort

Applico la modifica...

[Edit file]

✅ Modificato. Rileggo per verificare...

[Read file to confirm]

Fatto! Il filtro Genre è stato aggiunto a "My Songs" screen. Altro da modificare?
```

---

## Note sui Pattern di Interazione

### Pattern Raccomandazione
**Sempre usare**:
```
Raccomando [opzione] perché [motivo specifico].
Alternative: [A] (quando), [B] (quando).
Preferenza?
```

### Pattern Proposta con Dettagli
**Fornire dettagli già completi**:
- Non: "Serve conferma per delete?"
- Sì: "Propongo modal conferma per delete perché previene errori. Alternative: inline confirm (più veloce ma rischiosa). Raccomando modal."

### Pattern Gap
**Evidenziare con ⚠️** e proporre soluzione:
```
⚠️ Gap identificato: [scenario]
→ Proposta: [soluzione concreta]
→ Rationale: [perché necessario]
Aggiungo?
```

### Pattern Iterazione
**Supportare tutti e 3 i modi**:
1. Edit diretto → riconoscere e chiedere conferma applicazione sistematica
2. Commenti → identificare, risolvere uno per uno
3. Chat → read → edit → read to confirm
