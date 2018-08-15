# Tix Server
**cd ..**
move up

**cd ~**
root/ home

**cd -**
move to last dir

**:wq** 
Hit the Esc key to enter "Normal mode". Then you can type : to enter "Command-line mode". A colon (:) will appear at the bottom of the screen and you can type in one of the following commands. To execute a command, press the Enter key.

:q to quit (short for :quit)
:q! to quit without saving (short for :quit!)
:wq to write and quit
:wq! to write and quit even if file has only read permission (if file does not have write permission: force write)
:x to write and quit (similar to :wq, but only write if there are changes)
:exit to write and exit (same as :x)
:qa to quit all (short for :quitall)
:cq to quit without saving and make Vim return non-zero error (i.e. exit with error)
You can also exit Vim directly from "Command mode" by typing ZZ to save and quit (same as :x) or ZQ to just quit (same as :q!). (Note that case is important here. ZZ and zz do not mean the same thing.)

Vim has extensive help - that you can access with the :help command - where you can find answers to all your questions and a tutorial for beginners.




**mkdir -p** 
creates arbitrary directories

## Set up for user

    ssh root@(your ip address)
    Password for terminal, the one Bard gave
    su automan
    cd ~
    
## Set up website with Apache Virtualhosts

    $ ssh root@(your ip address)
    password for terminal, the one Bard gave 
    cd /var/www
    pwd
   you should see /var/www
     
    ls
create file

    vi index.html
write file
    
    <html>
        <head>
                <title>Welcome to Dimension C-137!</title>
        </head>
        <body>
                <h1>Ricklantis</h1>
                <p>Oh Geez Rick</p>
        </body>
    </html>
exit vi
    ** press i to enter insert mode** 
    ** esc, then SHIFT + ZZ to save and exit**
   

    mkdir html
    mv index.html html/
    tree .
    
    (control) R - recent 
    
    vim /etc/httpd/conf.d/welcome.conf
commentation 
    
    :wq:
create and move directory
    
    mkdir -p /var/www/test.bhrjcstv.com/public_html
    mv html/index.html tes.bhrjcstc.com/public_html
edit our main httpd conf
    
    vim /etc/httpd/conf/httpd.conf
    
        #Enable MMAP
    EnableSendfile on

    #Load config files in the "/etc/httpd/conf.d" directory, if any.
    IncludeOptional conf.d/*.conf

    # Custom VHosts
    <VirtualHost *:80>
            ServerAdmin webmaster@test.bhrjcstv.com
            DocumentRoot /var/www/test.bhrjcstv.com/public_html
            ServerName test.bhrjcstv.com
            ServerAlias bhrjcstv.com
            ErrorLog /var/www/test.bhrjcstv.com/error.log
    <VirtualHost *:80>
    ~                                                                                                  
    ~                                                      

    
    
    

    
  
 
 put file in directory
