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
    
    
    
    


    
   
