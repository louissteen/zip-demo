---
description: "Set up SAML single sign-on and SCIM user provisioning so Zip accounts follow your identity provider."
icon: key
---

# SSO and provisioning

Zip authenticates users through your identity provider using SAML 2.0, and keeps accounts current using SCIM. Configure SSO first, confirm you can sign in, then enable provisioning.

## Configure single sign-on

{% stepper %}
{% step %}
## Create the application in your IdP

In Okta, Entra ID, or your equivalent, create a new SAML application for Zip. Zip supplies the assertion consumer service URL and entity ID on the SSO settings page.
{% endstep %}

{% step %}
## Map the required attributes

Zip needs an email address as the name identifier, plus first name and last name. Map any additional attributes you plan to use for role mapping, such as department or group membership.
{% endstep %}

{% step %}
## Upload the IdP metadata

Paste the sign-on URL and the signing certificate, or upload the metadata file, into Zip's SSO settings.
{% endstep %}

{% step %}
## Test with a pilot user

Assign the application to one administrator and sign in through the IdP. Confirm the session lands on the Zip home page and the user's name and email are correct.
{% endstep %}

{% step %}
## Enforce SSO

Once the pilot succeeds, turn on enforcement so password sign-in is disabled for your domain. Keep at least one break-glass administrator account documented with your IT team.
{% endstep %}
{% endstepper %}

{% hint style="danger" %}
Enforce SSO only after a successful test sign-in. If enforcement is enabled while the SAML configuration is wrong, no one can sign in, and recovery requires contacting Zip support.
{% endhint %}

## Configure SCIM provisioning

SCIM keeps the user list accurate without anyone maintaining it by hand. Zip supports user create, update, and deactivate, plus group push.

{% stepper %}
{% step %}
## Generate a SCIM token

In Zip's provisioning settings, generate a bearer token and copy the SCIM base URL. The token is shown once.
{% endstep %}

{% step %}
## Enable provisioning in your IdP

Paste the base URL and token into the application's provisioning tab. Enable create, update, and deactivate. Leave push groups off until user sync is confirmed.
{% endstep %}

{% step %}
## Push a test group

Assign a small group and confirm the users appear in Zip with the expected attributes.
{% endstep %}

{% step %}
## Map groups to roles

Map each pushed group to a Zip role and scope. A group such as `zip-ap-emea` maps to the AP operator role scoped to the EMEA subsidiaries.
{% endstep %}
{% endstepper %}

## How deactivation behaves

When a user is deactivated in the IdP, Zip deactivates the account and blocks sign-in. Their historical records are preserved, and their name still appears on past approvals.

Live work is not silently dropped. Open approval steps assigned to a deactivated user are surfaced for reassignment, and any delegation rule they configured stops applying. See [Roles and permissions](roles-and-permissions.md) for how to reassign.

{% hint style="info" %}
Group-to-role mapping is evaluated on every SCIM update. Removing a user from a group removes the role at the next sync, so use group membership rather than manual role edits as your source of truth.
{% endhint %}
