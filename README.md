 # Send Mail From Terminal  using gmail and Mutt.
   
We can send mails from our terminals from gmail by using mutt package. 

It really cool idea to write scipts for login alerts  or some notifications from your PC or
servers for monitering its performance.

In such cases ,mutt is very nice package to send mails from command line or scripts in easy way.

Let see how to Install and Configure Mutt package in our PC

# Install Mutt Package

CentOs   : 

                 yum install mutt             
Ubuntu   :  

                 sudo apt-get install mutt

# Configure Mutt

Create these folders

                  mkdir -p /.mutt/cache
                  
Create Mutt Configuration file ~/.muttrc and add below lines and change your gmail and password 

                set from = "user@gmail.com"
                set realname = "ANY NAME"
                set imap_user = "username@gmail.com"
                set imap_pass = "gmail-password"
                set folder = "imaps://imap.gmail.com:993"
                set spoolfile = "+INBOX"
                set postponed ="+[Gmail]/Drafts"
                set header_cache =~/.mutt/cache/headers
                set message_cachedir =~/.mutt/cache/bodies
                set certificate_file =~/.mutt/certificates
                set smtp_url = "smtp://user@smtp.gmail.com:587/"
                set smtp_pass = "gmail-password"
                set move = no 
                set imap_keepalive = 900
  
# Gmail Setup : 

In your gmail, click the gear icon on right corner, open Settings ,Then click on Forwarding POP/IMAP on top , and enable IMAP Aceess . Click on configuration instructions to know more about IMAP access settings.

# Sending Mails :
  
  1.Sends mail with subject, messege body from given file ( msgbody.txt )
               
               mutt -s "Subject here" username@gmail.com < msgbody.txt
  
  2.Sends mail with given subject, msg body and attachment.
  
               mutt -s "subject Here" username@gmail.com < msgbody.txt  -a  attachment.pdf
   
  3. This command also does same as above but otherway.
               
               echo "Messege Here" | mutt -s "Subject here" username@gmail.com -a attachment.pdf
   
# Reference : 
   
   Its highly recomended to visit mutt documentation for more details.
   
               http://www.mutt.org/#doc
               
               
             # =========================================================================#
             #                        ANJI BABU KAPAKAYALA                              #
             #                         IIT KANPUR, INDIA.                               #
             #==========================================================================#






