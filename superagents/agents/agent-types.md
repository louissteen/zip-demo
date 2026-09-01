---
description: "The Superagent types available in Zip, what each one watches for, and the work it produces."
icon: shapes
---

# Agent types

Each agent is scoped to one part of the procurement process. Enable them individually. Most customers start with one agent on a high-volume, low-judgment task and widen from there.

## Intake agent

Watches new intake submissions. Reads the request, checks it against category rules and existing vendor records, fills in fields the requester left blank where the answer is unambiguous, and flags duplicates against open requests and active contracts.

Where the request is clearly misrouted, it corrects the category and lets the [workflow engine](https://app.gitbook.com/s/cCva0sBd9z7KRG56Fq0I/) reroute. It does not approve requests. See [Intake-to-Procure](https://app.gitbook.com/s/BMSPlYB6zBpUu9WDNW3q/).

## Vendor onboarding agent

Watches onboarding submissions. Checks tax forms and banking details for completeness, compares the submitted legal entity against existing vendor records, and chases the vendor for missing documents through the vendor portal. It stops before any change to bank details, which is always a human decision. See [Supplier Onboarding](https://app.gitbook.com/s/QStVF3i0EZksxOR4LHvB/).

## Invoice and bill agent

Watches inbound invoices. Reads the document, matches it to a purchase order, applies GL codes and cost centers from the PO and from prior coding on the same vendor, and routes exceptions to a human coder. Amount variances outside your tolerance go to a person rather than through. See [Procure-to-Pay](https://app.gitbook.com/s/uvWZCHh4l0VWI5nRG3c4/).

## Risk review agent

Watches requests that trigger a security, privacy, or compliance review. Assembles the assessment package, pulls prior assessments for the same vendor, and answers reviewer questions that a previous review already settled. Reviewers still decide. See [Risk Orchestration](https://app.gitbook.com/s/yP3apwhDPTBLUNkrxs0C/).

## Contract agent

Watches contracts arriving for review or approaching renewal. Extracts key terms, compares them against your standard positions, flags deviations for legal, and opens a renewal request ahead of an auto-renewal date. See [AI Contract Orchestration](https://app.gitbook.com/s/DeZIgDtBPmTV8Lg8mf2S/).

## Sourcing agent

Watches sourcing events. Drafts the request package from the intake record, normalizes vendor responses into a comparable structure, and summarizes differences across bids. Award decisions are always human. See [Sourcing](https://app.gitbook.com/s/yWPKTXf10NGJgEVmE6Ok/).

{% hint style="warning" %}
Enable one agent at a time and watch its intervention rate for a full cycle before enabling the next. Two agents introduced together make a rising exception count hard to attribute.
{% endhint %}

<details>
<summary>Choosing the first agent to enable</summary>

Pick the task with the highest volume and the narrowest judgment. For most organizations that is invoice coding or intake triage: the work is repetitive, the correct answer is usually determinable from existing records, and a mistake is visible immediately at the next approval step rather than after payment.

</details>
