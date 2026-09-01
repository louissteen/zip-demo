---
description: "Build evaluation sets for Zip AI features, gate releases on them, and monitor for quality drift after a change."
icon: microscope
---

# Evaluation and drift monitoring

Evaluation answers whether a change is safe to ship. Drift monitoring answers whether something already shipped has quietly stopped working. You need both, and they use different data.

## Evaluation sets

An evaluation set is a fixed collection of real cases with a known correct outcome. Build them from your own history rather than from generic examples, because the failures that matter are specific to your vendors, your categories, and your document formats.

Good sets include the ordinary cases, the edge cases your team argues about, the cases an agent previously got wrong, and cases that should stop rather than proceed. Sets without stop cases only measure eagerness.

Manage sets in **Settings**, then **AI**, then **Governance**, and open the **Evaluation** tab.

## Build a set

{% stepper %}
{% step %}

## Select source cases

Filter historical runs or answers by feature, category, and outcome. Include reversed runs and rejected checkpoints, which are your highest-signal cases.

{% endstep %}
{% step %}

## Record the expected outcome

For each case, record what should happen: the correct coding, the correct routing, or that the case should stop for a human. Have the team that owns the work confirm these rather than deriving them from what the agent did.

{% endstep %}
{% step %}

## Set a passing bar

Define the score the set must clear for a release to proceed, and which cases are blocking regardless of the overall score.

{% endstep %}
{% step %}

## Attach it as a release gate

Attach the set to the feature. Version changes then run it automatically before staging. See [Model and prompt versioning](model-and-prompt-versioning.md).

{% endstep %}
{% endstepper %}

{% hint style="warning" %}
Refresh evaluation sets on a schedule. A set built two years ago passes reliably and tells you nothing, because your process, your vendors, and your document formats have all moved.
{% endhint %}

## Drift monitoring

Drift is quality change without a version change. Its usual causes are business rather than technical: a new vendor sends invoices in a different layout, a category's policy changes, a reorganization moves cost centers, an integration starts returning different values.

Zip tracks these signals continuously per feature:

* Reversal rate by category, vendor, and entity
* Confidence distribution, watching for a shift rather than an absolute level
* Stop reason mix
* Checkpoint rejection rate
* Concierge deflection reasons, covered in [Coverage reporting](https://app.gitbook.com/s/cfyHKXX03HFOzcl9ZWBb/)

Alerts fire against a rolling baseline, and they are directed to the feature owner rather than to a general channel. Set thresholds narrow enough to catch a real move and wide enough that people still read the alerts.

## Responding to drift

Find the segment first. Drift is nearly always concentrated in one vendor, one category, or one entity, and a global response to a local problem makes the next investigation harder. Narrow the affected scope, fix the cause, add the failing cases to your evaluation set, then widen again.

Both evaluation results and drift alerts are part of the AI activity record and appear in the export described in [Compliance evidence](compliance-evidence.md).
