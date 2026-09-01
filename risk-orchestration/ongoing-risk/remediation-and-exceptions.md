---
description: "Track findings to closure, or accept them formally with an owner and an expiry."
icon: screwdriver-wrench
---

# Remediation and exceptions

An assessment that produces findings and no follow-up is a document, not a control. Every finding ends one of three ways: remediated, formally accepted as an exception, or resolved by not proceeding.

## Findings

A finding records the gap, the domain it belongs to, its severity, the evidence behind it, and what would close it. It has an owner, which may be the vendor or someone on your side, and a due date derived from severity.

Write the closure condition when the finding is raised. "Vendor to improve access controls" cannot be closed, because nobody can tell when it is done. "Vendor to enable multi-factor authentication for all administrative accounts and provide configuration evidence" can.

## Remediation

{% stepper %}
{% step %}
## Agree the plan

The finding owner proposes what will be done and by when. For vendor-owned findings, the vendor proposes and your reviewer accepts or pushes back on the date.
{% endstep %}

{% step %}
## Set a compensating control if needed

Where remediation takes time, agree what limits exposure meanwhile: restricted data scope, limited access, additional monitoring, or a contractual commitment. Compensating controls are recorded on the finding, not agreed informally.
{% endstep %}

{% step %}
## Track to the due date

The vendor updates progress in the portal and your reviewer sees it on the finding. Reminders go out ahead of the date and escalate after it.
{% endstep %}

{% step %}
## Verify closure

Closure requires evidence that satisfies the condition written when the finding was raised. The reviewer verifies and closes. A finding closed on the vendor's assertion alone should be recorded as an exception instead.
{% endstep %}
{% endstepper %}

## Exceptions

An exception is a decision to accept a risk rather than fix it, usually because remediation is not feasible, not proportionate, or not possible before the business needs the vendor.

Every exception carries the risk being accepted in plain terms, the business justification, any compensating controls, an approver at the authority level the severity requires, an expiry date, and a named owner.

{% hint style="warning" %}
An exception without an expiry date is not an exception, it is a decision to stop tracking. Every exception expires and is re-decided by someone accountable, even if the answer is usually to renew it.
{% endhint %}

## Approval authority

Approval authority should scale with severity. Low and medium findings can be accepted by the domain owner. High findings should require a senior risk owner. Critical findings should require an executive, and the request should be uncomfortable enough that it is made only when genuinely warranted.

Authority levels are configured as approval steps like any other, so exception approvals go through the same workflow and the same record. See [Workflow Engine](https://app.gitbook.com/s/cCva0sBd9z7KRG56Fq0I/).

## Expiry and review

Zip notifies the owner before an exception expires. At expiry the exception is renewed with fresh approval, closed because the underlying finding was remediated, or escalated because neither has happened.

Expired exceptions that nobody acted on appear on the risk register with the same visibility as an open critical finding, because that is effectively what they are.

## The risk register

The register is the aggregate view: every open finding and active exception across the vendor base, filterable by domain, severity, vendor tier, owner, and age. It is the standing agenda for a risk review meeting and the report you hand an auditor when they ask what you know about your third parties.
