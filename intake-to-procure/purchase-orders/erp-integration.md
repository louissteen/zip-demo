---
description: "How purchase orders, vendors, and accounting data move between Zip and your ERP."
icon: arrows-rotate
---

# ERP integration

Zip sits in front of the ERP. Requests, approvals, and negotiation happen in Zip; the ERP remains the system of record for the general ledger. The integration keeps the two consistent without asking anyone to key the same data twice.

Zip integrates with NetSuite, SAP, Oracle, Coupa, and Workday, among others.

## What syncs in each direction

{% tabs %}
{% tab title="ERP to Zip" %}
Reference data flows from the ERP into Zip so that requesters and buyers select values the ERP will accept.

* Chart of accounts and GL codes
* Departments, cost centers, and classes
* Subsidiaries and legal entities
* Currencies and exchange rates
* Tax codes
* Existing vendor records, for the initial load and for ongoing reconciliation
* Budget balances, where the ERP is the budget source

These are read on a schedule and cached in Zip. A value retired in the ERP stops appearing in Zip pickers on the next sync.
{% endtab %}

{% tab title="Zip to ERP" %}
Transactional records flow from Zip into the ERP once they are approved.

* Purchase orders, on issuance, with line-level coding
* PO revisions and closures
* New and updated vendor records, once onboarding is complete and approved
* Bills, once fully coded and approved
* Payment records, where Zip issues the payment

Zip writes only approved records. A request still in review never reaches the ERP.
{% endtab %}
{% endtabs %}

## Field mapping

Mapping is configured per integration. Each Zip field is mapped to an ERP field, and pickers in Zip are populated from the ERP values rather than from a separate list maintained by hand. Where the ERP requires a field Zip does not collect, add a question to the intake form so the value exists before the PO is written.

Unmapped or unmatched values are the most common cause of sync failures. Keeping the mapping current is part of running the integration.

## Sync timing and failures

Reference data syncs on a schedule set by your administrators. Transactional writes are attempted as soon as the record is approved.

When a write fails, the record stays in Zip with a sync error and is retried. The **Integrations** page lists failed records with the error the ERP returned, and a buyer or administrator can correct the record and retry. The PO remains valid in Zip while the error is open, but the ERP does not carry the commitment until the write succeeds.

{% hint style="warning" %}
Do not create a matching PO manually in the ERP to work around a sync error. When the retry succeeds you will have two commitments against the same purchase, and invoice matching will pick one at random.
{% endhint %}

## Vendor records and the ERP

The vendor record is the piece most likely to drift, because both systems can create vendors. Decide which system owns vendor creation and enforce it. Zip's usual pattern is that new vendors are created in Zip through onboarding and pushed to the ERP, while historical vendors are imported once and matched by tax ID. See [Vendor Management](https://app.gitbook.com/s/VzFAfjeuJK2DKd9GcLgy/) for deduplication and matching rules.

For connection setup, authentication, and the full list of supported systems, see the [API reference](https://app.gitbook.com/s/CXK9J3Tjg4dEAgf0G90t/).
