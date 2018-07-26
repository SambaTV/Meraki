//centralized identity
(Single Sign On Workflow)
# General
  ## How SSO Application works 
   1 - Select an App - Select an application you would like to establish SAML 2.0-based SSO with. Don't forget, if you have on-prem/legacy applications which use LDAP, you may use our LDAP services for those bindings.

   2 - Configure Your App - You can set the various SAML configurations, with JumpCloud acting as the app's "IDP" or identity provider. Each application connector has explicit instructions required to establish the connection.
 
   3 - Bind Your App to a User Group - Your app will then be bound to one or more of your User Groups. Members of the group gain access to your app via SAML. They will see the application icon in their User Portal. Many apps allow login from their services where they will be
redirected to JumpCloud for SAML authentication.
 
 
  ## Setting up SAML-based SSO with an Application

Within JumpCloud's Administrative Console, the 'Applications' object provides access to create new (+) or manage existing applications:
