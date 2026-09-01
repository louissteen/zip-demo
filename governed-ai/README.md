---
description: "The governance layer under every AI feature in Zip: policy, data boundaries, human checkpoints, versioning, evaluation, and audit evidence."
icon: shield-check
---

# Governed AI

Governed AI is the control layer that sits under [AI Procurement Concierge](https://app.gitbook.com/s/cfyHKXX03HFOzcl9ZWBb/), [Superagents](https://app.gitbook.com/s/VraYgcvvYjT6HbxCVqMF/), and [AI Contract Orchestration](https://app.gitbook.com/s/DeZIgDtBPmTV8Lg8mf2S/). It decides what the models may see, what they may do, where a person must intervene, and what evidence gets kept.

It exists because procurement AI touches contracts, banking details, and spend approval. Those are the parts of your business your auditors, your security team, and your regulators ask about first. Governed AI is where you configure the answers and where you export the proof.

<table data-view="cards"><thead><tr><th></th><th></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td><strong>AI policy definition</strong></td><td>Set what AI may do per feature, entity, and category, and who owns each decision.</td><td><a href="policy/ai-policy-definition.md">ai-policy-definition.md</a></td></tr><tr><td><strong>Data boundaries</strong></td><td>What the models can see, what is excluded, and how data is handled in transit and at rest.</td><td><a href="policy/data-boundaries.md">data-boundaries.md</a></td></tr><tr><td><strong>Human checkpoints</strong></td><td>Where a person must decide, and how checkpoints sit in an agent's decision path.</td><td><a href="policy/human-checkpoints.md">human-checkpoints.md</a></td></tr><tr><td><strong>Model and prompt versioning</strong></td><td>Pin versions, stage rollouts, and roll back a change that degrades quality.</td><td><a href="assurance/model-and-prompt-versioning.md">model-and-prompt-versioning.md</a></td></tr><tr><td><strong>Evaluation and drift</strong></td><td>Test sets, release gates, and monitoring for quality that moves after a release.</td><td><a href="assurance/evaluation-and-drift.md">evaluation-and-drift.md</a></td></tr><tr><td><strong>Compliance evidence</strong></td><td>The AI activity record and how to export it for an audit or an assessment.</td><td><a href="assurance/compliance-evidence.md">compliance-evidence.md</a></td></tr></tbody></table>

{% hint style="info" %}
Governed AI settings apply across features. A restriction set here cannot be relaxed inside an individual agent or in Concierge settings.
{% endhint %}
