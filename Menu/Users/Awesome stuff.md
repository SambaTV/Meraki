# New users play around

  ## Create 3 new users | with firstname,lastname,username,email | no ldap | Create and add them to 'TV Characters' group
    
       New-JCUser -firstname Rick -lastname Sanchez -username Rick&Morty -email Rick.Sanchez@samba.tv
       New-JCUser -firstname Quentin -lastname Coldwater -username TheMagicians -email Quentin.Coldwater@samba.tv
       New-JCUser -firstname Phil -lastname Miller -username TheLastManOnEarth -email Phil.Miller@samba.tv
       New-JCUserGroup 'TV Characters'
  ## group them together Give them LDAP in same script 
       Add-JCUserGroupMember -GroupName SFO -username Rick&Morty
       
       Set - JCUser -Username Rick&Morty -ldap_binding_user $True
  ## Delete
   Forced user
    
        Remove-JCUser superman -force
        
   User group
         
         Remove-JCUserGroup 'TV Characters'
        
  
