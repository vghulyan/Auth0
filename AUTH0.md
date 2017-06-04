# How to Login/Register using Auth0 popup component against a custom MongoDB

## To make sure it works on both desktop and mobile

## Use the same login popup as fiverr

## Allow login using user/email/password, facebook and google.

## Registration rule - two way authentication
### When user registers, the system should send an authentication email, asking user to click on the link to be authenticated. Upon clicking the link then the user will be authentication/authorised to use the secure page.

## Login
1. If user is not logged in and tries to access a secure page then a login popup should appear. If user logins then system should redirect to the original link where the request was made originally.
2. If user logged in and user refreshes the screen then system should not redirect to login page but stay on the same page.
3. If user logged in then logout link should appear and login link should disappear. 
4. Allow user to be authenticated using google or facebook.
5. Link to retrieve the forgotten password

## Secure page
Create a middleware to check if the request has a valid token and can perform a certain operations using secret key.

## Registration
### When user sucessfuly registers but not authorised to use the system yet, then save the record to temp table. Upon registration, send an email template to users email address asking user to click the link to be authenticated. If user clicks on the link then authenticate the user. If user did not click the link within 24 hours remove the user from the temp table.

## Test
###  Login
1. Test against, wrong user, correct password
2. Correct user, wrong paswsword
3. Wrong user, wrong password
4. Correct user, correct password

### Register
1. Test against, min user name
2. If username exist (in the main user table)
3. If email exist
4. if password is valid (using password rule)

## Prerequisits
### Rules
1. User name min length 2 chars
2. Valid email address
3. Password rule: min length 6 chars, using upper case, special character and number
4. Create a temporary user table for unothrorised users, delete after authentication
5. The temorary table create with time to live, delete after 24 hours

## Documentation
### How and where to configure
1. Write documentation the steps taken.
2. Logo on the popup
3. token/session time out/exipration
4. Password: length, alphanumeric, upper case, etc...