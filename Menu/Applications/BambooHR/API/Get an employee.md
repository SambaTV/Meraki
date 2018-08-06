GET
Get an employee
HTTP Method:GETPath:/api/gateway.php/{company}/v1/employees/{number}?fields={fieldList}Parameters:The {fieldList} is a comma separated list of values taken from the official list of field names. {number} is an employee ID. The special employee ID of zero (0) means to use the employee ID associated with the API key (if any).Response Format:The response for this resource is available in XML or JSON format. XML is the default. To request JSON data, set the HTTP header "Accept" to "application/json".Compatibility Note:For backwards compatibility reasons the state field has an inconsistent behavior for just this API call. It will not return the full name of a state. Rather, it returns the two character US state abbreviation. For international addresses, the state will either be the plain text name if the user hand entered it, or the 2-3 character state/province abbreviation if they selected it from a drop down.Success Response:200 - The response content will be an XML document with the requested information. Any fields that the API user does not have permission to see will be empty in the response.Failure Responses:
403 - if the API user does not have permission to see the requested employee.

404 - if the employee does not exist.

Sample URL:https://api.bamboohr.com/api/gateway.php/testcorp/v1/employees/123?fields=firstName,lastName
