---
description: "How vendors provide bank details and how Zip confirms the account belongs to the vendor."
icon: building-columns
---

# Banking details and verification

Bank details decide where money goes, which makes them the highest risk field in the whole vendor record. Zip collects them from the vendor directly in the portal, validates the format, and verifies that the account belongs to the vendor before the vendor can be paid.

## What the vendor provides

The fields depend on the country and currency. Zip presents the correct set rather than a generic form.

* Account holder name, which must match the vendor's legal entity
* Account number, or IBAN where applicable
* Routing identifier: ABA routing number, sort code, BSB, SWIFT or BIC, as the country requires
* Bank name and branch address
* Account currency
* Intermediary bank details where cross-border payment requires them

Zip validates identifiers structurally as they are entered: IBAN check digits, routing number checksums, and the length and format expected for the country. Around three quarters of bad bank data is caught here rather than by a returned payment.

## Verification methods

Format validation proves the number is well formed. Verification proves the account is the vendor's.

**Document evidence.** The vendor uploads a bank letter, a voided check, or a bank statement header. A reviewer confirms the account holder name and number match what was entered.

**Account validation service.** Where supported, Zip checks the account against a bank data service that confirms the account exists and that the holder name matches.

**Micro-deposit confirmation.** Zip sends a small deposit to the account and the vendor confirms the amount in the portal. Slower, but strong evidence the vendor controls the account.

**Callback verification.** A member of your team calls the vendor on a number obtained independently, never a number supplied in the same message as the bank details, and confirms the account verbally. Record the call on the onboarding record.

{% hint style="danger" %}
Callback verification only works if the phone number comes from a source other than the request. Fraudulent bank change requests include a phone number that reaches the fraudster. Use a number from the signed contract, from your existing vendor record, or from the vendor's published website.
{% endhint %}

## Changing bank details later

A change to bank details on an existing vendor is treated more carefully than the original submission, because an established vendor with a payment history is the target worth attacking.

{% stepper %}
{% step %}
## The vendor initiates the change in the portal

Changes are submitted by the vendor through the [vendor portal](https://app.gitbook.com/s/6BeW2bup2FUvVioEI5Le/) using its own credentials. Changes requested by email are not actioned.
{% endstep %}

{% step %}
## Payments are held

Zip places a hold on scheduled payments to that vendor while the change is pending, so a payment cannot go out to an unverified account.
{% endstep %}

{% step %}
## The change is verified independently

The change goes through verification again, and your policy normally requires a callback for bank changes regardless of what was used at onboarding.
{% endstep %}

{% step %}
## A second person approves

Bank changes require approval by someone other than the person who verified them. The old and new details are shown side by side.
{% endstep %}

{% step %}
## The hold is released

Once approved, the change is written to the vendor record and to the ERP, and payments resume. Existing vendor contacts are notified that the details changed, which gives the real vendor a chance to raise the alarm.
{% endstep %}
{% endstepper %}

## Access and audit

Full account numbers are masked for users without the banking permission, and every view, change, and approval is logged with the user and timestamp. The log is the record you need when a payment is disputed.
