# Wiring Git Sync

The 21 spaces already exist in GitBook and already contain this content, imported through the
API. Git Sync makes this repo the source of truth from here on, and fixes four things the
API import could not carry:

- **Images.** The five Zip product screenshots in `help-center/images/` and
  `procure-to-pay/images/` are in the repo but not in GitBook. Git Sync uploads them.
- **Page layout.** `home/README.md` asks for a wide hero layout with no table of contents.
  The API cannot set layout; Git Sync can.
- **Changelog tags.** `changelog/.gitbook/tags.yaml` gives the release tags their labels and
  icons. Right now the entries show raw slugs.
- **Navigation structure.** Each space's `SUMMARY.md` is the real table of contents. The
  imported trees approximate it.

## Step 0: push the repo

This repo is committed locally but has no remote.

```bash
cd zip-docs
git remote add origin git@github.com:<your-org>/zip-docs.git
git push -u origin main
```

## Step 1: wire each space

In GitBook, open each space, go to **Integrations**, then **Git Sync**, then **Configure**.

- **Repository**: the repo you just pushed
- **Branch**: `main`
- **Project directory**: the directory from the table below
- **Initial sync direction**: **GitHub to GitBook**, since the repo is the source of truth

| Space | Project directory |
|---|---|
| Home | `home` |
| Help Center | `help-center` |
| Intake-to-Procure | `intake-to-procure` |
| Procure-to-Pay | `procure-to-pay` |
| Sourcing | `sourcing` |
| AI Contract Orchestration | `ai-contract-orchestration` |
| Supplier Onboarding | `supplier-onboarding` |
| Vendor Management | `vendor-management` |
| Risk Orchestration | `risk-orchestration` |
| Vendor Portal | `vendor-portal` |
| Platform overview | `platform-overview` |
| Intake management | `intake-management` |
| Workflow engine | `workflow-engine` |
| Budgets | `budgets` |
| Spend insights | `spend-insights` |
| App Studio | `app-studio` |
| AI Procurement Concierge | `ai-procurement-concierge` |
| Superagents | `superagents` |
| Governed AI | `governed-ai` |
| API Reference | `api-reference` |
| Changelog | `changelog` |

Choosing GitHub to GitBook replaces the imported content with the repo's version. That is
what you want: the repo has the images, the layout and the correct navigation.

## Step 2: build the site structure

Site sections are set up in the UI under **Site**, then **Structure**. The intended shape:

- **Home**, **Help Center**, **API Reference**, **Changelog** as top-level sections
- **Product Docs** as a section group containing four groups:
  - Procurement lifecycle: Intake-to-Procure, Procure-to-Pay, Sourcing, AI Contract Orchestration
  - Suppliers and risk: Supplier Onboarding, Vendor Management, Risk Orchestration, Vendor Portal
  - Platform: Platform overview, Intake management, Workflow engine, Budgets, Spend insights, App Studio
  - Zip AI: AI Procurement Concierge, Superagents, Governed AI

## The OpenAPI spec

`api-reference/openapi.yaml` is already registered with the organization under the slug
`zip-procurement-v1` and processed with zero errors. `api-reference/SUMMARY.md` references
that slug from its **Endpoints** group, so the generated endpoint pages appear once Git Sync
runs on that space.
