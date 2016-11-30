# Advanced Login

## Reset User’s Password

*  From within the __Administration interface__, select __User Management__ and then __User__ from the Navigation Menu.  
*  Select the user whose password you need to reset, and click __Reset Password__. The password will be set to a blank password, which the user must then reset on his or her next login.

## Remember Me

*  Under **Properties -> Front End**, uncheck **Enable Remember Me** to force users to enter their password every time.  
*  When enabled, users will have the option to remember their password for up to the number of days specified under __Remember Me Age__.

## One Time Passwords (OTP)

One time passwords are an additional security method. The login process is in 2 stages. First, a user logs in with a username and password. Next, PaperTrail sends an SMS message that contains a PIN to the user’s mobile phone. The user enters the PIN to complete the login operation.  

One time passwords are a global. If a user does not have a mobile phone, then that user cannot log in with username and a password. However, the user can access PaperTrail with other SSO methods.

*  Make sure that SMS Notifications are configured.  
*  From __Services > Properties > One Time Password__, select __Require OTP SMS__.