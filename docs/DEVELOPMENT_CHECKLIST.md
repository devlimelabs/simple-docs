# Unified Document Hub – Development Checklist

This living checklist tracks every task required to bootstrap and iteratively ship the **Unified Document Hub**.  
Tasks are grouped by **Phase** and updated continuously – _tick a box (`[x]`) once finished_.

> **Convention**  
> • Major epics are level-2 headings.  
> • Concrete tasks use GitHub-flavoured todo boxes `[ ]`.  
> • Nested subtasks are indented with four spaces.  
> • ⏳ denotes work-in-progress.  
> • 🔗 links reference PRs / commits when available.

---

## 0. Foundations (Weeks 0-2)

### 0.1. Repository bootstrap

- [ ] Create base folder structure: `docs/`, `frontend/`, `functions/`, `scripts/`, `infra/`.
    - [x] `docs/` folder created  🔗 (commit)
- [x] Add `.gitignore` for Node, Firebase, and general artefacts.  🔗 (commit)
- [x] Add `README.md` skeleton with project vision & quick-start instructions.  🔗 (commit)
- [ ] Configure Git commit hooks via **pre-commit** (lint-staged / prettier / eslint).
- [ ] Set default Node / PNPM versions via `.nvmrc` & `.tool-versions`.

### 0.2. Continuous Integration / Delivery

- [ ] GitHub Actions workflow – **PR Lint & Test**
    - [ ] Install dependencies (pnpm cache)
    - [ ] Lint front-end (`ng lint`) & functions (`eslint`)
    - [ ] Run unit tests (`ng test --watch=false --browsers=ChromeHeadless`)
- [ ] GitHub Actions workflow – **Deploy to Firebase Hosting Preview** on every PR.
- [ ] GitHub Actions workflow – **Deploy to Production** on merge into `main`.

### 0.3. Firebase project scaffold

- [ ] Create Firebase project `unified-doc-hub`.
- [ ] Enable products: Authentication, Firestore, Cloud Storage, Functions, Hosting.
- [ ] Download `firebaseConfig` and store in `frontend/src/environments/*.ts`.
- [ ] Initialise `firebase.json` & `.firebaserc`.

---

## 1. Minimum Viable Product (Weeks 2-6)

### 1.1. Core Data Model

- [ ] Firestore rules skeleton – lock to authenticated user documents.
- [ ] Cloud Functions: `onDelete` cleanup blob storage.
- [ ] Define TypeScript interfaces: `Document`, `UserProfile`.

### 1.2. Authentication

- [ ] Implement Email/Password signup flow (AngularFire).
- [ ] Enable Google & GitHub OAuth providers.
- [ ] Route guards + auto-redirect logic.

### 1.3. CRUD & UI Basics

- [ ] Angular Material layout shell (toolbar, sidenav).
- [ ] Dashboard listing component (list + grid toggle).
- [ ] Monaco editor integration with Markdown preview.
- [ ] File upload service (drag-drop / paste) storing blobs in Cloud Storage.

### 1.4. Viewing & Search

- [ ] Marked + Prism viewer component.
- [ ] PDF.js viewer module.
- [ ] Basic string search over title/body (client-side) while Phase-1.

---

## 2. Organization & QoL (Weeks 6-10)

- [ ] Tag management service & UI.
- [ ] Star / Pin documents.
- [ ] Sort & filter controls.
- [ ] Bulk operations & Recycle bin.
- [ ] Dark ↔ Light theme toggle.

---

## 3. Capture Integrations (Weeks 10-14)

- [ ] Browser extension skeleton (Manifest v3).
- [ ] Context-menu & selection scrape → Cloud Function endpoint.
- [ ] PWA share target.
- [ ] Email → Doc gateway.

---

## 4. Collaboration & Linking (Weeks 14-18)

- [ ] `[[wikilink]]` parser & backlink panel.
- [ ] Document history versioning (Firestore document versions collection).
- [ ] Read-only share links.
- [ ] Inline comments threads.

---

## 5. Power Features (Weeks 18-24)

- [ ] Offline mode (Service Worker + IndexedDB cache).
- [ ] AI helpers (summarise, toc, Q&A) via OpenAI Functions.
- [ ] Batch export ZIP.
- [ ] Custom CSS / themes.

---

## Meta / House-keeping

- [ ] Keep this checklist updated every session – **DO NOT MERGE** without ticking/completing relevant items.
- [ ] Link every finished item to associated PR.

---

Last updated: <!-- KEEP-BOT-STAMP --> 2025-06-15
