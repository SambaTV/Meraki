## Fun Stuff

Displays all properties of a JumpCloud user object
   
    Get-JCUser | Get-Member

Uses the pipeline and the parameter '-returnProperties' to return the username and email for all JumpCloud users in an organization
    
    Get-JCUser -returnProperties username, email 

Using the boolean parameter '-activated' with the search filter $false this search returns all inactive users and their usernames and the date they were created.
    
    Get-JCUser -activated $false -returnProperties username, created

Search filter for all disabled ldap users
    
    Get-JCUser -ldap_binding_user $False -returnProperties username, created

Adds all JumpCloud users that have the custom attribute 'Department' set with a value of 'Sales' to the group 'Sales'
    
    Get-JCUser | ? attributes  -Like '*name=Department; value=Sales;*' | Add-JCUserGroupMember -GroupName Sales
    
   
Selects unique departments
    
    Get-ADuser -Filter {Department -ne "$null"} -Properties * | Select Department -Unique
    
   For each !!!!!!
   **User property -> User Group**
   
    Get-ADuser -Filter {Department -ne "$null"} -Properties * | Select Department -Unique | Foreach {New-JCUserGroup -GroupName $_.Department}
    
  ## Exporting User Information To CSV

 Backs up JumpCloud user information to CSV. A CSV backup file containing all user information will be created within the current working directory when this command is run.
     
     Get-JCBackup -Users


 Uses the parameter '-filterDateProperty' which creates the two dynamic parameters '-dateFilter' and '-date' to return users that were created in the last 7 days and exports their 'username', 'created date', and 'email' to the CSV 'NewUsers.csv'.
     
     Get-JCUser -filterDateProperty created -dateFilter after -date (Get-Date).AddDays(-7) -returnProperties username, created, email | Export-Csv NewUsers.csv
     


