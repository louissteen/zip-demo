---
description: "Define what complete and current vendor data means, measure it, and fix what fails."
icon: clipboard-check
---

# Data quality standards

Vendor data quality is not a cleanup project. It is a standard you define, a measurement you run continuously, and a set of workflows that fix what fails. Without the standard, "clean up the vendor master" has no finish line.

## The four dimensions

**Completeness.** The required fields are present. Requirements differ by vendor: a vendor you pay needs a bank account, a vendor with system access needs a completed security assessment, a vendor supplying on site needs current insurance.

**Validity.** Values are well formed and pass the checks available to them. Tax identifiers match the country format, IBANs pass check digits, addresses standardize, and domains resolve.

**Currency.** Values are recent enough to be trusted. A tax form within its validity period, a bank account confirmed within the refresh cycle, a risk assessment inside its reassessment interval, and a contact who still works at the vendor.

**Consistency.** Related values agree. The entity on the contract matches the entity on the tax form matches the account holder name on the bank account. Inconsistency here is the pattern most worth investigating, because it is both a data problem and a fraud indicator.

## Setting the standard

Standards are defined per vendor tier. Requiring a full data set of every vendor produces a long list of failures nobody works and an implicit conclusion that the report can be ignored.

A workable pattern:

* **Strategic vendors.** Complete data set, annual refresh, hierarchy modeled, named internal owner, current risk assessment.
* **Transactional vendors.** Identity, tax, and banking complete and valid. Refresh on expiry only.
* **One-time vendors.** The minimum needed to pay lawfully, with no ongoing refresh obligation.

## The data health view

The health view scores the vendor master against the standard and breaks results down by tier, by category, by owner, and by spend. Two views matter more than the headline score.

**Failures weighted by spend.** A missing field on a vendor you pay heavily is not the same as one on a vendor you used once.

**Trend.** Whether the failure count is rising or falling. A stable number with active remediation means new failures are being created as fast as you fix them.

{% hint style="info" %}
Report quality by owner, not only in aggregate. Vendor data improves when a named person is accountable for a defined set of vendors and can see their own list. An organization-wide percentage is nobody's job.
{% endhint %}

## Fixing failures

Failures route to whoever can actually fix them.

Vendor-attested fields go back to the vendor as a re-onboarding task, since your team should not be guessing a vendor's tax classification. See [Re-onboarding](https://app.gitbook.com/s/QStVF3i0EZksxOR4LHvB/).

Internal fields, such as category, tier, and owner, route to the vendor owner or to procurement operations.

Fields owned by the ERP are corrected there and flow back on the next sync. Correcting them in Zip creates a conflict that the next sync overwrites.

## Preventing failures

Validate at entry rather than reporting on entry errors later. Every check the onboarding form runs is a failure that never reaches the master. When a recurring failure appears in the health view, the durable fix is usually a validation rule or a better field prompt in the questionnaire, not a bulk update.
