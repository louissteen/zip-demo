---
description: "How inherent and residual risk are scored, and what the resulting tier changes."
icon: gauge-high
---

# Risk scoring and tiering

Scoring exists to drive decisions. If a tier does not change what happens, the score is a number that costs time to produce and nothing to ignore. Configure the consequences first, then the scoring.

## Inherent and residual risk

**Inherent risk** is the exposure before any of the vendor's controls are considered. It comes from what the vendor will do: the sensitivity and volume of data, the level of system access, how critical the service is, the spend, and where the vendor and its data are located.

Inherent risk is known at intake, from the requester's answers. It determines how much assessment the vendor gets.

**Residual risk** is what remains after the vendor's controls are evaluated. It comes from assessment results: which controls are in place, what evidence supports them, and what gaps remain. Open findings and accepted exceptions both raise it.

A vendor can have high inherent risk and low residual risk. That is the normal profile of a well-run vendor doing something sensitive, and it is the point of assessing rather than avoiding.

## Scoring inputs

Within a domain, each question or control contributes according to a weight. Weights reflect consequence, not how many questions cover a topic. Answers can be scored automatically for structured questions and by the reviewer for judgment-based ones.

Findings are scored by severity: critical, high, medium, and low, based on the impact if the gap were exploited and how likely that is.

{% hint style="warning" %}
Do not average away critical findings. A single critical finding should set the vendor's tier regardless of how well everything else scores. Averaging is how a vendor with no encryption reaches an acceptable overall number.
{% endhint %}

## Tiers and consequences

Tiers should map to specific, enforced consequences. A workable pattern:

**Critical.** Executive approval before proceeding, full assessment across all engaged domains, contract terms including audit rights and enhanced notification, annual reassessment, named relationship owner, and continuity planning.

**High.** Full assessment in engaged domains, standard enhanced contract terms, reassessment every one to two years, remediation plans required for high findings.

**Medium.** Reduced questionnaire or certification-based assessment, standard contract terms, reassessment on a longer cycle.

**Low.** Screening only, standard terms, no scheduled reassessment. Reassessed if the relationship changes.

## Overrides

A reviewer can override a calculated tier in either direction. Overrides require a reason and an approver, and both are recorded on the assessment.

Overrides are useful and also the first thing an auditor examines. A high rate of downward overrides usually means the scoring model is miscalibrated for your business rather than that reviewers are being lenient.

## Where the tier shows up

The tier is written to the vendor record and is available to workflow conditions everywhere in Zip. It commonly drives which approvals are required on future requests for that vendor, which contract terms are mandatory, the reassessment interval, whether the vendor may be used for new use cases without further review, and how the vendor appears in reporting.

For how the tier is displayed and maintained on the vendor, see [Vendor Management](https://app.gitbook.com/s/VzFAfjeuJK2DKd9GcLgy/).

## Reviewing the model

Review the scoring model periodically against outcomes. If incidents and issues cluster in vendors your model rated low, the model is measuring the wrong things. That review is more valuable than adding questions.
