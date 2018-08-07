Webhooks allow you to monitor changes made in BambooHR. BambooHR will watch for changes in fields you specify and post information to a location of your choice.

# Configuration
admin user in the tools section by clicking on the link "Webhooks".
      https://www.bamboohr.com/contact.php
     

 # specify which fields they want to monitor

The user can also configure which fields will be posted by the webhook. Any field in the database can be posted. Fields can be posted with an alternate name, but use BambooHR's field names (in English) by default.

        Department
        Division
        EEO Job Category
        Employee #
        Status
        Employment Status
        First Name
        Hire Date
        Home Email
        Job Title
        Last Name
        Location
        Middle Name
        Preferred Name
        Termination Date
        Work Email
        Work Phone
        Work Ext.
        City
        Rehire Date
        
# Useful 
   Useful for Updated 
         Status Active
        Employment Status
   
   Useful for Inserted  
   
   Useful for Deleted 

# CronJob... Kinda
Users can specify a schedule of when they want webhooks to fire (only at 12:00pm or every hour at 5 after the hour). They can also limit how often a webhook will fire by setting a maximum number of requests per interval in seconds.

# Security 
BambooHR will post to an HTTP or HTTPS url, but HTTPS is recommended. Best practices suggest that you specify a secret key when configuring a webhook and that your webhook check for that key, so that only systems that have the secret key can post to your webhook

        http://example.com/webHook.php?key=123abc
        
# Data format
Employee data will be batched when possible, so that if multiple employees' data has been changed, they will be sent together.
Data will be posted in the standard format of an HTML form submission. The structure will be:

      employees[<employeeId>][changedFields][0]=Employee #
      employees[<employeeId>][changedFields][1]=First Name
      employees[<employeeId>][Employee #]=9
      employees[<employeeId>][First name]=Robert
      employees[<employeeId>][Last name]=Smith
      employees[<employeeId>][Job title]=Engineer
      
 where "changedFields" is an array of fields that were changed. If the field is included in the employee data, it will give the name of the posted field. Otherwise, a field ID will be given, and more information about the field can be looked up using the API.
 
 More than one employeeId may be present as a key in the employees structure. While this structure will not be changed, more or less fields with different names may be sent to you, as configured by the user.	In addition, in the future, we may add more context to the structure, so it is good practice to ignore fields that your webhook does not recognize.
 
 
 https://support.litmos.com/hc/en-us/articles/227738887-BambooHR-Integration
