
### Prerequisities:
  * Generate a public certificate and private key pair.
     JumpCloud's SSO SAML connectors allow for either __SHA256__ certificates
     To create a private key -> public certificate for that private key
        
         openssl genrsa -out private.pem 2048
         openssl req -new -x509 -sha256 -key private.pem -out cert.pem -days 1095
         
     To determine the SHA256 Fingerprint for the public certificate 
         
         openssl x509 -sha256 -in cert.pem -noout -fingerprint
     
  * In order to successfully complete the integration between JumpCloud and Slack, you must use a Slack Plus/ Enterprise(administrator) account in BambooHR.
  * JumpCloud managed users must have an email address that corresponds to an email address associated with a Slack Plus account.
### Notes:
  * How to configure User authorization.
# Configure the JumpCloud SSO Application
  1. Access the JumpCloud Administrator Console at https://console.jumpcloud.com.
  2. Select Applications in the main navigation panel.
  3. Select the + in the upper left, scroll or search for the application in the 'Configure New Application' side panel, the select
  'configure'.
  4. In the **IDP Entity ID** field, enter https://YOURDOMAIN.TLD (e.g., https://thebestwidgets.com).
    
    -> https://samba.tv
  5. Select **Upload IdP Private Key** and upload the private.pem file generated according to the above prerequisites.
   
    see Rodney
  6. Select **Upload IdP Certificate** and upload the cert.pem file generated according to the above prerequisites.
  
    see Rodney
  7. In the **ACS URL** field, enter https://YOURDOMAIN.bamboohr.com/saml/consume.php (replace YOURDOMAIN with your account's registered BambooHR domain name).
  
    -> https://sambatv.bamboohr.com/saml/consume.php
  8. In the field terminating the **IdP URL**, either leave the default value or enter a plaintext string unique to this connector.
  
    -> https://sso.jumpcloud.com/saml2/bamboohr
  9. (Optional) In the **Display Label** field, enter a label that will appear beside the BambooHR logo within the JumpCloud console to guide administrators and users to the connection you have configured.
  
    Insert prompt here
  10. Select **Activate**.
  
# Configure the Service Provider
  1. Log in to BambooHR as an administrator (This user's email should also be managed by JumpCloud).
  2. Select the **Apps** icon in the upper right.
  3. Scroll down to the Single Sign-On section, and select the **SAML 2.0** icon.
  4. Select the **Install** button next to the SAML 2.0 icon.
  5. In the **SSO Login URL** field, enter the same IdP URL that you set in the JumpCloud console (if you did not modify the termination of this URL, then enter the default URL: https://sso.jumpcloud.com/saml2/bamboohr).
  6. In the **x.509 Certificate** field, paste the contents of your public certificate.
  7. Select **Install**.

# Validate SSO authentication workflows
### IdP Initiated

  * Access the JumpCloud User Console at https://console.jumpcloud.com.
  * Select the Service Provider icon.
  * This should automatically launch and login to the application.
### SP Initiated

  * Navigate to your Service Provider application URL.
  * You will be redirected to log in to the JumpCloud User Portal.
  * The browser will be redirected back to the application and be automatically logged in.
