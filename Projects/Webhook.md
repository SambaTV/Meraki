# Work flow

## (Allissa) BambooHR Webhook configuration
 ## (Bard) IP address -> HTTPS or HTTP -> URL Redirect
## (Me ) code

## Prerequisites
Webhook name: 

    Onboard/Offboard
What fields to monitor:

    Start Date, Termination date, Employment Status
What fields to post:

    First, Last, Department, Location, Effective Date, Employment Status
Form format:

     JSON
Post to URL: 

    https://webhook.site/f8ae5657-e185-4918-aaa7-2824626988d4 

Secret Key:  Security key, so only systems that have the secret key can post to your webhook Enter into terminal
 
    ruby -rsecurerandom -e 'puts SecureRandom.hex(20)'  export SECRET_TOKEN=your_token

When should data be sent: 
 
    Every 4 hours
    
## URL
 Secure tunnels to localhost
 "I want to expose a local server behind a NAT or firewall to the internet"
 **ngrok
 
  
## Code

 _Where do I keep code?
    Index.php file-

_How do Accept webhook?

_How do I write program to send email?
  Mailx crontab (pulls from file, 


_How do I set up a webhook?
1. Verify webhook 
so that BambooHR knows its safe 
  index.Php file

    <?php
    
    if(isset($_REQUEST['hub_challenge'])) {
      $challenge = $_REQUEST['hub_challenge'];
      $token = $_REQUST['hub_verify_token'];
    }
    
    if($token == "myCustomToken123") {
      echo $chalenge; 
    }





