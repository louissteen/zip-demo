---
description: "The fields on a vendor record, where each comes from, and who is allowed to change it."
icon: id-card
---

# What the vendor record holds

The vendor record is the single description of a company you buy from. It is assembled from what the vendor submitted during onboarding, what your teams have added, and what related records in Zip contribute. No single team owns all of it.

## Identity

Legal entity name, trading name, registration number, country of incorporation, registered address, and website. This section is the vendor's own attestation and changes only through the vendor or through a controlled update.

The legal entity name is the one that appears on contracts and payments. The trading name is what people search for. Keeping both is what stops a buyer creating a second record because they could not find the one that exists.

## Tax and compliance

Tax identifiers, the tax form on file with its expiry, withholding status, sanctions screening results and date, and any certifications with their validity dates. Owned by tax, AP, and compliance.

## Payment

Remit-to addresses, bank accounts by currency, payment method, payment terms, and the remittance email. Owned by AP, with change control described in [Banking details and verification](https://app.gitbook.com/s/QStVF3i0EZksxOR4LHvB/).

## Commercial

Categories and subcategories the vendor supplies, the internal vendor owner, the vendor tier, preferred status, active contracts, and negotiated terms. Owned by procurement.

## Risk

Risk tier, completed assessments with dates and outcomes, open findings, and the next reassessment date. Owned by the risk teams. See [Risk Orchestration](https://app.gitbook.com/s/yP3apwhDPTBLUNkrxs0C/).

## Relationships and activity

The vendor record links to everything transacted with the vendor: purchase requests, purchase orders, contracts, invoices, bills, payments, sourcing events, and risk assessments. The activity view is a chronological record of the relationship.

{% hint style="info" %}
Before raising a request against a vendor you have not used, open its record and read the risk section and the contract list. A vendor with an existing master agreement usually does not need a new one, and a vendor with an open critical finding is worth knowing about before you commit.
{% endhint %}

## Field ownership and permissions

Each section has an owning role, and the record enforces it. A category buyer can change the vendor owner and the categories but cannot change bank details. An AP clerk can change payment terms but not the risk tier.

Some fields are read only in Zip because the ERP owns them. Which system owns which field is set in the integration mapping, and Zip shows the owning system on any field it does not control.

## History

Every change to a vendor record is retained with the previous value, the person who made it, and the time. History is not purged when a vendor is offboarded, because the questions that need it, such as which account a payment two years ago went to, arrive long after the relationship ends.

<details>

<summary>Can I add fields of our own?</summary>

Yes. Custom fields can be added to any section, with their own permissions and validation, and they can be populated by the vendor in onboarding or by internal users. Custom fields are available to workflow conditions and reporting like any other field. For building interfaces on top of them, see [App Studio](https://app.gitbook.com/s/cX4Nf30DIjPccRE9laBv/).

</details>
