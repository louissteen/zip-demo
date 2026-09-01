# zip-docs

Source for the Zip documentation site demo built in GitBook.

Each top-level folder is a separate GitBook space. Wire each one to its directory via
Git Sync in the GitBook UI; edits then flow in both directions.

| Directory | Space | Section group |
|---|---|---|
| `home/` | Home | (top level) |
| `help-center/` | Help Center | (top level) |
| `intake-to-procure/` | Intake-to-Procure | Procurement lifecycle |
| `procure-to-pay/` | Procure-to-Pay | Procurement lifecycle |
| `sourcing/` | Sourcing | Procurement lifecycle |
| `ai-contract-orchestration/` | AI Contract Orchestration | Procurement lifecycle |
| `supplier-onboarding/` | Supplier Onboarding | Suppliers and risk |
| `vendor-management/` | Vendor Management | Suppliers and risk |
| `risk-orchestration/` | Risk Orchestration | Suppliers and risk |
| `vendor-portal/` | Vendor Portal | Suppliers and risk |
| `platform-overview/` | Platform overview | Platform |
| `intake-management/` | Intake management | Platform |
| `workflow-engine/` | Workflow engine | Platform |
| `budgets/` | Budgets | Platform |
| `spend-insights/` | Spend insights | Platform |
| `app-studio/` | App Studio | Platform |
| `ai-procurement-concierge/` | AI Procurement Concierge | Zip AI |
| `superagents/` | Superagents | Zip AI |
| `governed-ai/` | Governed AI | Zip AI |
| `api-reference/` | API Reference | (top level) |
| `changelog/` | Changelog | (top level) |

`api-reference/openapi.yaml` is the spec behind the generated endpoint pages. It is
registered with the GitBook organization under the slug `zip-procurement-v1`.
