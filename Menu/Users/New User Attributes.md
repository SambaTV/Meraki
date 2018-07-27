# Ex) User Attributes
email                          : phil.miller@samba.tv
username                       : thelastmanonearth
allow_public_key               : True
ssh_keys                       : {}
sudo                           : False
enable_managed_uid             : False
unix_uid                       : 5668
unix_guid                      : 5668
activated                      : False
password_expired               : False
account_locked                 : False
passwordless_sudo              : False
externally_managed             : False
firstname                      : Phil
lastname                       : Miller
ldap_binding_user              : True
enable_user_portal_multifactor : False
totp_enabled                   : False
attributes                     : {}
created                        : 7/27/18 5:38:43 AM
samba_service_user             : False
addresses                      : {}
phoneNumbers                   : {}
password_never_expires         : False
_id                            : 5b5aafe3c73401685bf3fcb9



# User Attributes
  JumpCloud's Custom Attributes enable you to create and store additional data to your users. 
  *Note* Custom Attributes are not yet supported for LDAP, RADIUS or SAML- although will be introduced in further       implementation phases.

## User Attribute configuration allows for:
   ** 1.) Name** - String defining attributes display name. Must be less than 32 characters, no special characters.
   ** 2.) Value** - Sting to insert the attributes value. No character restrictions. 
    
### Adding and Modifying Custom Attributes
   1. Specify the number of attributes you wish to interact with by setting the parameter _-NumberOfCustomAttributes_
      // If this parameter is not set then then the _-Attribute#name_ and _-Attribute#value_ parameters will not display (these are dynamic parameters that require a value to be set for the _-NumberOfCustomAttributes_ parameter.)
      
   2. For each custom attribute specified there are two parameters that populate the  _-Attribute#name_ and the _-Attribute#value_. 
   
     Set-JCUser -username bobby.boy -NumberOfCustomAttributes 2 -Attribute1_name Department -Attribute1_value Dev -Attribute2_name Location -Attribute2_value Boulder
   
   // _NumberOfCustomAttributes_ is set to **2** so a total of four additional parameters must be populated.If this number was set to **1** there would only be two parameters to populate and if it was se **3** there would be a total of six.
   
  ### displayName
  DisplayName(BambooHR) = Username(JumpCloud)

### firstName
  firstName = firstname

### lastName
 lastName = lastname
    
### Employee#
 Set-JCUser -username rickandmorty -NumberOfCustomAttributes 1 -Attribute1_name EmployeeNumber -Attribute1_value 
 
     Set-JCUser -username rickandmorty -NumberOfCustomAttributes 5 -Attribute1_name EmployeeNumber -Attribute1_value 0 -Attribute2_name jobTitle -Attribute2_value I.T. -Attribute3_name EmploymentStatus -Attribute3_value active -Attribute4_name HireDate -Attribute4_value 7/28/18 -Attribute5_name Location -Attribute5_value San Francisco 
    
    //How can i create Custom Attributes in powershell
    Get-JCUserGroupMember -GroupName 'TV Characters' | Set-JCUser -NumberOfCustomAttributes 1 -Attribute1_name 'EmployeeNumber' -Attribute1_value '0'
    
    //This example either updates or adds the Custom Attribute 'name = EmployeeNumber, value=0' to all JumpCloud Users in the JumpCloud User Group 'TV Characters'
    
     
### jobTitle
  *__jobTitle__* 

### EmploymentStatus
  *__EmploymentStatus__*

### HireDate
  *__HireDate__*

### Location
  *__Location__*
  
### Departure Day, script

## Create UserGroup add multiple Users
    Get-JCUser -filterDateProperty created -dateFilter after -date (Get-Date).AddDays(-1) -returnProperties username, created | Select Username -Unique | Add-JCUserGroupMember -GroupName TV Characters
    
    New-JCUserGroup 'TV Characters'
    
    Get-JCUser -filterDateProperty created -dateFilter after -date (Get-Date).AddDays(-1) -returnProperties username, created | Select Username -Unique | Add-JCUserGroupMember -GroupName SambaTV   
   // Get Users that have been added on 07/26/2018, adds them to TV Characters 
