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
  
  JumpCloud Admin Console -> Applications -> (+) 
 
  
 
   
