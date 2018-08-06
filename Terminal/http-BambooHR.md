# Authentication

At the HTTP level, the API key is sent over HTTP Basic Authentication. Use the secret key as the username and any random string for the password.

To use curl to make an API request, try:

    curl -i -u "{API Key}:x" "https://api.bamboohr.com/api/gateway.php/{subdomain}/v1/employees/directory"
					
Most browsers and tools can accept an url like

    https://{API Key}:x@api.bamboohr.com/api/gateway.php/{subdomain}/v1/employees/directory
