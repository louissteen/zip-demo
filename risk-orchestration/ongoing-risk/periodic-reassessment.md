---
description: "Keep assessments current on a schedule and in response to events, without reassessing everything."
icon: calendar-days
---

# Periodic reassessment

An assessment describes a vendor at one moment. Vendors change: they are acquired, they move infrastructure, they add subprocessors, they lose a certification, they have an incident. Reassessment keeps what you know current.

## Scheduled reassessment

Intervals are set per risk tier, not per vendor. Higher tiers are reassessed more often. The interval runs from the completion of the last assessment, and Zip opens the reassessment with enough lead time for the vendor to respond before the current one lapses.

Reassessment reuses everything still valid. The vendor confirms unchanged answers, updates what moved, and supplies replacement evidence for anything that expired. Reviewers see a change summary rather than a fresh questionnaire.

## Event-driven reassessment

Some events matter more than the calendar. These trigger a reassessment regardless of when the last one ran.

**Scope change.** The vendor starts handling data it did not handle before, gets access it did not have, or is used for a new purpose. Usually detected from a new intake request naming an existing vendor.

**Corporate change.** Acquisition, merger, or change of control. The company you assessed may no longer be the company you are dealing with.

**Incident.** A breach or outage at the vendor, whether it affected you or not.

**Certification lapse.** An audit report or certification expires without replacement, which removes the evidence that satisfied much of the last assessment.

**Contract renewal.** A renewal is a natural point to confirm the risk position, and it is the point at which you can require remediation as a condition of continuing.

{% hint style="info" %}
Link reassessment to renewal where you can. The vendor is already engaged, the business is already reviewing the relationship, and any remediation you need can become a condition of renewal rather than a request with nothing behind it.
{% endhint %}

## Continuous monitoring

Between assessments, external monitoring can watch for signals: breach disclosures, sanctions list changes, financial distress indicators, certification changes, and external security ratings.

Monitoring alerts are triage inputs, not findings. Most are noise or concern a different entity with a similar name. Route them to a reviewer who decides whether to open a finding, trigger a reassessment, or dismiss the alert with a note.

## Keeping the volume manageable

Reassessment volume grows with the vendor base and can quietly consume a risk team. Three things keep it proportionate.

**Tier honestly.** If most vendors are high tier, tiering is not doing its job. Most vendors genuinely are low risk.

**Reassess by delta.** Confirmed-unchanged answers should not be re-reviewed.

**Offboard aggressively.** Dormant vendors should not be reassessed, they should be retired. See [Vendor Management](https://app.gitbook.com/s/VzFAfjeuJK2DKd9GcLgy/).

## Reporting

The reassessment view shows vendors by state: current, due, overdue, and lapsed. Overdue high-tier vendors are the number worth watching, because a lapsed assessment on a critical vendor is an unmeasured risk rather than an administrative miss.

For portfolio-level reporting across risk and spend together, see [Spend Insights](https://app.gitbook.com/s/zebllmmpY7BlosLYBwUh/).
