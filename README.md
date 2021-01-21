# **Send Mail From Terminal  using gmail and Mutt.**
   
  - We can send mails from our terminals from gmail by using mutt package. 

  - It really cool idea to write scipts for login alerts  or some notifications from your PC or
    servers for monitering its performance.

  - In such cases ,mutt is very nice package to send mails from command line or scripts in easy way.
  
  - Let see how to Install and Configure Mutt package in our PC

# **Install Mutt Package**

**CentOs   :** 
                 
       yum install mutt  
       
**Ubuntu   :**  

       sudo apt-get install mutt

# **Configure Mutt**

- Create these folders

                  mkdir -p /.mutt/cache
                  
- Create **Mutt** Configuration file **~/.muttrc** and add below lines and change your gmail and password 

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
  
# **Gmail Setup :**

**IMAP setup :**

In your gmail, click the gear icon on right corner, open Settings ,Then click on Forwarding POP/IMAP on top , and enable IMAP Aceess . Click on configuration instructions to know more about IMAP access settings.

**SSL setup:**

Inorder to access your gmail from mutt, you need to provide the access rights to mutt to use smtp server. turn ON the access to the less secure app
from the Google account. following link can be referenced.

      https://support.google.com/accounts/answer/6010255?p=lsa_blocked&hl=en&visit_id=637468299219858485-1060437365&rd=1

# **Sending Mails :**
  
  - Sends mail with subject, messege body from given file ( msgbody.txt )
               
        mutt -s "Subject here" username@gmail.com < msgbody.txt
  
  - Sends mail with given subject, msg body and attachment.
  
        mutt -s "subject Here" username@gmail.com < msgbody.txt  -a  attachment.pdf
   
  - This command also does same as above but otherway.
               
         echo "Messege Here" | mutt -s "Subject here" username@gmail.com -a attachment.pdf
   
# **Reference :**
   
   - Its highly recomended to visit mutt documentation for more details.
   
               http://www.mutt.org/#doc
             
             
# **Shell Script to Send Mails from Terminal**             
             
 ```shell
 
# Bash Script to send mails from terminal by using mutt package.
#
# Authour :  ANJI BABU KAPAKAYALA
#             IIT KANPUR, INDIA.
# USAGE   : sh send_mail.sh (Then follow instructionns)
#
#!/bin/bash
echo "=================================================="
echo -e "\e[31;44m*****WELCOME TO ANJI BABU MAILING SERVICE *****\e[0m"
echo "==================================================="
yes="y"
no="n"
echo ""
read -p "Enter mail-id:" mailid          #Enter mailid of reciver
read -p "Enter Subject :" subject        #Enter Subject of mail
# if [[ $subject == *"$no"* ]] then
#    echo "You choosed not to enter subject"
# fi
read -p "Write Message here  :" msg      # Write body of message here
# if [[ $msg == *"$no"* ]] 
# then
#    echo "You have choosed not to enter Message"
# fi
read -p "Any Attachments ( y/n) :" choice   #Enter y if you want to attach file else enter n
 if [[ $choice == *"$yes"* ]] 
 then
    read -p "Enter attachment :" filename   #Enter filename of attachment
    echo ""
    echo "sending mail to $mailid"
    echo "$msg" |mutt -s "$subject" $mailid -a $filename   
 else
    echo ""
    echo "No file is attached" 
    echo "sending mail to $mailid"
    echo "$msg" |mutt -s "$subject" $mailid   
 fi
echo ""
echo "Your mail has been sent."
echo ""
echo "====================================================" 
 ```
 ```
 
       # =========================================================================#
       #                        ANJI BABU KAPAKAYALA                              #
       #                         IIT KANPUR, INDIA.                               #
       #==========================================================================#
 ```





