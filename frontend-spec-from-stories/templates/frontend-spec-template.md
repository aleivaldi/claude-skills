# Frontend Specifications - [Project Name]

> **Status:** [Draft/Review/Approved]
> **Version:** [X.Y]
> **Last Updated:** [Date]
> **Derived from:** [User Stories v1.0 / Project Brief]

---

## 1. Overview

**Project:** [Project Name]
**Application Type:** [Web App/Mobile App/Desktop App/Multi-platform]
**UX Approach:** [Chosen approach + brief rationale]
**Target Platforms:** [Desktop/Mobile/Tablet - specify breakpoints if responsive]

---

## 2. User Roles

### [Role Name]
[Brief description of access level and primary goals - 1-2 lines]

### [Role Name]
[Brief description of access level and primary goals - 1-2 lines]

---

## 3. Sitemap

### Visual Structure

```
/ (Public)
├─ /
├─ /login
├─ /signup
├─ /forgot-password
│
/app (Authenticated - User)
├─ /dashboard (home)
├─ /feature-a
│  ├─ /feature-a (list)
│  ├─ /feature-a/:id (detail)
│  └─ /feature-a/new (create)
├─ /feature-b
└─ /settings
   ├─ /settings/profile
   ├─ /settings/account
   └─ /settings/preferences
│
/admin (Authenticated - Admin)
├─ /admin/dashboard
├─ /admin/users
│  ├─ /admin/users (list)
│  └─ /admin/users/:id (detail)
└─ /admin/system
```

### Navigation Levels

- **L0 - Entry Points:** [Description of public pages]
- **L1 - Main Areas:** [Description of primary authenticated sections]
- **L2 - Feature Pages:** [Description of feature-specific pages]
- **L3 - Deep Pages:** [Description of detail/deep pages - max recommended depth]

### Global Navigation

**Primary Nav (always visible):**
- [List of main navigation items]
- **Position:** [sidebar/top bar/bottom bar]
- **Mobile:** [hamburger/bottom nav/tab bar]

**Secondary Nav (contextual):**
- [Where it appears]
- [When it appears]

### Access Matrix

| Path Pattern | Roles | Redirect if Unauthorized |
|-------------|-------|-------------------------|
| / | All | - |
| /login | Guest | /dashboard if authenticated |
| /app/* | User, Admin | /login |
| /admin/* | Admin only | /dashboard |

### Navigation Notes

- **Deep linking:** [Support for direct URLs with auth check]
- **Breadcrumbs:** [Where needed - typically beyond L2]
- **Back behavior:** [Browser back vs app back button]
- **Mobile specifics:** [Gesture navigation, bottom nav behavior, etc.]

---

## 4. Screens Inventory

### [Screen Name]

**Route:** `/path/to/screen` (web) | **Screen ID:** `ScreenName` (mobile)
**Users:** [Role1, Role2]
**Satisfies:** US-001, US-003 | **Platform:** Web + Mobile
**Sitemap Location:** [Path from sitemap - e.g., /app/feature-a/list]

#### Purpose
[1-2 lines describing what this screen does]

#### Layout & Components

**Main Sections:**
- [Section 1]: [Concise description]
- [Section 2]: [Concise description]

**Interactive Elements:**
- **Buttons** ([N] total):
  - [Button 1]: [Action/destination]
  - [Button 2]: [Action/destination]
- **Forms/Inputs** ([N] total): [Type and purpose]
- **Dropdowns/Select**: [List]
- **Other Controls**: checkbox, radio, slider, toggle, context menu, etc.
- **Gestures (mobile):** swipe, long-press, pull-to-refresh, pinch-to-zoom, etc.

**Platform Differences:**
- **Mobile:** [Only if different from web]
- **Web:** [Only if different from mobile]

#### Data Displayed

- **[Field/Section]:** Source (entity.field) - [format/transformation if relevant]
- **[Field/Section]:** Calculated ([formula/logic])

#### Actions

**[Action Name]** (US-XXX)
- **Who:** [Roles that can perform]
- **Trigger:** [Button/gesture/event]
- **Flow:** [Step1 → Step2 → Result]
- **Confirmation:** [Modal/inline - with rationale]
- **States:** Loading/success/error behavior

#### States & Feedback

- **Loading:** [Solution - e.g., skeleton, spinner] - [Rationale]
- **Empty:** [CTA + messaging] - [Rationale]
- **Error:** [Recovery mechanism - e.g., toast + retry]
- **Success:** [Feedback - e.g., toast, animation, redirect]

#### Navigation

**Entry points:** [List of paths/screens that lead here]
**Exit points:** [List of paths/screens reachable from here]
**Breadcrumb:** [If applicable - structure]

#### Notes
[Technical constraints, design considerations, open questions]

---

### [Screen Name]
[Repeat structure above for each screen]

---

## 5. Navigation Flow Diagram

```
[Textual diagram showing main flows]

Public Flow:
Landing → Login → Dashboard
       → Signup → Onboarding → Dashboard

User Flow:
Dashboard → Feature A List → Feature A Detail → Edit Feature A
         → Feature B
         → Settings → Profile/Account/Preferences

Admin Flow:
Admin Dashboard → Users → User Detail
               → System Config
```

---

## 6. Coverage & Gaps

### Stories Covered

| Story ID | Screen(s) | Status | Notes |
|----------|-----------|--------|-------|
| US-001 | Dashboard, Feature A List | ✅ | |
| US-002 | Feature A Detail | ✅ | |
| US-003 | Settings > Profile | ✅ | |

### Stories Not Covered

| Story ID | Reason | Proposed Action |
|----------|--------|-----------------|
| US-XXX | [Why not covered] | [What to do] |

### Identified Gaps (not in stories but necessary)

- **[Scenario/Edge Case]:** [Description of gap]
  → **Proposal:** [Proposed solution]
  → **Decision:** [Pending/Approved/Rejected by user]

**Common gaps to consider:**
- 403 Forbidden page (unauthorized access)
- 404 Not Found page
- Network error handling
- Session timeout behavior
- First-time user onboarding
- Global search (if applicable)
- Notifications system (if applicable)

---

## 7. Open Questions

[Only if there are questions still open after interaction]

- **Q:** [Question]
  - **Context:** [Why it's important]
  - **Options:** [Possible solutions]
  - **Decision:** [Pending]

---

## 8. Change Log

[Track iterations and key decisions]

- **v1.0** (YYYY-MM-DD): Initial draft from user stories
- **v1.1** (YYYY-MM-DD): Updated Dashboard layout per user feedback
- **v1.2** (YYYY-MM-DD): Added mobile gestures to Feature A List
- **v1.3** (YYYY-MM-DD): Resolved gap: added 403/404 pages
