# mutt : email_client_on_linux
Instructions to setup mutt email to access emails from your terminal. 

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
## Customizations ..

### Making mutt look pretty (Color templates)
mutt in its vanilla version looks uncoool. For all the people who want their mutt to look good . Consider implementing the following color templates. 

Step 06 : Pick a template (you can find one in the mutt-color-template dir) of your choice. 
Make sure you download the directory and place it in the same directory as yout muttrc file. Add the source to your muttrc file . 
```
source mutt-color-templates/dark-16.muttrc
```

### Creating a desktop shortcut (exclusively for slothbears)
One might find it tiring to open a terminal and type a 4 letter cmd "mutt". Nevertheless if you want to open the terminal based email client with a click on your desktop , you can do that...

Step 06 : Create a .desktop file and paste the contents in it. Give necessary permissions for it .
You can find the .desktop file in this repository.

### Setting your offline email : <TODO>
The basic version of mutt looks at the servers on the internet to create cache and that forces you to have an internet connection to use mutt... until this !!!



  Note  : 
  1)  $ refers to terminal commands , only the after $ should be entered !!
  
  References / resources : 
  https://linuxconfig.org/how-to-install-configure-and-use-mutt-with-a-gmail-account-on-linux \
  https://www.youtube.com/watch?v=CxPQ_IVLYvM \
  FOr color templates : https://github.com/altercation/mutt-colors-solarized
  

