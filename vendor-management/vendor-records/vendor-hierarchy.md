---
description: "Model parent and child vendor entities so spend, risk, and contracts roll up correctly."
icon: sitemap
---

# Vendor hierarchy

A supplier is rarely one legal entity. A global software company might have a US parent, an Irish entity that sells into Europe, and local subsidiaries elsewhere. You contract and pay each separately, but you negotiate with one company and you want to know what you spend with it in total.

Vendor hierarchy models that. Each legal entity keeps its own record, with its own tax form and bank accounts, and the records are linked under a parent.

## What a parent is for

The parent is a rollup node, not a payable entity. You do not raise a purchase order against a parent. What the parent gives you is:

**Total spend.** Spend across every child entity in one number, which is the number you take into a negotiation.

**Relationship view.** Every contract, event, and assessment across the group in one place.

**Shared attributes.** Vendor tier, internal owner, and category classification set once at the parent and inherited by children unless a child overrides.

**Risk context.** A finding on one entity is visible when you look at another entity in the same group. A breach at the parent is relevant to a subsidiary you buy from, whatever the subsidiary's own assessment says.

## What stays at the child

Anything legally specific to the entity: tax form, tax identifier, bank accounts, remit-to address, and the contracts that entity is party to. These never inherit, because inheriting them is how a payment ends up at the wrong entity.

## Building the hierarchy

{% stepper %}
{% step %}
## Identify the group

Search for existing records by name fragment and by registered address. Companies that belong together often do not share a name, particularly after acquisitions.
{% endstep %}

{% step %}
## Create or designate the parent

Create a parent record for the group. If one entity is genuinely the head and you also transact with it, that record can serve as both parent and a payable entity.
{% endstep %}

{% step %}
## Link the children

On each child record, set the parent. A child can have only one parent, and the hierarchy can be several levels deep.
{% endstep %}

{% step %}
## Set what inherits

Choose which attributes are inherited from the parent and which the child controls. Categories and tier commonly inherit; owner sometimes does not, where a regional entity has a regional owner.
{% endstep %}
{% endstepper %}

{% hint style="warning" %}
Do not use hierarchy to model resellers. A reseller is a separate commercial relationship, not a subsidiary of the manufacturer whose product it sells. Linking them makes spend rollups wrong in both directions. Record the relationship as a related vendor instead.
{% endhint %}

## Enrichment

Where your organization subscribes to a corporate data provider, Zip can propose hierarchy links from that provider's ownership data. Proposals are reviewed rather than applied, because ownership data lags corporate events and because a legal parent is not always the commercial counterparty you deal with.

## Reporting with hierarchy

Spend and contract reporting can be run at either level. Category managers usually work at the parent, since that is the negotiating unit. AP works at the child, since that is what gets paid. For rollup analysis across the vendor base, see [Spend Insights](https://app.gitbook.com/s/zebllmmpY7BlosLYBwUh/).

## Corporate changes

When a vendor is acquired, do not rename the existing record to the acquirer. The entity you contracted with may still exist, and the history belongs to it. Add the new parent, link the record to it, and note the acquisition date. If the entity itself is dissolved and replaced, create the new entity and offboard the old one so the boundary is clear.
