# mutt : email_client_on_linux
Instructions to setup mutt email to access emails via console

This is a comprehensive set of instructions to setup mutt on your ubuntu 

Step 01 : Install mutt 
```
$ sudo apt-get install mutt
```
Step 02 : Create and edit the congif file 
Create a directory ".mutt" by :
```
$ mkdir .mutt
```
Step 03 :Navigate to the .mutt directory and create a muttrc file (which acts as a config file for mutt). Do it by the following commands :
```
$ vim muttrc
```
Step 04: Paste the following contents in the muttrc file . After done type :wq to write and quit vim editor
```
#### Starts for here !!!

set from = "test@iith.ac.in"   
set realname = "test name"
set imap_user = "test@iith.ac.in"
set imap_pass = "<mutt-app-specific-password>"

##REMOTE GMAIL FOLDERS
set folder = "imaps://imap.gmail.com:993"
set spoolfile = "+INBOX"
set postponed ="+[Google Mail]/Drafts"
set trash = "+[Google Mail]/Trash"

##SMTP Settings to sent email
set smtp_url = "smtp://test@iith.ac.in@smtp.gmail.com:587/"   
set smtp_pass = "<mutt-app-specific-password>"

##LOCAL FOLDERS FOR CACHED HEADERS AND CERTIFICATES
set header_cache =~/.mutt/cache/headers
set message_cachedir =~/.mutt/cache/bodies
set certificate_file =~/.mutt/certificates

##SECURING
set move = no  #Stop asking to "move read messages to mbox"!
set imap_keepalive = 900

##Sort by newest conversation first.
set sort = reverse-threads
set sort_aux = last-date-received

##Set editor to create new email
set editor='vim'
:wq

#### Ends here !!!
```  
  
Note  : Generating an app-specific-password for Mutt

If we are using google two-factor authentication, to be able to access our gmail account from Mutt, we need to generate an app-specific-password, since google requires it for the applications that don’t use Oauth2 as authentication method. To generate an app-specific-password, just navigate to the link provided below , authenticate yourself, and follow the instructions to generate the password: we will use it in the configuration.
  
 Link  --> https://security.google.com/settings/security/apppasswords
  
  
 Step 05 :  Stop reading this and start using mutt :) by the following cmd
 ```
 $mutt
```
  
  Note  : 
  1)  $ refers to terminal commands , only the after $ should be entered !!
  
  References  : 
  https://linuxconfig.org/how-to-install-configure-and-use-mutt-with-a-gmail-account-on-linux
  https://www.youtube.com/watch?v=CxPQ_IVLYvM

