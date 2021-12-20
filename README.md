# Hades Distribution Company
We believe a certain individual uses this website for shady business. Can you find out who that is and send him an email to check, using the web site's functionality?
Note: The flag is not an e-mail address. 
  
## Task 1:  Log in the control panel
There is a simple login screen with 2 input fields.
It performs an HTTP-POST when the PHP page is submitted
  
There are two hidden input fields called name1 and name2
  
When the page is loaded, it pulls back a javascript file with a method in (doProcess()) which looks odd because all it does is submit the form - a submit button would do the same surely?  
  
in another js file, a jQuery one.
  
Inside the jQuery file is another version of doProcess() which hard-codes values into the hidden input fields.  This reveals the login credentials!
  
## Task 2:  Find the email to find the bad guy
I was browsing around.  The control panel had lots of ‘frames’ which loaded different pages.
  
the ‘send email’ page wasn’t helping me much
however the ‘Special Customers' Mailbox’ page seemed like it might contain some useful info
  
I actually noticed it via wireshark but really just had to view the page source:  there was a gif located in `./secret_area_/mails.gif`.  could this lead us to something hmmmm?
  
Changing the url to `docker.hackthebox.eu:port/main/secret_area_/` took me to a directory with a text file in.  inside the text file were a list of email addresses to try
  
One email has the domain ‘badmail’.  Is this the culprit? apparently not
  
[FuckthemALL@mail.com](mailto:FuckthemALL@mail.com)?
  
Tried them all, found the flag!
#hackthebox #hacking #pentesting #exploitation
