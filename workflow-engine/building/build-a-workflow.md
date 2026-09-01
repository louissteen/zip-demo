---
description: "Create a workflow from an empty canvas: set the trigger, add steps, attach conditions, and configure assignees."
icon: hammer
---

# Build a workflow

Build the happy path first, then add the conditional branches. A workflow that starts as a straight line is much easier to reason about than one assembled branch by branch.

{% stepper %}
{% step %}
## Create the workflow and set its trigger

Go to **Workflows** and select **New workflow**. Choose the object it runs on, such as purchase request or bill, and the event that starts it. Name it for the process, not the team: `Standard purchase approval` rather than `Procurement flow 2`.
{% endstep %}

{% step %}
## Add the steps everything goes through

Add the steps that apply to every record with no condition attached. For a purchase request this is usually manager approval and a procurement final review. Leave them sequential.
{% endstep %}

{% step %}
## Add the conditional review steps

Add legal, security, privacy, tax, and finance as separate steps, each with a condition. Group them into a parallel block so they activate together. See [Conditions and branching](../concepts/conditions-and-branching.md).
{% endstep %}

{% step %}
## Configure assignees and fallbacks

Set each step's assignee. Prefer groups and dynamic references over named individuals, and set a fallback assignee on every dynamically resolved step so it cannot stall unassigned.
{% endstep %}

{% step %}
## Set completion rules

For each group-assigned step, decide whether one approver, all approvers, or a quorum completes it. Default to any one approver unless there is a policy reason not to.
{% endstep %}

{% step %}
## Add thresholds and escalation

Add the amount-gated steps such as department head and executive approval. Configure escalation and delegation so the chain does not stop when someone is out. See [Escalation and delegation](escalation-and-delegation.md).
{% endstep %}

{% step %}
## Set SLAs on the steps that matter

Attach a response target to the steps you report on. See [Step SLAs](step-slas.md).
{% endstep %}

{% step %}
## Simulate, then publish

Run the workflow against real historical records before publishing. See [Test and publish a workflow](../release/test-and-publish.md).
{% endstep %}
{% endstepper %}

{% hint style="warning" %}
Do not add a step for a team that has not agreed to staff the queue. An unstaffed review step is the most common cause of requests aging past their target, and it looks like a Zip problem rather than a staffing one.
{% endhint %}

## Keeping the workflow maintainable

**One workflow per process shape, not per policy variation.** Express variation with conditions on subsidiary and category.

**Name steps for what they decide.** `Confirm budget availability` is more useful on an approver's task list than `Finance step 2`.

**Write the condition in the step description.** Reviewers frequently ask why they received something. A one-line description answers it without anyone opening the builder.

**Review annually against the audit log.** Steps that are approved every time without comment are candidates for auto-approval or removal. Steps that are consistently reassigned point at a wrong assignee reference.
