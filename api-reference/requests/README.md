---
description: "Raise purchase requests, submit them for approval, and read their approval chains."
icon: file-lines
---

# Requests

A purchase request is where spend starts in Zip. It records what someone wants to buy, from which vendor, against which category and cost center, and it carries that context through every object that follows.

Use these endpoints when another system is the front door. A ticketing tool, an internal portal, or a Superagent can create a request, add line items over several calls while it is still in `draft`, and then submit it. Submitting is what builds the approval chain: Zip reads the amount, category, subsidiary, and custom field values and resolves who has to review, so your integration never has to encode approval policy of its own.

Statuses are `draft`, `pending_approval`, `approved`, `rejected`, and `cancelled`. The list approvals endpoint returns every step in order, including pending ones, which is what you render if you want to show a requester who they are waiting on.

An approved request becomes a [purchase order](../purchase-orders/README.md), and the PO's `request_id` links back here. Check a line against a [budget](../budgets/README.md) before you submit, so the requester sees the problem while they can still fix it.

For how requests behave in the product, including intake forms and routing rules, see [Intake-to-Procure](https://app.gitbook.com/s/BMSPlYB6zBpUu9WDNW3q/).
