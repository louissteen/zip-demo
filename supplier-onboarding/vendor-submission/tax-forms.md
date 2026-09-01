---
description: "Collect the right tax form for each vendor, validate it, and keep it current."
icon: file-invoice-dollar
---

# Tax forms

Zip collects the tax form appropriate to the vendor's jurisdiction and your reporting obligations. The form the vendor sees is determined by its country and entity type, so vendors are not asked to work out which document applies to them.

Tax forms are collected as part of onboarding and stored on the vendor record. A vendor cannot be activated without a valid form where one is required.

{% tabs %}
{% tab title="US vendors" %}
US persons and US entities complete a **W-9**, which supplies the taxpayer identification number and the federal tax classification, and certifies the vendor is not subject to backup withholding.

Zip presents the form in the portal, validates the TIN format against the entity type, and checks that the classification and the name are consistent. A sole proprietor entering a business name without the individual name is a common rejection and is caught at entry.

Where your organization uses TIN matching against the tax authority, a mismatch is flagged for the vendor to correct before submission rather than surfacing months later on a reporting run.

W-9 information feeds 1099 reporting for vendors that meet the reporting criteria.
{% endtab %}

{% tab title="Non-US vendors" %}
Foreign persons and entities receiving US-source income complete a **W-8** form. The correct variant depends on the vendor.

* **W-8BEN** for a foreign individual.
* **W-8BEN-E** for a foreign entity, including the treaty claim and the entity's chapter 4 status.
* **W-8ECI** where income is effectively connected with a US trade or business.
* **W-8EXP** and **W-8IMY** for the narrower cases those forms cover.

Zip determines the variant from the vendor's answers about entity type and residence, and presents only that one. Treaty benefit claims require the country, the article claimed, and a foreign tax identifying number, and Zip validates that the claimed treaty exists between the two countries.

W-8 forms expire. Zip tracks the expiry date and starts a refresh before it lapses.
{% endtab %}

{% tab title="Other jurisdictions" %}
Outside the US, Zip collects the identifiers your reporting requires for the vendor's country. Typical examples are a VAT registration number in the EU and UK, a GST number in Canada, Australia, or India, and the local business registration number.

VAT and GST numbers are validated against the relevant public register where one is available, which confirms both the number and the registered name. A number that validates to a different entity name is held for review.

Withholding tax questions appear where the buying subsidiary's jurisdiction requires them, and the answers drive whether withholding is applied when the vendor is paid.
{% endtab %}
{% endtabs %}

{% hint style="warning" %}
A vendor's tax form must match the legal entity you contract with and pay, not its parent and not a local sales affiliate. A mismatch between the entity on the contract, the entity on the tax form, and the account receiving payment is a reporting problem and often a fraud indicator.
{% endhint %}

## Expiry and refresh

Forms with a defined validity period are tracked to their expiry date. Zip notifies the vendor ahead of expiry and asks it to submit a replacement through the portal. An expired form does not stop payment automatically by default, but it can be configured to, and it always appears on the vendor data quality report.

## Storage and access

Tax forms contain sensitive identifiers. Access is restricted to roles that need it, typically AP, tax, and vendor administration. The identifier is masked in the interface and in exports for anyone without that permission, and every view of a full identifier is logged.

For how these documents are reviewed before activation, see [Approve and activate a vendor](../review-and-activation/approval-and-activation.md).
