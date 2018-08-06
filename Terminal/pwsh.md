# Powershell
  ## Run JC Pwsh Module
    1. Go to terminal
    2. run Powershell
      -> pwsh
    3. Make sure PS Version is 5+
      -> $PSVersionTable
    4. Install JC Powershell Module
      -> Install-Module JumpCloud -Scope CurrentUser
    5. Confirm 
      -> Y
  
  ## JC Pwsh Module Commands
    1. List Commands
      -> Get-Command -Module JumpCloud
    2. Run a command
      -> Connect-JCUser
          * Type !? for Help
      -> It will ask for JumpCloudAPIKey
        -> To obtain JumpCloudAPIKey
          1. go to JumpCloud Admin Login 
          2. click email adress in top right corner
          3. Select API settings from the drop down menu
          	-> your API key will appear 
          4. Copy API key
    3. Paste JumpCloudAPIKey into Terminal
            
    
