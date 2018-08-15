# Tix Server
**cd ..**
move up

**cd ~**
root/ home

**cd -**
move to last dir

**:wq** 
comment out

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
    
    mkdir -p /var/www/test.bhrjcstv.com/public_html
    mv html/index.html tes.bhrjcstc.com/public_html
    vim /etc/httpd/conf/httpd/conf
    
    
    
    
    

    
  
 
 put file in directory
