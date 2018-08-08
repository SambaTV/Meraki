# JumpCloud-API scripting Timeline

# Evaluating the JumpCloud platform (Completed)
1. Adding Users & Systems
2. Groups
(^ These items are necessary to interact with and leverage other more advanced features of JC)

# JumpCloud API for Python (Didn't work) 

1. Download Python for JumpCloud API
2. To be able to run scripts from Python
  the plan is to create automated scripts for the user ( pull/get info like Name, email, password)

# JumpCloud Powershell Module (Completed)
1. Download Powershell for Mac os
2. Download JC Powershell Module through Terminal
3. Run Powershell Commands/scripts 
4. Customize scripts

# JC Active Directory Bridge (Paused)
1. Create 'Read All' User
2. Install AD Bridge Agent on domain controllers
3. Create Two Security Groups

# Configure GAM for JumpCloud (Paused)
1. Download GAM
2. Configure GAM
3. Run GAM
4. GAM API communicate with JC

# SSO SAML2 (Paused)
1. SHA256
2. BambooHR
3. Slack

# BambooHR Onboarding/Offboarding (Current)
php -> python -> python API ffor BambooHR
1. Get all info of one user with one script by calling their user ID/ username
2. Send data from Webpage to our server to be processed
3. New user(onboarding) ->  email notification to IT admin
  * last change information
  * Web hooks
  * Using gmail with command line Linux mail
4. Delete user(offboarding) -> email notification to IT admin
  * last change information
  * Web hooks
  mail x
  native mailer on system
  runtime ssh to connect to Bards server
  
# Connect Bamboo HR userID number with Jumpcloud username (Future)

**New Hire**  
*opt 1. (Last changed + Since +)*
Hired -> Create an account on BambooHR -> GET:LastChanged (inserted)-> JumpCloud/JumpCloud API -> Create account in Gmail

*opt 2. (web hooks)*
Hired -> Create an account on BambooHR -> Triggers (inserted) BambooHR Webhook (posted in HTML form) -> JumpCloud/JumpCloud API -> Create account in Gmail

