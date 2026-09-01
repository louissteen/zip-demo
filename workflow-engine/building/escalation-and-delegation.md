---
description: "Keep approvals moving when an approver is on leave, unresponsive, or no longer with the company."
icon: user-clock
---

# Escalation and delegation

Approval chains stop for human reasons far more often than technical ones. Zip offers three mechanisms, and they solve different problems.

## Delegation

Delegation is set by the approver, in advance, for a defined period. It is the out-of-office mechanism.

While a delegation is active, steps assigned to the delegator are also assigned to the delegate. The delegate can act, and the audit log records both names: who acted, and who they acted for.

Delegation does not transfer authority beyond the delegator's own. A delegate acting for a department head approves only what that department head could have approved.

{% hint style="info" %}
Encourage approvers to set delegation before leave rather than relying on escalation to catch it. Delegation names a person who has context; escalation usually names someone who does not.
{% endhint %}

## Escalation

Escalation is configured by an administrator on the step, and fires automatically when a response target is missed.

Configure three things:

**When it fires.** After the step's SLA elapses, or after a fixed period from activation.

**What it does.** Reminder only, add an escalation assignee alongside the original, reassign to the escalation assignee, or auto-approve.

**Who it goes to.** Usually the assignee's manager, the group's owner, or the procurement owner for the category.

Escalation is typically staged: a reminder first, then a manager is added, then the procurement owner is notified.

{% hint style="danger" %}
Auto-approve on escalation converts an unstaffed queue into approved spend with no human review. If you use it, restrict it to low-value, low-risk steps, and report on how often it fires. A rising auto-approve rate is a staffing signal, not a success metric.
{% endhint %}

## Reassignment

Reassignment is manual, done by an operator or administrator when neither delegation nor escalation applies. The most common case is an approver who has left the company.

When a user is deactivated through SCIM, their open steps are surfaced for reassignment rather than silently dropped. See [SSO and provisioning](https://app.gitbook.com/s/dxaoa7neP0H4mhCCMRFl/).

## Choosing between them

<details>

<summary>Which mechanism for which situation</summary>

**Approver on planned leave.** Delegation, set by the approver.

**Approver unexpectedly unavailable.** Escalation to their manager after the SLA elapses.

**Whole queue is behind.** Escalation to the group owner, plus a conversation about staffing. Do not solve a capacity problem with auto-approval.

**Approver has left the company.** Reassignment, triggered by deactivation.

**Approver is the requester.** Configure the step to skip self-approval and route to the next level up. Set this deliberately; without it, a department head can approve their own request.

</details>

## Reporting on it

Track delegation coverage, escalation frequency, and reassignment volume in [Spend insights](https://app.gitbook.com/s/zebllmmpY7BlosLYBwUh/). Repeated escalation on one step is a design problem: either the assignee is wrong, the SLA is unrealistic, or the step should not exist.
