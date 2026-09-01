---
description: "How an unanswered Concierge question becomes a queued task for your procurement team, and how the answer returns to the requester."
icon: user-headset
---

# Handoff to a human

A handoff is what happens when the Concierge cannot answer, or when the requester asks for a person. The conversation does not end. It becomes a tracked task with the question, the context, and the requester attached, so nobody has to re-explain the problem.

## When a handoff triggers

* The Concierge has no configured source for the topic.
* The retrieved policy is ambiguous or contradicts itself.
* The requester asks for an exception, a negotiated term, or anything requiring judgment.
* The requester selects **Talk to a person** at any point in the conversation.
* The topic is on an administrator's always-escalate list. See [Tuning answers](../administration/tuning-answers.md).

## What the team receives

The handoff creates a task in the procurement queue containing the original question in the requester's own words, the conversation transcript, the sources the Concierge retrieved and why it judged them insufficient, and the requester's department, subsidiary, and any request already in flight.

Handoffs route with the same conditions as any other work in Zip, so a question about a security review reaches your IT security reviewers rather than a general inbox. Routing rules live in the [workflow engine](https://app.gitbook.com/s/cCva0sBd9z7KRG56Fq0I/).

## How the answer comes back

The assignee replies in the task. The requester receives the reply in the channel where they asked, so a question started in Slack is answered in Slack.

{% hint style="info" %}
When an assignee marks a reply as reusable, it becomes a candidate answer for the same question next time. Reviewing those candidates is the fastest way to expand coverage, because they are written by your own team about questions your own users actually asked.
{% endhint %}

<details>
<summary>Handoffs and the audit trail</summary>

Every handoff records the question, the deflection reason, the assignee, the reply, and the time between them. These records are part of the AI activity log described in [Governed AI](https://app.gitbook.com/s/oovoef3hZyAQg9DepDDH/), and they are exportable with the rest of your AI compliance evidence.

</details>

## Reducing handoffs over time

Handoffs are a signal, not a failure. A topic that generates repeated handoffs is usually a topic where your written policy has a gap. Work the list in [Coverage reporting](../administration/coverage-reporting.md) from the top: the highest-volume deflection is nearly always worth writing down once.
