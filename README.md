   # Send Mail From Terminal  using gmail and Mutt.
   

We can send mails from our terminals from gmail by using mutt package. 

It really cool idea to write scipts for login alerts  or some notifications from your PC or
servers for monitering its performance.

In such cases ,mutt is very nice package to send mails from command line or scripts in easy way.

Let see how to Install and Configure Mutt package in our PC

# Step 1 :  Install Mutt Package

CentOs  : 

                  yum install mutt
Ubuntu  :  

                  sudo apt-get install mutt

# Step 2 :  Configure Mutt

Create these folders

                  mkdir -p /.mutt/cache
                  
Create Mutt Configuration file ~/.muttrc and add below lines

                set from = "user@gmail.com"
                set realname = "Guillermo Garron"
                set imap_user = "user@gmail.com"
                set imap_pass = "password"
                set folder = "imaps://imap.gmail.com:993"
                set spoolfile = "+INBOX"
                set postponed ="+[Gmail]/Drafts"
                set header_cache =~/.mutt/cache/headers
                set message_cachedir =~/.mutt/cache/bodies
                set certificate_file =~/.mutt/certificates
                set smtp_url = "smtp://user@smtp.gmail.com:587/"
                set smtp_pass = "password"
                set move = no 
                set imap_keepalive = 900
  
