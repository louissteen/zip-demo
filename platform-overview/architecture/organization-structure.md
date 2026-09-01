---
description: "Subsidiaries, departments, GL codes, and cost centers: the dimensions that scope every record in Zip."
icon: building
---

# Organization structure

Zip mirrors the shape of your business so that requests, approvals, and accounting land in the right place. Four dimensions do most of the work.

## Subsidiary

The subsidiary is the legal entity a transaction belongs to. It is the most consequential dimension in Zip because it determines:

- The functional currency of the request, the PO, and the payout.
- Which chart of accounts and tax codes are available.
- Which vendor records can be transacted with, since vendors are enabled per subsidiary.
- Which approval policy applies, in most multi-entity configurations.

Subsidiaries are normally synced from the ERP. A user can be given access to one subsidiary, several, or all of them.

## Department

Departments identify who bears the cost internally. They drive budget consumption and are frequently the trigger for a departmental approval step, since the department owner is often the person whose budget is affected.

## GL code

The GL code is the account the spend posts to. Zip validates GL codes against the synced chart of accounts, so requesters can only pick codes that exist in the ERP for that subsidiary.

{% hint style="info" %}
Requesters rarely pick GL codes well. Most organizations hide the field on the intake form and derive the code from the category, then let procurement or AP adjust it during coding. See [Intake management](https://app.gitbook.com/s/klfPYPbO77zxOWiQGk7y/).
{% endhint %}

## Cost center

Where your ERP uses cost centers alongside or instead of departments, Zip carries them as an additional dimension on the line item. Which of the two is required depends on how your chart of accounts is configured.

## How the dimensions combine

Dimensions are applied at the line item, not the request header. One request can split across two departments and three GL codes, and each split is tracked separately through the PO and the bill.

<details>

<summary>Worked example</summary>

A marketing team raises one request for a design agency engagement worth an annual fee plus a project fee.

- Subsidiary: the US operating entity, so amounts are in USD.
- Line 1: professional services GL code, Marketing department, charged against the marketing services budget.
- Line 2: professional services GL code, Brand cost center, charged against a project budget.

The PO issues with both lines. When the agency invoices the project fee only, the invoice matches line 2, and the PO shows the annual fee still open.

</details>

## Keeping structure in sync

Structure changes constantly: entities are added, departments are reorganized, accounts are retired. Zip refreshes these on a schedule from the ERP.

Two behaviors matter when structure changes:

**Retired values stay readable.** A GL code that has been deactivated in the ERP stops appearing in pickers but still displays correctly on historical records.

**In-flight records keep their values.** Reorganizing departments does not retroactively recode approved requests. If a re-code is needed, it is done deliberately during bill coding.

See also [Budgets](https://app.gitbook.com/s/gD02PoHU1QdZrvopYAC5/) for how budgets attach to these dimensions.
