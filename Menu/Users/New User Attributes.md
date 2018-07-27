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
   
     Set-JCUser -username bobby
   
   // _NumberOfCustomAttributes_ is set to **2** so a total of four additional parameters must be populated.If this number was set to **1** there would only be two parameters to populate and if it was se **3** there would be a total of six.
   
    
   Employee#

  displayName

 firstName

lastName

jobTitle

EmploymentStatus

HireDate

Location
