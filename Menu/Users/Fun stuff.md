# Displays all properties of a JumpCloud user object
    Get-JCUser | Get-Member

# Uses the pipeline and the parameter '-returnProperties' to return the username and email for all JumpCloud users in an organization
    Get-JCUser -returnProperties username, email 

# Using the boolean parameter '-activated' with the search filter $false this search returns all inactive users and their usernames and the date they were created.
    Get-JCUser -activated $false -returnProperties username, created

# Search filter for all disabled ldap users
    Get-JCUser -ldap_binding_user $False -returnProperties username, created

# Adds all JumpCloud users that have the custom attribute 'Department' set with a value of 'Sales' to the group 'Sales'
    Get-JCUser | ? attributes  -Like '*name=Department; value=Sales;*' | Add-JCUserGroupMember -GroupName Sales

