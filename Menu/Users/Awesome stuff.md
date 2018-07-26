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
 
 ## Remove LDAP | Create and add them to 'TV Characters' group
  
  ## group them together Give them LDAP in same script 
       
        New-JCUserGroup 'TV Characters'
       
       Set - JCUser -Username rickandmorty -ldap_binding_user $True
  ## Delete
   Forced user
    
        Remove-JCUser rickanmorty -force
        Remove-JCUser themagicians 
        Remove-JCUser thelastmanonearth
        
   User group
         
         Remove-JCUserGroup 'TV Characters'
        
  
