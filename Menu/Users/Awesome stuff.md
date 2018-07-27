# New users play around

  ## Create 3 new users | with firstname,lastname,username,email | 2 w/ ldap & 1 w/o | 
  **Note** & in the username doesnt work! 
  **Note** Usernames must be lowercase
  
       New-JCUser -firstname Rick -lastname Sanchez -username rickandmorty -email Rick.Sanchez@samba.tv
       
       New-JCUser -firstname Quentin -lastname Coldwater -username themagicians -email Quentin.Coldwater@samba.tv -ldap_binding_user $True 
       
       New-JCUser -firstname Phil -lastname Miller -username thelastmanonearth -email Phil.Miller@samba.tv -ldap_binding_user $True 
      
  ## Put in a group SambaTV ( for each?)
     Add-JCUserGroupMember -GroupName SambaTV -username rickandmorty
     Add-JCUserGroupMember -GroupName SambaTV -username themagicians 
     Add-JCUserGroupMember -GroupName SambaTV -username thelastmanonearth
  
   * Get-JCUser -filterDateProperty created -dateFilter after -date (Get-Date).AddDays(1) -returnProperties username, created | Select Username -Unique | Foreach {JCUser -GroupName SambaTV} * FAILED
    
   //get users that were added today, return users, select unique users, for each user add to group 'AllUsers'
   *I contacted JumpCloud directly for this issue 
   Jason Katz replied:
Hi Rodney,

Test this command out by omitting the last part in bold there to verify you’re grabbing the correct users, 
    
    Get-JCUser -filterDateProperty created -dateFilter after -date (Get-Date).AddDays(-1) -returnProperties username, created | Select Username -Unique
 then go ahead and append the command with the last part again to add them to your group.
    
    Get-JCUser -filterDateProperty created -dateFilter after -date (Get-Date).AddDays(-1) -returnProperties username, created | Select Username -Unique | Add-JCUserGroupMember -GroupName AllUsers
    

It should work, but you may need to play around/test the parameters a bit to get it just right.
   
   
    
   **Note** useful for duplicate results, it only does one
      
      Select Department -Unique 
 
  
  
  ## create group | Give them LDAP  
       
        New-JCUserGroup 'TV Characters'
       
       Set - JCUser -Username rickandmorty -ldap_binding_user $True
  ## Delete
   Forced user
    
        Remove-JCUser rickandmorty -force
        Remove-JCUser themagicians 
        Remove-JCUser thelastmanonearth
        
   User group
         
         Remove-JCUserGroup 'TV Characters'
         
  
