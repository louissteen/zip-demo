---
description: "Upload vendor invoices, match them to a purchase order, code them, or return them."
icon: file-invoice
---

# Invoices

An invoice is the vendor's document. Zip captures it, matches it to a purchase order, and turns the result into a bill. These endpoints let another system own the capture step.

Create an invoice in one of two ways. Post the file as multipart form data and Zip extracts the header and line values itself, or post JSON when a scanning provider has already captured them. Either way Zip attempts a purchase order match as soon as the invoice exists.

The `match_state` field is the one to watch: `not_matched`, `partially_matched`, `matched`, or `exception`. An exception means a price, quantity, or receipt tolerance was breached, and `match_exceptions` says which line and by how much. Call match yourself to point an invoice at a specific purchase order, or to map invoice lines to PO lines when the vendor's line order does not agree with yours.

Coding applies the GL code, department, cost center, and category to each line. A fully coded invoice with a clean match becomes a [bill](../bills/README.md) and enters finance approval.

When an invoice cannot be processed, for example a missing PO number or a price that does not agree with the order, return it to the vendor with a reason code rather than leaving it in the AP queue.

Related: [Purchase Orders](../purchase-orders/README.md), [Procure-to-Pay](https://app.gitbook.com/s/uvWZCHh4l0VWI5nRG3c4/).
