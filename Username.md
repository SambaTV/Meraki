# Username field 

  The username field is Hard-coded(once configured, can not be changed) when a new user is saved. 
    -> the username is pushed to a machine when a user is bound to a system 

  NOTE 
  If username field of existing account on a previous workstation matches the username field on JC
    -> the agent will take over the account and it will be manageable from JC admin console

  Mismatch = BAD
    ex) steve.jobs vs sjobs
    
    
    -------------------------- Example 1 --------------------------
    
    PS C:\> Get-JCUser
    
    Returns all JumpCloud Users and the information describing these users.
    -------------------------- Example 2 --------------------------
    
    Get-JCUser -Username cclemons
    
    Returns the information describing the JumpCloud User with Username cclemons
    -------------------------- Example 3 --------------------------
    
    Get-JCUser -Username *clemons
    
    Returns all JumpCloud users that usernames end with clemons using the wildcard character '*'
    -------------------------- Example 4 --------------------------
    
    Get-JCUser -filterDateProperty created -dateFilter after -date 01/01/2018
    
    Returns all JumpCloud users that were created after '01/01/2018'. The parameter '-filterDateProperty' takes both 'created' and 'password_expiration_date' as input and creates two dynamic parameters '-dateFilter' which takes "before" or "after" as input and "-date" which takes a date value as input.
    -------------------------- Example 5 --------------------------
    
    Get-JCUser -returnProperties username, sudo
    
    Returns all JumpCloud users and only the username and sudo Properties of their JumpCloud user object.
    
RELATED LINKS
    Online Help Get-JCUser https://github.com/TheJumpCloud/support/wiki/Get-JCUser



#User email

  Can be updated after account is created

  Office 365 or G Suite?
    -> Directory sync feature
      (Allows JC to view password authority for only accounts admin specifies)
      
      How to leverage Directory Sync Feature?
        1. Authorize the directory sync
          (this is done in the Directories Tab)
        2. Once authorized, import users in bulk directly through this integration
          * additional info ( support.jumpCloud.com ) 
          
          
