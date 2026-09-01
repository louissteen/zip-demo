---
description: "Issue, amend, send, and close the purchase orders that commit spend against a vendor."
icon: file-contract
---

# Purchase Orders

A purchase order is the commitment. It fixes the vendor, the line items, the prices, and the currency, and it is the record every incoming invoice is matched against.

Most purchase orders are created from an approved request, which carries the vendor, coding, and line items across and links the two records. You can also create a standalone PO when the commitment did not come through intake, in which case you supply the full line item set yourself.

Amending an open order creates a new version rather than overwriting the old one. The list versions endpoint returns each version with who changed it, what the totals were, and whether that version reached the vendor, which is what auditors ask for. Depending on your workflow configuration, an amendment above tolerance routes for re-approval before it can be sent.

Send to vendor emails the current version to the vendor contacts you name, or to the vendor's default ordering contact. Closing an order stops further invoice matching and releases the unbilled commitment back to the [budget](../budgets/README.md), so close orders promptly once a vendor has delivered in full.

Each PO carries an `erp_reference` once it syncs. For receiving, three-way matching, and the ERP behavior behind these fields, see [Procure-to-Pay](https://app.gitbook.com/s/uvWZCHh4l0VWI5nRG3c4/).
