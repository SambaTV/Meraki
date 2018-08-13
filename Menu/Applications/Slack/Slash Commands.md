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
    
  
  
    
    
