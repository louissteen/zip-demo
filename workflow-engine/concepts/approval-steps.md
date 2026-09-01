---
description: "Sequential and parallel steps, how assignees are resolved, and what approve, reject, and return actually do."
icon: circle-check
---

# Approval steps

A step is one unit of decision in the chain. It has an assignee, an action type, and a completion rule.

## Sequential and parallel

**Sequential** steps run one after another. Each waits for the previous to complete. Use sequential when a later approver needs the earlier decision as context, for example an executive approving after finance has confirmed the budget position.

**Parallel** steps run at the same time. All of them activate together, and the chain moves on when the group completes. Use parallel for independent functional reviews: legal, security, privacy, and tax have no reason to wait for each other.

{% hint style="info" %}
Parallel reviews are the single largest cycle time improvement available in most workflows. If your legal and security reviews are sequential today, check whether either actually depends on the other's output. Usually neither does.
{% endhint %}

## Resolving the assignee

Assignees are rarely named individuals. Zip resolves them at the moment the step activates, using one of:

**A named user.** Simple, and fragile. Use only for genuinely singular roles.

**A group or team.** The step goes to a queue that any member can claim and action. Best for functional reviews.

**A dynamic reference.** Resolved from the record: the requester's manager, the department owner, the budget owner, the procurement owner for the category, the subsidiary controller. This is the most durable option because it survives reorganizations.

**A hierarchy walk.** Climb the management chain until someone with sufficient approval authority is reached. Used for amount-based approvals.

<details>

<summary>When the assignee cannot be resolved</summary>

Resolution can fail: a requester with no manager set, a department with no owner, a hierarchy that runs out before the threshold is met.

Configure a fallback assignee on every dynamically assigned step. Without one, the step stalls with no one assigned, and stalled steps are only discovered when someone chases the request.

</details>

## Completion rules

For a step assigned to a group, decide what completes it:

**Any one approver.** The first response decides. Standard for functional review queues.

**All approvers.** Every named assignee must respond. Use sparingly; it is the slowest possible configuration.

**A quorum.** A defined number must approve. Used for committee-style approvals such as a capital review board.

## What an approver can do

**Approve** completes the step and advances the chain.

**Reject** ends the chain and returns the record to the requester. Rejection is final for that submission; the requester can revise and resubmit, which builds a new chain.

**Return for information** pauses the step and sends a question to the requester. The step stays assigned to the same approver, so answering returns it to them rather than restarting.

**Reassign** hands the step to someone else, with the change recorded on the history.

**Add an ad hoc approver** inserts a step for someone the workflow did not anticipate, either before or after the current step. This is how a reviewer pulls in a specialist without an administrator editing the workflow.

## Auto-approval

Steps can be configured to auto-approve when a condition is met, for example a renewal at the same amount with the same vendor and no contract change. Auto-approvals are recorded in the [audit log](https://app.gitbook.com/s/dxaoa7neP0H4mhCCMRFl/) with the rule that applied, so they are distinguishable from human decisions.

Use auto-approval for volume, not for risk. It works well on low-value repeat spend and badly anywhere a human would have caught something.
