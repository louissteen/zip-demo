---
description: "Find duplicate vendor records, decide which to keep, and merge them without losing history."
icon: clone
---

# Duplicate detection and merging

Duplicates are created by ordinary behavior: someone cannot find a vendor and creates it, a legal name and a trading name are entered as two companies, an ERP migration loads records that already exist. The cost is real. Spend splits across records so nothing looks material, a negotiation misses half your volume, and payment can go to whichever record happens to hold the older bank account.

## Prevention at the point of creation

The cheapest duplicate is the one never created. During onboarding, Zip matches the submission against existing vendors before the record is created and holds an apparent match for review.

Matching compares tax identifier, legal name after normalization, address, domain from the contact email, and bank account. Tax identifier and bank account are strong signals. Name alone is weak, since large companies have many entities with near-identical names.

{% hint style="info" %}
Give buyers a good search before you give them a duplicate check. Most duplicates are created by someone who genuinely could not find the existing record, usually because it is filed under a legal name nobody uses. Keeping trading names on records prevents more duplicates than any matching rule.
{% endhint %}

## Finding duplicates in the existing master

The duplicate report scores candidate pairs and groups them by confidence. Work the high-confidence groups first, and work by spend rather than alphabetically, since merging two dormant records changes nothing.

Each candidate pair shows the fields that match, the fields that conflict, and the transaction volume on each record. Conflicting bank accounts on an otherwise strong match deserve attention on their own, whether or not you merge.

## Merging

{% stepper %}
{% step %}
## Confirm they are the same legal entity

This is the decision the whole process rests on. Two entities in the same group are not duplicates, they are a hierarchy. Check the tax identifiers. Different tax IDs almost always mean different entities.
{% endstep %}

{% step %}
## Choose the surviving record

Keep the record with the most complete and most current data, and with the cleanest ERP linkage. Transaction volume matters less than data quality, because history follows the merge.
{% endstep %}

{% step %}
## Resolve field conflicts

For each conflicting field, choose the value to keep. Zip defaults to the surviving record's value and shows the alternative. Take particular care with bank accounts and tax forms: pick the one the vendor most recently attested to, not the one with more payments against it.
{% endstep %}

{% step %}
## Review what moves

Zip lists everything that will be repointed: requests, purchase orders, contracts, invoices, bills, payments, and assessments. Check for open transactions on the record being retired.
{% endstep %}

{% step %}
## Merge

The merged record is retired, not deleted. It keeps a pointer to the survivor so any reference, link, or report that used the old identifier resolves to the right vendor.
{% endstep %}

{% step %}
## Reconcile with the ERP

Merges must be reflected in the ERP as well. Zip pushes the merge where the integration supports it; where it does not, the ERP record is deactivated manually and the mapping updated.
{% endstep %}
{% endstepper %}

{% hint style="warning" %}
Merges are hard to unwind once transactions have been repointed. Where you are not confident two records are the same entity, link them as related vendors and leave them separate. A pair of linked records is a minor annoyance; a wrong merge is a data recovery exercise.
{% endhint %}

## Measuring the problem

Track duplicates created per month, not just duplicates merged. A merge program that runs alongside an unchanged creation process never finishes. If duplicates keep appearing at onboarding, the fix is in search and matching, not in cleanup.
