# Workspace Administration
Configure access & security

SAML single Sign on
(Workspace owners and Admins)
(Workspace Owner != Primary Owner)

* Enable SAML with IDP ?
(JumpCloud)

* Enable SSO feature in Slack
(Workspace Owner) 
( toggle test mode to try the connection and make sure it passes)

From your desktop, click your workspace name in the top left.
Select Administration, then Workspace settings from the menu.
Click the Authentication tab.
Click Configure next to SAML authentication, choose your SAML provider, then click Configure.
Next to SAML SSO URL, enter your SAML 2.0 Endpoint URL (HTTP). (This would have come from setting up your connector. If Okta is your provider, you can include the IDP URL if you'd like.)
Enter your IDP Entity ID next to Identity Provider Issuer. 
Copy the entire x.509 Certificate from your identity provider and paste it in the Public Certificate field.
Click Expand next to Advanced Options. Choose how the SAML response from your IDP is signed. If you need an end-to-end encryption key, check the box next to Sign AuthnRequest to show the certificate.
Under Settings, decide if members can edit their profile information (like their email or display name) after SSO is enabled. You can also choose whether SSO is required, partially required* or optional.
Under Customize, enter a Sign In Button label.
Select Save Configuration to finish. 
Note: If you have guest accounts, we recommend choosing the option where SSO is partially required, so guests can still sign in to the workspaces they have access to.


What to expect after SSO is enabled
When you've finished setting up SSO, each member will receive an email letting them know about the change. The email will prompt members to connect — or bind — their Slack accounts with your identity provider. Members will have 72 hours to bind their account before their link expires.

From now on, all members will sign in to Slack with their identity provider account. If you chose to require SSO, members will see a sign in page when they visit your Slack URL.

Tip: To simplify member management, Slack supports the SCIM provisioning standard. Visit Manage members with SCIM provisioning to learn how to automatically manage members.


