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

# Mailing System


### Pen (index.php)

   Accept webhooks from BambooHR.
     
    <?php
    
    $json = file_get_contents('php://input');
    $action = json_decode($json, true);
    $action_id =$action->id;
    $card_id = $action->data->card->id;
    var_dump($array);
    
   Post webhook input to local file msg.php
   (Overwrite info every 4 hours)
   (Keep same file location) cd directory
   
   curl -o /Users/rodneynobles/Backup/subject.txt https://fileinfo.com/extension/example
   
    file_put_contents('subject.txt', 'insert subject here');
      echo file_get_contents('subject.txt');// insert subject here
      file_put_contents('subject.txt', 'new subject');;
      echo file_get_contents('subject.txt); // new subject
  
### Paper (subject.txt)
change from a read-only chmod 777 subject.txt

    Hello

### Envelope(mcpmailx.php)

    echo "First, Last, Department, Location, Effective Date, Employment Status" | mail -q subject.txt -s "Employee Status Update" -r "MCP SambaTV<noreply@samba.tv>"  -S replyto="Rodney<rodney@samba.tv>" rodney@samba.tv
    
### Crontab

    yum install php-cli
    crontab -e
read file directory

    readlink -f test.php
    /home/automan/mcpmailx.php
    crontab -e 
    0 0 * * * cd /home/automan/; ./mcpmailx.php
    0 */2 * * * = At minute 0 past every 2nd hour
    
    or
    
    0 0 * * * php /var/www/vhosts/domain.com/httpdocs/scripts/example.php 
This will execute every day at midnight. 


    


