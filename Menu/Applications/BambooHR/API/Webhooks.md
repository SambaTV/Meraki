Webhooks allow you to monitor changes made in BambooHR. BambooHR will watch for changes in fields you specify and post information to a location of your choice.

# Configuration
admin user in the tools section by clicking on the link "Webhooks".
      https://www.bamboohr.com/contact.php
      
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

# specify which fields they want to monitor

The user can also configure which fields will be posted by the webhook. Any field in the database can be posted. Fields can be posted with an alternate name, but use BambooHR's field names (in English) by default.

Users can specify a schedule of when they want webhooks to fire (only at 12:00pm or every hour at 5 after the hour). They can also limit how often a webhook will fire by setting a maximum number of requests per interval in seconds.

# Security
