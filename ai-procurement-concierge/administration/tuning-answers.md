---
description: "Correct a wrong Concierge answer, pin a preferred answer, scope answers by audience, and force escalation on sensitive topics."
icon: sliders
---

# Tuning answers

Administrators tune the Concierge from the **Answers** tab in **Settings**, then **AI**, then **Concierge**. Tuning changes what the assistant says without changing the underlying records, so it is safe to iterate on.

## Correct a wrong answer

{% stepper %}
{% step %}

## Find the conversation

Open the **Answers** tab and filter by topic, by department, or by answers a requester marked as unhelpful. Each row shows the question, the answer given, and the sources used.

{% endstep %}
{% step %}

## Decide whether the source or the answer is wrong

If the source itself is out of date, fix the source. A correction layered on top of a stale policy hides the real problem. If the source is right but the Concierge read it badly, continue here.

{% endstep %}
{% step %}

## Write the corrected answer

Select **Correct answer** and write what the assistant should have said. Write it as an answer to a requester, in the same voice you would use in a reply, not as a note to yourself.

{% endstep %}
{% step %}

## Scope and publish

Set the audience the correction applies to, then select **Publish**. The correction takes effect on new questions immediately.

{% endstep %}
{% endstepper %}

## Pinned answers

A pinned answer is used verbatim for a topic, regardless of what retrieval returns. Pin an answer when the wording matters: an approved definition of a policy threshold, a required disclosure, or a statement legal has signed off on.

Keep the pinned set small. Every pinned answer is one your team has to maintain by hand, and a stale pin is worse than no pin because it outranks the live source.

## Audience scoping

Scope any correction or pin by department, subsidiary, region, or category. Scoping is how you handle a policy that genuinely differs across the business without maintaining separate assistants.

{% hint style="info" %}
When two scoped answers both match a requester, the more specific scope wins. A correction scoped to one subsidiary and one category beats one scoped to the subsidiary alone.
{% endhint %}

## Escalation rules

Add a topic to the always-escalate list when you never want an automatic answer, even if a good one is available. Common candidates are exception requests, anything touching data residency commitments, and questions about an active negotiation. Escalated topics go straight to [handoff](../using-the-concierge/handoff-to-a-human.md).

<details>
<summary>Change history on tuning</summary>

Every correction, pin, scope change, and escalation rule is versioned with its author and timestamp, and appears in the AI change record described in [Governed AI](https://app.gitbook.com/s/oovoef3hZyAQg9DepDDH/). You can compare versions and roll back a pinned answer to a previous wording.

</details>
