# Add New User 
 Superman Example
   
   Create New User
         
         New-JCUser -firstname Clark -lastname Kent -username superman -email clark.kent@samba.tv
          
   Put in SFO Group
          
          Add-JCUserGroupMember -GroupName SFO -username superman
   // Adds the user 'superman' to the user group 'SFO'
    
   Enable as LDAP Bind DN
          
          Set-JCUser -Username superman -ldap_binding_user $True
   **Help
          
          Help New-JCUser -Online
    
 # Delete User
   Remove User
          
          Remove-JCUser superman
   //Remove commands remove objectsor associations between objects.
        
           Y
          
   //To skip the default warning when running a Remove command use the '-force- parameter
         
         Remove-JCUser superman -force
         
 # Get BambooHR Departure Date
