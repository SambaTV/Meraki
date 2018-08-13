# Slash Commands 

## Info
Slash Commands are initiated from the message box in Slack.
Once part of an app, they can easily be installed for your workspace as an internal integration or shared with the world, distributed to other work spaces via the App Directory.

## Structure
* A user in Slack types in the message box with the command, and submits it.
* A data payload is sent via an HTTP POST request to the URL configured for that command in your app.
* The app responds in some way.

# Serverless Slash Commands with Python
Here’s a way to build them with Python, host them for pennies a month on (Amazon)AWS Lambda, and use these same tools to issue delayed responses when creating long-running commands. 

## Slack App
* Create a Slack app
* Scroll down to _App Credentials_ section and make note of your app's verification token.
* ex) command invoked with /hello-there responds with "General Kenobi!"
* Create New Command, placeholder request url

## Install your app to your workspace
* install app in Slack workspace, Basic information page, click Install App to Workspace to authorize the app
* open slack and test commands/ you should see autocorrect

## Development
-Flask
    
    $ pyenv virtualenv 3.6.4 hello-there
    $ pyenv local hello-there
    (hello-there)$ pip install flask
    
 Backend for command
 1. recieve a POST request
 2. verify that the request was issued by Slack 
 3. respond with the desired message
 
 ex) file called **hello-there.py**
 
     import os

    from flask import abort, Flask, jsonify, request


    app = Flask(__name__)


    def is_request_valid(request):
        is_token_valid = request.form['token'] == os.environ['SLACK_VERIFICATION_TOKEN']
        is_team_id_valid = request.form['team_id'] == os.environ['SLACK_TEAM_ID']

        return is_token_valid and is_team_id_valid


    @app.route('/hello-there', methods=['POST'])
    def hello_there():
        if not is_request_valid(request):
            abort(400)

        return jsonify(
            response_type='in_channel',
            text='<https://youtu.be/frszEJb0aOo|General Kenobi!>',
        )
   **Slack Verification Token** is the app's verification token from before
   **Slack Team ID** To find your Slack team ID is open to Slack web client in your browser, inspect the source using the dev tools, and search for team_id.
   _is_request_valid()_ See slack's command validation docs and _link formatting docs_ 
   
   * Run the app like you would any other Flask app while exporting the environment variables it needs.
   
    (hello-there)$ SLACK_VERIFICATION_TOKEN=your-verification-token SLACK_
    
The app will run on port 5000 by default
   * install ngrok
   * test the command ffrom Slack
   * leave the server running and start ngrok in a separate process
    
    $ ngrok http 5000    
    
Copy the second HTTPS forwarding URL
   
    https://8731214d.ngrok.io
    
In your browser, go to Slack , open created app's "Slash Commands" section. Replace the _Request URL_ with the ngrok forwarding URL and the path to your created app's **/hello-there** endpoint

**Request URL**

    https://8731214d.ngrok.io/hello-there
  * Save the changes, test the command in Slack
  
## Deployment
Slash Commands are event-driven, they don't need continuos servers. 
Use Python framework _Zappa_ to deploy Flask app to Amazon Lambda.

    (hello-there)$ pip install zappa
    
*If you haven't already, create a local _AWS cresentials file_ (Zappa needs this file to sign requests to AWS

    (~/ .aws/credentials)

Define simple Zappa settings file called **zappa_settings.json**

    {
        "prod": {
            "app_function": "hello-there.app",
            "aws_region": "us-east-1",
            "exclude": [
                "__pycache__",
                ".git/*",
                "gitignore",
                ".python-version",
                "LICENSE",
                "README.md",
                "requirements.txt",
                "zappa_settings.json",
             ],
             "keep_warm": true,
             "keep_warm_expression": "rate(5 minutes)",
             "memory_size": 128,
             "project_name": "default",
             "project_name": "hello-there",
             "runtime": "python3.6",
             "s3_bucket": "hello-there",
             "timeout_seconds": 30,
         }
      }
 These settings tell Zappa where to find your app, what you want to prevent from being uploaded to AWS, and how to onfigure the resulting Lambda function.
 
 * Deploy your app to AWS
 
        (hello-there)$ zappa deploy prod
        
 * Head to AWS console in your browser, go to Lambda service , see new function
                
                
                
                
                
        


## Created by Rodney
  
  /helpdesk
  

## Built in 

 Invite a member to a channel
 
    /invite @someone [#channel]
    
 Set a reminder to a member or a channel
 
    /remind [@someone or #channel] to [What] [When]
    
 Get a list of reminders you have set
 
    /remind list
    
 Search slack messages and files
 
    /search [your text]
    
  
  
    
    
