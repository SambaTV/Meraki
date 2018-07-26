# Importing Users from a CSV file
  
  Build CSV
          
    New-JCImportTemplate
    
  Build User Group
  
    New-JCUserGroup
    
  Import CSV file 
  
    Import-JCUsersFromCSV
    
# Query existing AD users
  Selects unique departments
    
    Get-ADuser -Filter {Department -ne "$null"} -Properties * | Select Department -Unique
    
   For each !!!!!!
   ### User property -> User Group
   
    Get-ADuser -Filter {Department -ne "$null"} -Properties * | Select Department -Unique | Foreach {New-JCUserGroup -GroupName $_.Department}
    
   ### To bind System to user during import
   1. JC agent must be installed on machine
   2. JC CSV import template
            
            New-JCImportTemplate
      //Create file in Home directory
   3. change CSV output location? Y
   Bind new users to existing JC systems during import? Y
   Add new users to JC user groups during import? Y
   Max # of groups added to a single user during import ? (Department, All Employee, Systems)3
   Custom attributes to your users during import? (creation date in AD, Location
   Max # of Custom attributes added to a single user during import ? (2)
   open file? Y
   
   
   
   #### Pulling from Directory to Excell
   
    Get-ADUser -Filter * -Properties *
    -SearchBase "OU=DenverOffice,OU=Employees,DC=Azzipa01,DC=local" | `
    Select-Object @{name = 'FirstName'; expression = {$_.givenname}}, `
    @{name = 'LastName'; expression = {$_.surname}}, `
    @{name = 'UserName'; expression = {$_.samaccountname}}, `
    @{name = 'Email'; expression = { $_.mail }}, `
    @{name = 'Department'; expression = {$_.department}}, `
    @{name = 'StartDate'; expression = {$_.created}} |
    Export-Csv 'DenverUserExport.CSV'
    
 **Note** 
    If you dont create your users with a password at import then then they will receive an activation email to set their JC password/ If user is create with password then no email is sent
    
   4. bind to users 
    //use find feature in Excell to associate users and systems
    
   5. Import CSV
          
          Import-JCUsersFromCSV .\JCUserImport_12-27-2017.csv | Out-file Results.txt
         //file Location, logging to show output of user creation
   6. It should provide validation , press Y
   
   **Note** 
 it takes 3 times as long 3 times the amount of API calls during user creation. For each user they are added to Number of groups and some to systems (15 minutes for 516 users)  
   
    
    
    
    


    
   
