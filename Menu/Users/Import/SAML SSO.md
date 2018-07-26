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

  JumpCloud utilizes the SAML 2.0 protocol as its method to assert identities with application service providers. JumpCloud is considered the "Identity Provider" or "IdP", where the application is denoted as the "Service Provider" or "SP". As a JumpCloud Administrator, clicking on the 'configure' button next to any of the supported SP icons will provide the SAML IdP configuration parameters, Google Apps in this case below:

  ## Configuring Authentication from the Application Service Provider
The SP will typically provide simple-to-input SAML configuration parameters to set up Single Sign On from a compatible IdP like JumpCloud. E.g., Google's Admin Console:

  ## Restricting Employee Access to Applications
Managing user access on a per-application basis is explained in the SAML Configuration Notes.
 
  ## End User Experience
Once the IdP and SP configurations are complete, employees can gain access to the applications they have been assigned to in two ways:
  * IdP-Initiated - Access via the JumpCloud User Portal
  * SP-Initiated - Access directly from the application
  
  ## IdP Initiated
With IdP initiated access the employee will log in to their JumpCloud User Portal and select the application icon.
  1. Login to the JumpCloud User Console https://console.jumpcloud.com/ 
  2. Under "My applications" and select the appropriate application. JumpCloud will assert the user's identity to the SP and be authenticated without further action.
  
  ## SP Initiated
SP initiated means the user enters through the SP application instead of the JumpCloud user console. Not all SP's support this workflow
 
  1. Navigate to the SP
  2. Generally, there is either a special link or an adaptive username field that detects the user is authenticated via SSO, this varies by SP.
  3. Login will redirect to JumpCloud. The user will enter their JumpCloud credentials.
  4. Once logged in successfully, the user will be redirected back to the SP and automatically logged in.
