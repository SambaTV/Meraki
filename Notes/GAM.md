# GAM 

  ## Download GAM
    1. Shell prompt(Mac OS terminal app)
    bash <(curl -s -S -L https://git.io/install-gam)
      -> the script will download the latest release of GAM and install it to $HOME/bin/gam directory
        -> after download and installation, it will prompt you to setup a project and authorize GAM for admin management and user data/config access.

  ## Configure GAM
    * An API project which identifies your install of GAM to Google and keeps track of API quotas.
    * Authorization to act as your G Suite Administrator.
    * A special service account that is authorized to act on behalf of your users in order to modify user-specific settings       and data such as Drive files, Calendars and Gmail messages and settings like signatures.
  
  ## Creating a Project
    If GAM isn't already prompting you to create a project, you can run:
      -> gam create project
      
        -> GAM will prompt you for your G Suite admin email address. 
      1. Enter the address of a super admin in your Google Apps instance.
      
        -> Depending on your choices, either a website will open automatically or you'll be given a URL to go to to authorize GAM to create projects as the admin you specified. 
      2. Click allow, copy the code if given one and switch back to the GAM window.
        -> GAM will now create the project, 
      3. turn on necessary Google APIs for the project such as Drive, Gmail, Admin SDK, etc and finally create a service account.
        -> Next, you'll be asked to go to a URL and perform a few actions to create a "OAuth client ID". 
      4. Follow the steps as provided and copy the client ID and secret back into GAM when prompted.
        -> Now you are asked to return to the browser window and make a change to your new service account. 
      5. Once you've enabled G Suite Domain-wide Delegation, return to the GAM console window.

  ## Authorize Admin Access
        ->If you're not already prompted to authorize an admin as part of the install and configure process above, you can manually start the authorization by running 
      gam oauth create 
        -> You'll be prompted for the email address of a super admin in your G Suite domain.
        -> You'll be presented a long list of APIs that GAM can use. By default, the most important APIs are selected. 
      1. Unless you know what you are doing you can leave this selection as is and press C to continue to authorization.
        -> GAM will either open a web page for you or prompt you with a URL to visit in order to authorize admin access. 
      2. Visit the URL and Authorize. 
        -> You may need to copy a code from the browser back to the GAM window.
        -> That's it, GAM is now authorized to perform admin actions.
  ## Authorize User Data and Settings Access
        -> you can manually start the authorization process by running 
        gam user a_user@example.com check serviceaccount
        -> GAM will prompt you for the email address of a regular, non-admin user in your G Suite domain. 
      1. Make sure this user has the Gmail, Drive and Calendar services enabled. If the service is not enabled, GAM will fail to connect to that service for the user.
        -> Now GAM will attempt to authenticate with each service / scope via the service account and acting on behalf of the user you specified above. It's expected that the first time through these attempts will FAIL. GAM will provide you with a URL to visit, a "Client name" and a list of scopes. 
      2. Visit the URL and copy the "Client name" and scopes. 
        -> Pay special attention when copying the scopes that you don't accidentally cut off the full list of URLs.
        -> Once you've authorized the Client name for the scopes in the admin console, 
      3. re-run the check by saying Y or running 
      gam user a_user@example.com check serviceaccount  
        -> It may take a few minutes after authorizing the scopes for all tests to PASS. If you've confirmed the Client name and scopes are listed properly on the website, grab a coffee and then try again.
        -> That's it! GAM is now setup and ready to run.
        **Note** : If you're getting a 401 error "client not found" from Google OAuth Authorisation, please check that the client_secrets.json file inside your gam directory matches your GSuite API client id and customer secrets (recursive creation of projects creates new files on the filesystem instead of overwriting the default one)

  ## Running GAM for the First Time

      1. Open a command prompt, shell or terminal on your computer. 
      2. Run 
        gam info user
        -> You'll be asked to specify which "scopes" you'd like the OAuth token to support. 
      3. For now, select the last option to continue, 
        -> all scopes will be selected. 
        -> Next GAM will open up a web page in order for you to grant access to retrieve data and make changes to your Google Apps account. 
      4. Make sure you are logged in to a Google G Suite Administrator account before granting access. 
        -> Once you've granted access...
      5. Switch back to the command prompt window, GAM should already be working to display information about your user account.
        -> Congrats, you're up and running with GAM.

## More simple GAM commands
    Try the following GAM commands to get a feel for how the program works. I suggest creating a test user account for experimenting, or if you don't have a test account, use your account, we'll call our test user crashtestdummy in the examples below.

    If you haven't already, we can just create our crashtestdummy account with GAM:
      gam create user crashtestdummy firstname Crash lastname "Test Dummy" password "BuckleUp"
   
    We can give crashtestdummy an alias so that emails to idontwearseatbelts go to him:
      gam create alias idontwearseatbelts user crashtestdummy

    We can create a group for crash test dummy's friends:
      gam create group test-dummies-united name "Test Dummies United" description "Support Group Against Plastic Abuse"

    Crash test dummy likes Gmail but sometimes he prefers to use IMAP with his favorite email client, Thunderbird, let's enable IMAP for him:
      gam user crashtestdummy imap on
    these are just a few examples, more are available under the topics to the right. Have fun!


