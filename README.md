# Unified Document Hub

_Light-weight knowledge base focused on simplicity and low-friction capture of Markdown, PDF & text._

## Repository Layout (WIP)

```
├── docs/                 ← Documentation & roadmaps
│   └── DEVELOPMENT_CHECKLIST.md ← Living task list (update every PR)

DOCS_ROADMAP.md currently lives in the repo root; it will be moved under `docs/` once initial scaffolding stabilises.
├── frontend/             ← Angular 20 source (to be generated)
├── functions/            ← Firebase Cloud Functions
├── infra/                ← Terraform / deployment scripts (optional)
└── scripts/              ← One-off utilities
```

## Getting started (after scaffold)

1. Install [PNPM](https://pnpm.io) – `npm i -g pnpm`.
2. Initialise Firebase: `firebase init` (Hosting, Functions, Firestore, Storage).
3. Generate Angular workspace inside `frontend/`: `pnpm create @angular/core latest`.
4. Run locally with emulators: `firebase emulators:start`.

_Detailed instructions will evolve alongside the codebase._

---

• Roadmap: **DOCS_ROADMAP.md**  
• Task board: **docs/DEVELOPMENT_CHECKLIST.md**
