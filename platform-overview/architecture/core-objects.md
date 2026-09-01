---
description: "The records Zip creates and maintains, and the relationships that connect a purchase request to the payout that eventually settles it."
icon: cubes
---

# Core objects

Almost everything in Zip is one of a small number of objects. Learning what each one is, and which object it points at, explains most of the product's behavior.

## The object model

```mermaid
erDiagram
    SUBSIDIARY ||--o{ DEPARTMENT : "contains"
    SUBSIDIARY ||--o{ PURCHASE_REQUEST : "scopes"
    SUBSIDIARY ||--o{ VENDOR_RECORD : "enables"
    SUBSIDIARY ||--o{ GL_CODE : "publishes"

    INTAKE_FORM ||--o{ PURCHASE_REQUEST : "produces"
    WORKFLOW ||--o{ APPROVAL_CHAIN : "generates"
    PURCHASE_REQUEST ||--|| APPROVAL_CHAIN : "runs"
    PURCHASE_REQUEST ||--o{ REQUEST_LINE_ITEM : "itemizes"
    REQUEST_LINE_ITEM }o--|| GL_CODE : "codes to"
    REQUEST_LINE_ITEM }o--|| DEPARTMENT : "charges"
    REQUEST_LINE_ITEM }o--o| BUDGET : "consumes"

    PURCHASE_REQUEST ||--o| PURCHASE_ORDER : "becomes"
    PURCHASE_REQUEST }o--|| VENDOR_RECORD : "names"
    PURCHASE_REQUEST ||--o{ CONTRACT : "attaches"

    PURCHASE_ORDER ||--o{ PO_LINE_ITEM : "itemizes"
    PURCHASE_ORDER }o--|| VENDOR_RECORD : "issued to"
    PURCHASE_ORDER ||--o{ INVOICE : "billed against"

    INVOICE ||--o| BILL : "coded into"
    INVOICE }o--|| VENDOR_RECORD : "received from"
    BILL ||--|| APPROVAL_CHAIN : "runs"
    BILL }o--o{ VENDOR_CREDIT : "offset by"
    BILL }o--o| PAYOUT : "settled by"
    PAYOUT }o--|| VENDOR_RECORD : "pays"
    VENDOR_CREDIT }o--|| VENDOR_RECORD : "issued by"

    USER ||--o{ PURCHASE_REQUEST : "requests"
    USER ||--o{ APPROVAL_CHAIN : "approves in"
```

## The objects, one by one

<details>

<summary>Transaction objects</summary>

**Purchase request (PR)**: what a requester submits. It carries the intake form answers, one or more line items, the named vendor, and the approval chain. It is the root of the audit trail for a purchase.

**Purchase order (PO)**: the commitment issued to the vendor. Zip can generate it automatically when a PR is fully approved, populated from the PR, and sync it to the ERP. A PO tracks how much of its value has been billed.

**Invoice**: the document the vendor sends. It reaches Zip by email, vendor portal upload, or manual creation, and Zip scans it to pre-populate the record. Invoices match to POs where possible.

**Bill**: the coded, approvable form of an invoice. Coding assigns GL codes, departments, tax codes, and amortization schedules. Once coded, the bill runs its own approval chain.

**Payout**: the payment issued to the vendor, net of any applied vendor credits. One payout can settle several bills for the same vendor and currency.

**Vendor credit**: a credit memo from the vendor, matched to a PO and applied to bills before payment.

</details>

<details>

<summary>Master data objects</summary>

**Vendor record**: the supplier as Zip knows it, including contacts, banking details, onboarding state, and risk status. Vendor records are enabled per subsidiary.

**Subsidiary**: the legal entity a transaction belongs to. Subsidiary determines the currency, the available chart of accounts, and often the approval policy.

**Department, GL code, cost center**: the accounting dimensions applied to line items, normally synced from the ERP.

**Category and subcategory**: Zip's own taxonomy for what is being bought. Categories drive routing far more often than GL codes do.

</details>

<details>

<summary>Process objects</summary>

**Intake form**: the questions asked at the start. See [Intake management](https://app.gitbook.com/s/klfPYPbO77zxOWiQGk7y/).

**Workflow**: the rules that decide who approves what. See [Workflow engine](https://app.gitbook.com/s/cCva0sBd9z7KRG56Fq0I/).

**Approval chain**: the instantiated result of a workflow on one record. Chains exist on requests and on bills, and are the thing an approver actually acts on.

</details>

{% hint style="info" %}
The link from a payout back to the original purchase request survives the whole chain. Open a payout, follow it to the bill, the invoice, the PO, and the PR, and you can see the intake answers and every approval that authorized the spend.
{% endhint %}
