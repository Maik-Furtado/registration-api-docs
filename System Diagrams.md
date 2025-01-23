# DIAGRAMS:

This document presents all the system diagrams.

## Use case diagram ##

**Use case User is not registered:**
* ACTOR: User.
* PRECONDITION: User is not registered.
* POSTCONDITION: User registered successfully or validation error.


*Main flow*
* 01 User fills ou the registration form.
* 02 System validate the data.
* 03 System send verification code by e-mail.
* 04 System validate the code.
* 05 System saves the user in the database.

*Alternative flow*
* 01 E-mail already registered.
* The system displays an error message  indicating that the e-mail already been registered previous.

* 02 Weak password:
* The system displays an error message indicating that the password entered is week.

* 03 UserName validation erro:
* The system display on error message indicatiing that the name must contain at least 3 characteres and maximum 30 characteres.

* 04 Erro savin to the Database:
* the system displays a generic error messages and HTTP code and records an error in a new log.

## Use Case: User login into the system.
* ACTOR: User.
* PRECONDITION: User has a registered ands is disconnected from the system.
* POSTCONDITION: User login into the system or validation error.

  *Main flow*
  * 01 User fills out the login form.
  * 02 The system validates the user's data.
  * 03 The system send a verification code by e-mail.
  * 04 The system validades the code.
  * 05 The user as redirected to the home page.
 
    *Alternative flow*
    * 01 User not found:
    * The system displays an error message indicating that the user was not found.
   
    * 02 Incorret password:
    * The system displays an error message indicationg that the password is incorret.
   
    * 03 The user forgets the password:
    * The user request password recovery.
    * the system redirects the user to the password recovery form.
   
    * 
