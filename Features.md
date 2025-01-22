# User Registration API Features.

## Introduction:

this document contain dates, features, endpoints for User registration API.


## Entity

* **User**
    * **id:** Long (Unique identifier)
    * **name:** String (3-30 characters, alphanumeric)
    * **email:** String (Valid email format, unique)
    * **password:** String (Encrypted with [algoritmo de criptografia]) 
    * **admin:** Boolean (Indicates if the user is an administrator)
 

  ##Endpoints.

  01 Register user:
  @POST Content-Type : apllication/json {name:, e-mail:, password:}
  URL: http://domain/user/register

  02Login
  @POST Content-Type : apllication/json {name: || e-mail:, password:}
  URL: http://domain/user/login

  03 update
  @patch Content-Type : application/json {data that the user wants to change}
  URL: http://domain/user/id


  04 Delete
  @DELEET Content-Type : application/json {name:, e-mail, password}
  URL: http://domian/user/id

  05 change password
  @PUT Content-Type : application/json {password}
  URL: http://domain/user/id
  
