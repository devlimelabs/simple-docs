# Unified Document Hub – Feature & Road-map

Light-weight knowledge base focused on **simplicity** and **low-friction capture** of Markdown, PDF, text & small HTML snippets.

This roadmap is grouped into delivery phases so that we can ship value quickly (MVP) while keeping long-term ambitions visible.

---

## 0. Foundations (Weeks 0–2)

* Tech decisions
  * Front-end: **Angular 20** + Angular Material
  * Back-end: **Firebase** (Auth, Firestore, Cloud Storage, Hosting, Functions)
* Repo setup & CI
  * Linting / Pre-commit hooks
  * Automated deployments to Firebase Hosting (preview & prod channels)

---

## 1. Minimum Viable Product (MVP – Weeks 2-6)

### 1.1. Core data model
* Document (`doc`): id, title, body (Markdown), mimeType, source, createdAt, updatedAt, size, tags []
* Stored in Firestore; blobs (PDF etc.) in Cloud Storage.

### 1.2. Authentication
* Firebase Email/Password, Google, GitHub providers.

### 1.3. CRUD & UI basics
* Responsive dashboard (list / grid)
* Create / edit Markdown docs with Monaco-based editor + live preview
* Upload PDFs / Text / simple HTML (server converts HTML→Markdown via Turndown)
* Drag-and-drop upload & clipboard paste

### 1.4. Viewing
* Markdown render (Marked + Prism highlighting)
* In-browser PDF viewer (PDF.js)

### 1.5. Search
* Simple full-text search (Firestore queries; later switch to Algolia)

Deliverable: A user can sign in, add documents, edit Markdown, and search within their vault.

---

## 2. Organization & Quality of Life (Weeks 6-10)

* Tag management (create, rename, color-code)
* Star / Pin important docs
* Sort & filter (tag, type, date, size)
* Bulk operations (delete, tag, export)
* Soft-delete & recycle bin (30-day retention)
* Dark / light theme toggle

---

## 3. Capture Integrations (Weeks 10-14)

### 3.1. Browser extension (Chrome / Edge / Firefox)
* 1-click “Send to Hub” from
  * ChatGPT / Claude / Manus pages ⇒ grabs selected text & source URL
  * Any webpage ⇒ converts selection → Markdown, stores original HTML snapshot

### 3.2. Share-sheet on mobile PWA
* “Share to Hub” target for iOS/Android browsers

### 3.3. Email-to-Doc gateway
* Unique address (Cloud Functions) → parses email → Markdown doc

---

## 4. Collaboration & Linking (Weeks 14-18)

* Internal wiki links: `[[Doc Title]]` auto-link + backlink panel
* Document history & diff viewer (Firestore document versions)
* Read-only share links (expiring, password optional)
* Comment threads per paragraph / line

---

## 5. Power Features (Weeks 18-24)

* Offline mode – PWA with IndexedDB cache & background sync
* AI helpers (Cloud Functions + OpenAI API)
  * Summarize doc
  * Generate table of contents
  * Q&A over vault (embeddings)
* Batch export: Markdown bundle or ZIP (original files + JSON manifest)
* Theming / CSS overrides per user

---

## 6. Enterprise / Long-term Ideas (backlog)

* Role-based access control & shared workspaces
* e-Pub / Word import/export
* Git-style branching for docs
* Self-hosting option (Supabase / App Engine)
* SSO (SAML / OIDC)

---

## Development Milestones & Deliverables

| Phase | Timeframe | Key Deliverable |
|-------|-----------|-----------------|
| 0     | 0-2 wks   | Repo, CI/CD, Firebase project |
| 1     | 2-6 wks   | MVP deployed – auth, CRUD, Markdown editor/viewer |
| 2     | 6-10 wks  | Tagging, filtering, UI polish |
| 3     | 10-14 wks | Browser extension & mobile share target |
| 4     | 14-18 wks | Linking, history, sharing |
| 5     | 18-24 wks | Offline mode + AI helpers |

---

## Open Questions

1. PDF annotation – needed?
2. Versioning granularity (per save vs draft snapshots)?
3. Pull vs push integrations (e.g., GitHub repo sync)?
4. Pricing / limits strategy (if public launch)?

---

## Next Steps

1. Review & trim MVP scope if needed.
2. Lock technical stack versions & Firebase quotas.
3. Generate wireframes for dashboard & editor screens.
4. Kick-off Phase 0 tasks.

