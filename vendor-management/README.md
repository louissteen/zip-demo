---
description: "Maintain the vendor master: records, hierarchy, data quality, and the vendor lifecycle."
icon: address-book
---

# Vendor Management

The vendor master is the list of companies you can buy from and pay. It sounds like a reference table and behaves like a living system: vendors merge, rebrand, change banks, get acquired, and get created twice by two people who spelled the name differently. Vendor Management is where that list is kept correct.

Everything else in Zip depends on it. A purchase request selects a vendor, a purchase order commits to one, an invoice is matched to one, and a payment goes to a bank account held on one. A duplicate or a stale record does not stay a data problem for long; it becomes a misdirected payment or a spend report nobody trusts.

<table data-view="cards"><thead><tr><th></th><th></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td><strong>What the vendor record holds</strong></td><td>The fields on a vendor and who owns them.</td><td><a href="vendor-records/the-vendor-record.md">the-vendor-record.md</a></td></tr><tr><td><strong>Vendor hierarchy</strong></td><td>Parent and child entities, and rolled-up spend.</td><td><a href="vendor-records/vendor-hierarchy.md">vendor-hierarchy.md</a></td></tr><tr><td><strong>Duplicate detection and merging</strong></td><td>Find duplicates and merge them safely.</td><td><a href="data-quality/duplicate-detection.md">duplicate-detection.md</a></td></tr><tr><td><strong>Data quality standards</strong></td><td>Define what good vendor data looks like and measure it.</td><td><a href="data-quality/data-quality-standards.md">data-quality-standards.md</a></td></tr><tr><td><strong>Lifecycle states</strong></td><td>How a vendor moves from prospective to archived.</td><td><a href="lifecycle/lifecycle-states.md">lifecycle-states.md</a></td></tr><tr><td><strong>Offboard a vendor</strong></td><td>Retire a vendor without breaking history.</td><td><a href="lifecycle/offboarding-a-vendor.md">offboarding-a-vendor.md</a></td></tr></tbody></table>

{% hint style="info" %}
New vendors are created through [Supplier Onboarding](https://app.gitbook.com/s/QStVF3i0EZksxOR4LHvB/), not by editing the vendor master directly. This space covers what happens to a vendor record after it exists.
{% endhint %}
