\#\# Use case diagram \#\#

\#\# Use Case: User Registration

\*\*ACTOR:\*\* User

\*\*PRECONDITION:\*\* User is not registered.

\*\*POSTCONDITION:\*\* User registered successfully or validation error.

\*\*Main flow\*\*  
1\. User fills out the registration form.  
2\. System validates the data.  
3\. System sends verification code by e-mail.  
4\. System validates the code.  
5\. System saves the user in the database.

\*\*Alternative flows\*\*  
1\. \*\*E-mail already registered:\*\*  
    \* The system displays an error message indicating that the e-mail has already been registered previously.  
2\. \*\*Weak password:\*\*  
    \* The system displays an error message indicating that the password entered is weak.  
3\. \*\*UserName validation error:\*\*  
    \* The system displays an error message indicating that the name must contain at least 3 characters and a maximum of 30 characters.  
4\. \*\*Error saving to the Database:\*\*  
    \* The system displays a generic error message and HTTP code and records an error in a new log.

\#\# Use Case: User Login

\*\*ACTOR:\*\* User

\*\*PRECONDITION:\*\* User has a registered account and is disconnected from the system.

\*\*POSTCONDITION:\*\* User logs into the system or validation error.

\*\*Main flow\*\*  
1\. User fills out the login form.  
2\. The system validates the user's data.  
3\. The system sends a verification code by e-mail.   
4\. The system validates the code.  
5\. The user is redirected to the home page.

\*\*Alternative flows\*\*  
1\. \*\*User not found:\*\*  
    \* The system displays an error message indicating that the user was not found.  
2\. \*\*Incorrect password:\*\*  
    \* The system displays an error message indicating that the password is incorrect.  
3\. \*\*The user forgets the password:\*\*  
    \* The user requests password recovery.  
    \* The system redirects the user to the password recovery form.

\#\# Use Case: Recover Password

\*\*ACTOR:\*\* User

\*\*PRECONDITION:\*\* User requests to recover password.

\*\*POSTCONDITION:\*\* User updates password or validation error

\*\*Main flow\*\*  
1\. The user fills out the e-mail form.  
2\. The system validates the form.  
3\. The system sends a code by e-mail.  
4\. The system validates the code.  
5\. The user fills out the new password form.  
6\. The user confirms the new password.  
7\. The system validates the form.  
8\. The system updates the password in the Database.  
9\. The system sends an email confirming the password change.  
10\. The system redirects the user to login.

\*\*Alternative flows\*\*  
1\. \*\*Email not found:\*\*  
    \* The system displays an error message stating that the email was not found.  
2\. \*\*Incorrect or invalid code:\*\*  
    \* The system displays an error message indicating an incorrect or invalid code.  
3\. \*\*Weak password:\*\*  
    \* The system displays an error message indicating that the new password is weak.  
4\. \*\*Incompatible password:\*\*  
    \* The system displays an error message indicating that the passwords must be the same.  
5\. \*\*Error saving password to the database:\*\*  
    \* The system displays a generic error and records the error in a new log.

\#\# Use Case: Update User Data

\*\*ACTOR:\*\* User

\*\*PRECONDITION:\*\* User is logged into the system.

\*\*POSTCONDITION:\*\* Update user data or error.

\*\*Main flow\*\*  
1\. The user fills in the data to be updated.  
2\. The system validates the data.  
3\. The system updates the data in the database.

\*\*Alternative flows:\*\*  
1\. \*\*Empty fields:\*\*  
    \* The system displays an error message indicating that the field cannot be empty.  
2\. \*\*Validation error:\*\*  
    \* The system displays an error message indicating that the field was not filled in correctly.  
3\. \*\*Weak password error:\*\*  
    \* The system displays an error message stating that the new password is weak.  
4\. \*\*Error updating the database:\*\*  
    \* The system displays a generic message and records the error in a new log.

\#\# Use Case: Delete Account

\*\*ACTOR:\*\* User

\*\*PRECONDITION:\*\* User is logged in.

\*\*POSTCONDITION:\*\* Account deleted from the system.

\*\*Main flow:\*\*  
1\. User fills out the form to delete their account.  
2\. The system validates the information.  
3\. The system deletes the user's account and returns to the registration page.

\*\*Alternative flows:\*\*  
1\. \*\*Incorrect user data:\*\*  
    \* The system displays an error message with incorrect fields.

\#\# Use Case: Disconnect

\*\*ACTOR:\*\* User

\*\*PRECONDITION:\*\* User is logged in.

\*\*POSTCONDITION:\*\* User disconnects.

\*\*Main flow:\*\*  
1\. User sends a request to disconnect.  
2\. The system asks for confirmation.  
3\. The user confirms.  
4\. The system disconnects and returns to login.

\*\*Alternative flows:\*\*  
1\. \*\*User refuses to disconnect:\*\*  
    \* The system returns to home.  
