## Overview

    1. Select BambooHR
       Select an application to establish SAML 2.0-based SSO with.
       __Don't forget, if you have on-prem/legacy applications which use LDAP, you may use JC LDAP services for those bindings__

    2. Configure the App
       Set the various SAML configurations, with JumpCloud acting as BambooHR's 'IDP' or identity provider. 
       Each application connector has explicit instructions required to establish the connection.

    3. Bind BambooHR to a User Group
        BambooHR will be bound to one or more of the User Groups. 
        Members of the group gain access to BambooHR via SAML. 
        They will see the BambooHR icon in their User Portal. 
        __Many apps allow login from their services where they will be redirected to JumpCloud for SAML authentication__ 

## Setting up SAML-based SSO with an Application
  
  JumpCloud uses SAML 2.0 protocol as its method to assert identities with application service providers. 
  __JumpCloud is considered the Identity Provider(IDP) and BambooHR is known as the Service Provider(SP)__
  
  JumpCloud Admin Console -> Applications -> (+) -> Configure
  
## Configuring Authentication from the Application Service Provider
    
  SP will provide SAML configuration parameters to set up SSO
  
   Sigin-in page URL    ->https://sso.jumpcloud.com/saml2/google
   //URL for signing in to your system and Google Apps
   
   Sign-out page URL    ->https://console.jumpcloud.com
   //URL for redirecting users to when they sign out
   
   Change password URL  ->https://console.jumpcloud.com
   //URL to let users change their password in your system; when defined here, this is shown even when Single Sign-on is not enabled
   
   Vertification certificate  
   //The certificate file must contain the public key for BambooHR to verify sign-in requests.
   
 # Restricting Employee Access to Applications
 Managing users access on a per-application basis is explained in the __SAML Configuration Notes__
 
 For organizations using Groups, *all users are implicitly denied access* to the BambooHR
 
 *To grant access to BambooHR using Group binding:
 
    1. Create a Group of Users that should have access to the BambooHR Application
    2. Edit the Group Configuration
    3. On the Applications tab,select BambooHR. 
    __Applications will not appear until the connector has been activated.
  # End User Experience
 
  Once the IDP and SP configurations are complete, employees can gain access to the applications they have been assigned to in two ways:
* *IDP-Initiated -* Access via the JumpCloud User Portal
* *SP-Initiated -* Access directly from the application

## Idp Initiated
   
   With IDP Initiated access the employee will log their JumpCloud User Portal and select the application icon.

   1. Login to the JumpCloud User Console https://console.jumpcloud.com/
   2. Under "My applications" and select the apptopriate application. JumpCloud will assert the user's identity to the SP and be authenticated without further action.

## SP Initiated 

   SP initiated means the user enters through the SP application instead of the JumpCloud user console. Not all SP's support thi workflow
   
   1.Navigate to the SP
   2.Generally, there is either a special link or an adaptive username field that detects the user is authenticated via SSO, this varies by SP
   
  3. Loguin will redirect to JumpCloud. The user will enter their JumpCloud credentials.
  4. Once logged in successfully, the user will be redirected back to the SP and automatically logged in.
  
 
   
