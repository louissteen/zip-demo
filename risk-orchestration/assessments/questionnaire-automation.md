---
description: "Reduce the questions vendors answer by reusing evidence, prior answers, and documentation."
icon: robot
---

# Questionnaire automation

The security questionnaire is the slowest part of vendor risk. A vendor receives a long spreadsheet, routes it to a team that answers dozens of these a month, and returns it weeks later. Zip reduces the questions asked rather than only speeding up the sending.

## Reuse of prior answers

When a vendor has answered a question before, in an earlier assessment or for a different business unit, the previous answer is prefilled with its date and source. The vendor confirms it is still accurate or updates it.

Confirmation is required rather than assumed. An answer carried forward without the vendor confirming it is an answer nobody currently stands behind.

## Certification mapping

Where a vendor holds a recognized certification or has an audit report, Zip maps the controls that document covers to the questions in your questionnaire and marks them as evidenced. The vendor answers only what the certification does not cover.

This is where most of the reduction comes from. A vendor with a current audit report covering the majority of your control set answers a fraction of the questionnaire.

{% hint style="warning" %}
Check the scope of a certification, not just its existence. An audit report covering one product line does not evidence controls for the product you are buying, and a certificate with a stale validity period evidences nothing. Zip records the scope and validity dates so a reviewer can check both.
{% endhint %}

## Document ingestion

Vendors often have their own answers already written: a security overview, a trust page, a completed standard questionnaire in an industry format. Zip reads uploaded documents and proposes answers with a link to the source passage.

Proposals go to the vendor for confirmation, not straight into the assessment. The vendor is the party attesting, so the vendor confirms.

## Reviewer assistance

On the reviewer's side, Zip summarizes what changed since the last assessment, highlights answers that conflict with supplied evidence, and flags responses that fall outside your defined acceptable positions.

Reviewers work exceptions rather than reading every answer. The full response set stays available, and the reviewer's own conclusions are what the assessment records. For how AI features handle vendor documents and what is logged, see [Governed AI](https://app.gitbook.com/s/oovoef3hZyAQg9DepDDH/).

## Chasing responses

Assessments stall in the vendor's queue more often than anywhere else. Zip sends reminders on a schedule, escalates to the vendor's commercial contact when the security contact does not respond, and notifies the internal requester so they can apply the pressure that actually works.

The assessment aging report shows what is outstanding, with whom, and for how long. Sort it by the value of the linked request, since that is what determines how hard to push.

<details>

<summary>Can we accept a vendor's own completed questionnaire in a standard format?</summary>

Yes. Upload it and Zip maps the answers onto your question set, flagging anything your questionnaire asks that theirs does not cover. The vendor confirms the mapped answers and completes the gaps. This is usually faster than asking a vendor to complete your format from scratch.

</details>

<details>

<summary>Does automation reduce the rigor of the assessment?</summary>

It changes what reviewers spend time on. The same controls are evaluated; the difference is that evidence already provided is not requested again, and reviewer attention goes to gaps and exceptions rather than to transcription.

</details>
