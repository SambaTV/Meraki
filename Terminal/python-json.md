https://github.com/TheJumpCloud/jcapi-python

    pip install git+https://github.com/TheJumpCloud/jcapi-python.git#subdirectory=jcapiv2

    $ python setup.py install --user

# API v2 example:

    import jcapiv2
    from jcapiv2.rest import ApiException

    ...
    content_type = 'application/json'
    accept = 'application/json'

    # set up the configuration object with your API key:
    jcapiv2.configuration.api_key['x-api-key'] = '<YOUR_API_KEY>'

    # instantiate the API object for the group of endpoints you need to use
    # for instance for User Groups API:
    userGroupsAPI = jcapiv2.UserGroupsApi()

    try:
        # make an API call to retrieve all user groups:
        userGroups = userGroupsAPI.groups_user_list(content_type, accept)
        print(userGroups)
    except ApiException as e:
        print("Exception when calling UserGroupsApi->groups_user_list: %s\n" % e)
        
# System Context Authorization example:

           import jcapiv2
    from jcapiv2.rest import ApiException

    content_type = 'application/json'
    accept = 'application/json'
    system_id = '<YOUR_SYSTEM_ID>'

    # set headers for the System Context Authorization:
    # for detailed instructions on how to generate these headers,
    # refer to: https://docs.jumpcloud.com/2.0/authentication-and-authorization/system-context
    sys_context_auth = 'Signature keyId="system/<YOUR_SYSTEM_ID>",headers="request-line date",algorithm="rsa-sha256",signature="<YOUR_SYSTEM_SIGNATURE>"'
    sys_context_date = 'Thu, 19 Oct 2017 17:27:57 GMT' # the current date on the system

    # instantiate the API object for the group of endpoints you need to use
    # for instance for User Groups API:
    systemsAPI = jcapiv2.SystemsApi()

    try:
        # list the system groups this system is a member of:
        # Note that we pass the System Context Authorization headers as the 'date' and 'authorization' parameters
        groups = systemsAPI.graph_system_member_of(system_id, content_type, accept, date=sys_context_date, authorization=sys_context_auth)
        print groups
    except ApiException as e:
        print("Exception when calling systemsAPI->graph_system_member_of: %s\n" % e)
