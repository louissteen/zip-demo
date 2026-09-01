---
description: "What the onboarding form asks vendors, how it adapts, and how to keep it short."
icon: list-check
---

# The onboarding questionnaire

The onboarding questionnaire is what the vendor fills in. It should ask for the minimum needed to pay the vendor lawfully and to know who you are dealing with. Everything beyond that belongs in a risk assessment, which only applies to the vendors that warrant one.

## What is always asked

**Legal identity.** Registered legal name, trading name if different, registration number, registered address, and country of incorporation.

**Tax.** Tax identification number and the appropriate tax form for the jurisdiction. See [Tax forms](../vendor-submission/tax-forms.md).

**Remittance.** Bank account details, the currency the vendor is paid in, and a remittance email address. See [Banking details and verification](../vendor-submission/banking-details.md).

**Contacts.** An accounts receivable contact and, usually, a commercial contact. Vendors can add more later in the portal.

**Diversity and classification.** Where your organization tracks supplier diversity, small business status, or similar classifications, these are collected here with the supporting certificates.

## Conditional sections

The form adapts to what the vendor is. Conditions read the country, the category, the expected spend, and answers earlier in the form.

A vendor in a country with withholding requirements sees the additional tax questions for that country. A vendor supplying services on your premises sees insurance certificate uploads. A software vendor sees a short set of questions establishing whether a full security assessment is needed. A vendor under a low spend threshold sees a shortened form.

{% hint style="info" %}
Resist the temptation to ask everything of everyone. Every question you add is asked of every vendor that reaches it, and long forms are the main reason onboarding stalls. Ask what you need to pay them; assess risk separately for the vendors where risk is real.
{% endhint %}

## Validation as the vendor types

Fields are validated at entry rather than at review, so errors come back to the vendor in seconds instead of days.

Tax identification numbers are checked for format by country and, where a government service supports it, validated against the register. Bank details are checked against the format for the country and currency. Addresses are standardized. Required documents are checked for the right form type and for legibility.

## Attachments and evidence

Common attachments are the tax form, a bank verification document such as a voided check or a bank letter, certificates of insurance, and any diversity certification. Each attachment slot states what is acceptable and what is not, which prevents most of the back and forth.

## Configuring the form

Administrators configure the questionnaire on the **Supplier onboarding** settings page. The form is versioned: vendors part-way through continue on the version they started, and the version used is recorded on the vendor record.

Test conditional branches in preview before publishing, particularly the country branches, because a vendor cannot work around a section that fails to appear.

<details>

<summary>Can we onboard a vendor in more than one language?</summary>

The questionnaire can be published in multiple languages, and the vendor selects its language in the portal. Translate the guidance text as well as the field labels, since the guidance is what prevents wrong submissions.

</details>
