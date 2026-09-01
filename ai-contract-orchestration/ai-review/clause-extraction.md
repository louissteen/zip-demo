---
description: "What Zip reads out of a contract document and how extracted terms are reviewed."
icon: wand-magic-sparkles
---

# Clause extraction

When a contract document is uploaded, Zip reads it and pulls out the terms that matter operationally. Extraction runs on your own paper, on supplier paper, and on legacy contracts loaded into the repository in bulk.

## What gets extracted

**Parties and entities.** The legal entities on each side, which is not always the entity the requester named. Extraction catching a subsidiary that differs from the one on the purchase request is a common and useful early save.

**Dates.** Effective date, term start and end, renewal type, notice period, and any milestone dates written into the agreement.

**Commercials.** Total value, currency, pricing structure, payment terms, uplift or escalator provisions, and minimum commitments.

**Legal positions.** Limitation of liability, indemnities, warranty, termination rights, governing law, assignment, and confidentiality term.

**Data and security terms.** Data processing provisions, transfer mechanism, subprocessor rights, security standards referenced, audit rights, and breach notification periods.

**Obligations.** Commitments either party takes on that need tracking after signature, such as a required certification, a service credit regime, or a notice the buyer must give.

## Confidence and review

Every extracted value carries a confidence indicator and a link to the exact passage it came from. Low-confidence values are flagged for a human to confirm before they are written to the contract record.

Selecting a value scrolls the document to the source text. Reviewers read the passage rather than trusting the field, which is the part of the workflow that keeps extraction honest.

{% hint style="warning" %}
Extracted values are a proposal, not the agreement. The document is the agreement. Where a field and the underlying text disagree, the text governs, and the field should be corrected.
{% endhint %}

## Corrections and learning

Correcting an extracted value updates the contract record and records the correction. Repeated corrections of the same field on the same template are a signal that the template or the extraction configuration needs attention, and the extraction quality report surfaces them.

## Bulk extraction on legacy contracts

Existing contracts can be loaded in bulk and extracted so the repository starts useful rather than empty. Bulk runs produce a review queue sorted by confidence, so a small team can confirm the uncertain values and accept the rest.

Prioritize by what you need soonest. For most teams that is dates and notice periods, because those are what cause an unwanted auto-renewal, followed by value and counterparty for spend reconciliation.

## Data handling

Contract documents are processed within your Zip tenant. Extraction does not train shared models on your documents, and access to a contract's content follows the same permissions as the contract record itself. For the full description of how AI features handle your data, model selection, and audit logging, see [Governed AI](https://app.gitbook.com/s/oovoef3hZyAQg9DepDDH/).

<details>

<summary>Which file types can be extracted?</summary>

Text-based PDFs and common word processing formats extract directly. Scanned documents are processed with optical character recognition first, which usually works but produces lower confidence on poor scans. A photograph of a signature page is not a usable source document.

</details>
