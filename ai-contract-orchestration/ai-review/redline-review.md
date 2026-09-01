---
description: "Compare an incoming contract against your playbook and work through the deviations."
icon: pen-ruler
---

# Redline review

Redline review answers one question for a legal reviewer: where does this document differ from what we are willing to sign, and how far off is it. Everything that matches your standard positions is set aside so the reviewer reads the exceptions.

## Your playbook

The playbook is your set of positions by clause type. For each clause it records:

* The preferred position, the language you would like.
* The fallback position or positions, what you will accept without escalation.
* The unacceptable position, what requires escalation to a named approver.
* Guidance for the reviewer, the reasoning behind the position.

Playbooks are maintained by legal and can vary by agreement type, by counterparty tier, and by region. A vendor agreement under a low threshold does not need the same liability position as a strategic multi-year commitment.

## Running a review

{% stepper %}
{% step %}
## Upload the counterparty document

Open the contract record and upload the supplier's version. Zip extracts the clauses and compares each one against the applicable playbook.
{% endstep %}

{% step %}
## Read the deviation summary

The summary lists every clause that does not match a preferred or fallback position, classified by severity. Clauses that match your positions are grouped and collapsed.
{% endstep %}

{% step %}
## Work each deviation

For each one, Zip shows the counterparty's language, your preferred and fallback language, and the guidance from the playbook. Accept the counterparty position, propose your fallback, or write your own language.
{% endstep %}

{% step %}
## Generate the redline

Zip produces a marked-up version of the document containing your proposed changes, with a comment on each change explaining the position. Review it before it goes out.
{% endstep %}

{% step %}
## Send and track

Send the redline to the counterparty. When they respond, upload their version and run the comparison again. Each round is retained on the contract record.
{% endstep %}
{% endstepper %}

{% hint style="warning" %}
A clause missing from the document is not the same as a clause that matches your position, and it is the failure mode reviewers miss most often. Zip flags absent clauses that your playbook requires, but confirm the list on any agreement drafted from unfamiliar paper.
{% endhint %}

## Escalation

A deviation classified as unacceptable adds an approval step for the named escalation approver, usually a general counsel or a designated deputy depending on the clause. The reviewer cannot clear the contract by accepting an unacceptable position without that approval, and the approval is recorded on the contract.

## Tracking positions over time

Because every review records which positions you accepted and where, you can see how often a given fallback is actually used. Fallbacks that are always accepted are candidates to become the preferred position. Preferred positions that never survive negotiation are costing you rounds without changing outcomes.

The playbook analytics view shows acceptance rates by clause and by counterparty, which is the basis for reviewing the playbook periodically rather than when someone complains.

For how these reviews route to approvers, see [Legal review and approval](../contract-intake/legal-review-and-approval.md).
