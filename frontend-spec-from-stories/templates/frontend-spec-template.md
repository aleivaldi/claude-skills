# Frontend Specifications - [Project Name]

> **Status:** [Draft/Review/Approved]
> **Version:** [X.Y]
> **Last Updated:** [Date]
> **Derived from:** [User Stories v1.0 / Project Brief]

---

## 1. Overview

**Project:** [Project Name]
**Application Type:** [Web App/Mobile App/Desktop App/Multi-platform]
**Target Platforms:** [Desktop/Mobile/Tablet/Multi-platform]
**Purpose:** [Brief description of what this application does - 1-2 lines]

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

### Access Matrix

| Path Pattern | Roles | Redirect if Unauthorized |
|-------------|-------|-------------------------|
| / | All | - |
| /login | Guest | /dashboard if authenticated |
| /app/* | User, Admin | /login |
| /admin/* | Admin only | /dashboard |

---

## 4. Screens Inventory

### [Screen Name]

**Route:** `/path/to/screen` (web) | **Screen ID:** `ScreenName` (mobile)
**Users:** [Role1, Role2]
**Satisfies:** US-001, US-003
**Sitemap Location:** [Path from sitemap - e.g., /app/feature-a/list]

#### Purpose
[1-2 lines describing what this screen does - functional goal]

#### Data Displayed (cosa si vede)

- **[Information/Data 1]:** [Source: entity.field] - [Type: text/number/date/image/list/etc]
- **[Information/Data 2]:** [Source: entity.field or "Calculated"] - [Type]
- **[Section/Group]:** [Description of grouped information]

#### Actions Available (quali azioni)

**[Action Name]** (US-XXX)
- **Who:** [Roles that can perform]
- **What:** [What this action does]
- **Confirmation:** [Yes/No - if yes, specify why needed]

**[Action Name]** (US-XXX)
- **Who:** [Roles]
- **What:** [Description]
- **Confirmation:** [Yes/No]

#### Input Required (quali input inserire)

**[Field Name]:**
- **Type:** [text/number/email/date/select/checkbox/radio/file/etc]
- **Purpose:** [What this input is for]
- **Validation:** [required/optional, format requirements, range, etc]

**[Field Name]:**
- **Type:** [type]
- **Purpose:** [purpose]
- **Validation:** [validation rules]

#### Components Needed

- [Component type: button/form/table/list/search/filter/modal/dialog/dropdown/etc]
- [Component type]
- [Component type]

#### States

- **Loading:** [When data is being loaded]
- **Empty:** [When no data is available - what message/CTA to show]
- **Error:** [When operation fails - what info to show, recovery options]
- **Success:** [When operation succeeds - what feedback to provide]

#### Navigation

**Entry points:** [List of paths/screens that lead here]
**Exit points:** [List of paths/screens reachable from here]

#### Notes
[Functional constraints, business rules, open questions]

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
