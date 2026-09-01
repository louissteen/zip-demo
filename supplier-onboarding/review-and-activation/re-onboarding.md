---
description: "Refresh vendor data when it expires, when the vendor changes, or on a periodic cycle."
icon: rotate
---

# Re-onboarding

Vendor data decays. Tax forms expire, companies are acquired, finance contacts leave, and certificates lapse. Re-onboarding asks the vendor to confirm or update what you hold, without repeating the parts that have not changed.

## What triggers a refresh

**Document expiry.** A W-8 form, an insurance certificate, or a compliance certification reaching its expiry date. Zip starts the refresh ahead of the date rather than after it.

**Periodic cycle.** A recurring review by vendor tier. Strategic vendors are refreshed more often than a vendor you used once two years ago. The cycle is set per tier by your administrators.

**Vendor-initiated change.** The vendor updates something material in the portal, such as its legal name, address, or bank account. A material change reopens the relevant checks.

**Corporate event.** A merger, acquisition, or entity restructure. These need a new tax form and often a new contract, because the entity you are paying is not the entity you signed with.

**Data quality finding.** A field flagged as missing, stale, or inconsistent by the vendor data quality report.

**Reactivation.** A vendor that was made inactive and is being brought back. Anything past its validity period must be refreshed before the vendor becomes payable again.

## How a refresh runs

{% stepper %}
{% step %}
## Zip opens a refresh task

The vendor is notified in the portal and by email. The internal vendor owner is notified too, so they know the vendor is being asked for something.
{% endstep %}

{% step %}
## The vendor reviews prefilled data

The vendor sees what you currently hold. It confirms each section as unchanged or updates it. Only sections that require attention are editable by default.
{% endstep %}

{% step %}
## The vendor submits

The submission includes what changed and what was confirmed unchanged, with the confirmation date.
{% endstep %}

{% step %}
## Only changed sections are reviewed

Sections confirmed unchanged are not re-reviewed. Sections that changed go to the reviewers who own them, with bank changes always requiring independent verification.
{% endstep %}

{% step %}
## The record is updated

Approved changes are written to the vendor record and synced to the ERP. The previous values are retained in history.
{% endstep %}
{% endstepper %}

{% hint style="warning" %}
A change of legal entity name is not a data update. Confirm whether the entity itself changed or only its trading name. If the entity changed, you need a new tax form, a check of whether your contract permits assignment, and usually a new vendor record rather than an edit to the existing one.
{% endhint %}

## Enforcement

Refreshes can be advisory or enforced. Advisory refreshes appear on the data quality report and nag the vendor. Enforced refreshes place a hold on new purchase orders, on payments, or on both when a deadline passes.

Enforce narrowly. Blocking payment to a vendor over a lapsed certificate creates an escalation that reaches finance leadership quickly and rarely produces the certificate faster than a phone call would.

## Reporting

The vendor data health view shows vendors by refresh state: current, due, overdue, and blocked. Filter by tier and by spend so effort goes to the vendors that matter. A vendor with no spend in two years is usually better offboarded than refreshed, which is covered in [Vendor Management](https://app.gitbook.com/s/VzFAfjeuJK2DKd9GcLgy/).
