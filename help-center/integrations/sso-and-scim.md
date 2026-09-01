---
description: "Set up single sign-on and automated user provisioning so access to Zip follows your identity provider."
icon: key
---

# SSO and user provisioning

Zip supports SAML 2.0 single sign-on and SCIM provisioning with the common identity providers, including Okta, Entra ID, Google Workspace and OneLogin.

## Single sign-on

With SSO enabled, users sign in through your identity provider and never hold a Zip password.

{% stepper %}
{% step %}
## Create the application in your IdP

Add Zip as a SAML application. Zip supplies the ACS URL and entity ID under **Settings**, then **Security**, then **Single sign-on**.
{% endstep %}

{% step %}
## Exchange metadata

Upload your IdP metadata to Zip, or paste the sign-in URL and signing certificate.
{% endstep %}

{% step %}
## Map attributes

Map email, first name and last name at minimum. Department and manager are worth mapping too, since Zip can use them in approval routing.
{% endstep %}

{% step %}
## Test, then enforce

Test with a pilot group before enforcing SSO for everyone.
{% endstep %}
{% endstepper %}

{% hint style="warning" %}
Keep at least one administrator able to sign in without SSO until you have confirmed the configuration works. Enforcing SSO with a broken configuration locks everyone out.
{% endhint %}

## SCIM provisioning

SCIM creates, updates and deactivates Zip users automatically from your identity provider.

* A new hire added to the Zip group in your IdP gets a Zip user
* An attribute change, such as a department move, updates the Zip user
* A leaver removed from the group is deactivated in Zip, and their in-flight approvals are surfaced for reassignment

{% hint style="info" %}
Deactivation does not delete history. The user's past approvals and comments remain on the record for audit.
{% endhint %}

## Gating the help center

If your help center is restricted to signed-in users, the same identity provider controls access to it. Readers sign in once and reach both Zip and the documentation.

## Related articles

* [SSO and provisioning in the product documentation](https://app.gitbook.com/s/dxaoa7neP0H4mhCCMRFl/administration/sso-and-provisioning)
* [Roles and permissions](https://app.gitbook.com/s/dxaoa7neP0H4mhCCMRFl/administration/roles-and-permissions)
