// SubjectsPlus Version 2.0 - AD Integration //

The following instructions for AD Integration assume that you have a working install of 
SubjectsPlus 2.0 up and running. Please remember to backup all files and setup prior to 
continuing. We used the adLDAP src files as the main authenticator for our AD setup as it 
has the potential to support group, user, and contact management. However, for our 
purposes, we only set up and tested the user authentication. The full package and 
documentation can be found here: http://adldap.sourceforge.net/

//////////////////
// SETUP //
//////////////////

1. Place the 'src' folder under 'subjectsplus/control/'

2. Navigate to 'subjectsplus/control/src' and edit/configure 'adLDAP.php' to include your
AD information. 

3. Using SubjectsPlus' built in login, create a user with credentials that match AD 
information. (i.e. if your AD account suffix is '@domain.edu', you must create a user with 
the credentials 'user@domain.edu' in order to work properly).

Note: The email key you set up in SubjectsPlus should match the AD account suffix. 
Only the username is crucial here, a generic password will suffice as we will ultimately be 
authenticating against the user's AD password. 

4. Refer to the modified 'login.php'. Replace existing 'control/login.php' with the modified 
'login.php' (or refer to lines 190-235 to see changes made to include AD authentication to the 
login form)

5. Refer to the modified 'functions.php'. Replace existing 'control/includes/functions.php' 
with the modified 'functions.php' (or refer to lines 51, 72 to see changes made to alter 
the isCool function)

6. At this point, you should be able to point your browser to 'subjectsplus/control/login.php' 
and test your AD authentication against the user that you previously created. You should only 
have to use the AD base username and AD password here, as SubjectsPlus will construct the user 
email (i.e. If user's email = user@domain.edu, then login using 'user'). Good Luck!

Note: Once you have created a user, and successfully authenticated against AD, you should be 
able to use that account to add subsequent users. 