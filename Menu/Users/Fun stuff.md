# Get-JCUser | Get-Member
Displays all properties of a JumpCloud user object

# Get-JCUser -returnProperties username, email 
Uses the pipeline and the parameter '-returnProperties' to return the username and email for all JumpCloud users in an organization

# Get-JCUser -activated $false -returnProperties username, created 
Using the boolean parameter '-activated' with the search filter $false this search returns all inactive users and their usernames and the date they were created.

//Search filter for all disabled ldap users
# Get-JCUser -ldap_binding_user $False -returnProperties username, created 

