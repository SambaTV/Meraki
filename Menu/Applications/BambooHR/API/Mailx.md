# Send Automated Linux email with gmail
mailx with a gmail Account profile.

Any email sent from the system will get sent through the gmail servers. 
 * host email domain with Gsuite 
 * make a **noreply** mailbox
 * set up 2 factor authentication on it
 * password for less secure apps
 
 ## Install mailx
 
 
      yum install heirloom-mailx
      sudo apt-get install heirloom-mailx
 ## Create the gmail account for mailx
 
 Add the following information into ~/.mailrc with **nano ~/.mailrc**
 
      account gmail {
          set smtp-use-starttls
          set ssl-verify=ignore
          set smtp-auth=login
          set smtp=smtp://smtp.gmail.com:587
          set from="noreply@yourdomain.com(Your real name)"
          set smtp-auth-user=noreply@domain.com
          set smtp-auth-password=your_less_secure_apps_password
          set ssl-verify=ignore
      }
      
 Customize settings above
 Save and send a text message to yourself
 
      echo -e "Mail body text" | mailx -A gmail -s "Mail subject" your@email
      
 You should receive your email soon from your gmail account
 
 _For automated system-wide emails to be sent correctly you need to login as root. You can **sudo su** to get access as root
 then repeat this process_
