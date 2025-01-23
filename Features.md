# User Registration API Features.

## Introduction:

this document contain dates, features, endpoints for User registration API.


## Entity

* **User**
    * **id:** Long (Unique identifier)
    * **name:** String (3-30 characters, alphanumeric)
    * **email:** String (Valid email format, unique)
    * **password:** String (Encrypted with [algoritmo de criptografia])
    * **role:** String (enum: "user", "admin")

### Attention
To view the Use Case diagram and other diagrams, access this link

  ## Endpoints.
  
* **01 Register User**
    * **Method:** POST
    * **URL:** /users 
    * **Request Body:** 
        * `{"name": string (required), "email": string (required), "password": string (required)}`
    * **Response:**
        * 201 Created: User created successfully.
        * 400 Bad Request: Invalid or incomplete data.
        * 409 Conflict:User already exists.

* **02 Login**
    * **Method:** POST
    * **URL:** /users/login
    * **Request Body:** 
        * `{"email": string (required), "password": string (required)}`
    * **Response:**
        * 200 OK:Login successful ("token": "string" // JWT authentication token).
        * 401 Unauthorized: Invalid credentials.

* **03 Update User**
    * **Method:** PATCH
    * **URL:** /users/{userId}
    * **Request Body:** 
        * `{"name": string (optional), "email": string (optional)}` 
    * **Response:**
        * 200 OK: User updated successfully.
        * 400 Bad Request: Invalid or incomplete data.
        * 404 Not Found:User not found.

* **04 Delete User**
    * **Method:** DELETE
    * **URL:** /users/{userId}
    * **Response:**
        * 204 No Content: User deleted successfully.
        * 404 Not Found: User not found.

* **05 Change Password**
    * **Method:** PUT
    * **URL:** /users/{userId}/password
    * **Request Body:**
        * `{"new_password": string (required)}`
    * **Response:**
         * 200 OK: Password changed successfully.
        * 400 Bad Request: Invalid or incomplete data.
        * 404 Not Found: User not found.

* **06 Logout**
    * **Method:** DELETE
    * **URL:** /users/logout 
    * **Response:**
         * 200 OK:Logout successful.
     


# Admin

* **01 Register User**
    * **Method:** POST
    * **URL:** /admin/users 
    * **Request Body:** 
        * `{"name": string (required), "email": string (required), "password": string (required)}`
    * **Response:**
        * 201 Created: User created successfully.
        * 400 Bad Request: Invalid or incomplete data.
        * 409 Conflict:User already exists.

* **02 Login**
    * **Method:** POST
    * **URL:** /admin/login
    * **Request Body:** 
        * `{"adminCode": String (required), "password": string (required)}`
    * **Response:**
        * 200 OK:Login successful ("token": "string" // JWT authentication token).
        * 401 Unauthorized: Invalid credentials.

* **03 Update User**
    * **Method:** PATCH
    * **URL:** /admin/users/{userId}
    * **Request Body:** 
        * `{"name": string (optional), "email": string (optional)}` 
    * **Response:**
        * 200 OK: User updated successfully.
        * 400 Bad Request: Invalid or incomplete data.
        * 404 Not Found:User not found.

* **04 Delete User**
    * **Method:** DELETE
    * **URL:** admin/users/{userId}
    * **Response:**
        * 204 No Content: User deleted successfully.
        * 404 Not Found: User not found.

* **05 Change Password**
    * **Method:** PUT
    * **URL:** admin/users/{userId}/password
    * **Request Body:**
        * `{"new_password": string (required)}`
    * **Response:**
         * 200 OK: Password changed successfully.
        * 400 Bad Request: Invalid or incomplete data.
        * 404 Not Found: User not found.

* **06 Logout**
    * **Method:** DELETE
    * **URL:** admin/users/logout 
    * **Response:**
         * 200 OK:Logout successful.
     
* **07 List users**
    *  **Method:** GET
    *  **URL**/admin/users
    *  **Query Paramters**
    *  name: String (optional) - Filter by name.
    *  email: String (optional) - Filter by e-mail.
    *  role: String (optional) - Filter by role (e.g. "user", "admin").
    *  page: Integer (optional) - Page number.
    *  pagesize: Integer (optional) - Number of records per page.
    *  orderBy: String (optional) - Sort field (e.g. "name", "registrationDate").
    *  order: String (optional) - Sort order ("asc" or "desc").
    *   **Response:**
           * 200 OK: List users findBy Id,name,e-mail,.
           * 400 Bad Request: Invalid or incomplete data.
           * 404 Not Found:User not found.
* **Exemple**
* https//domain/admin/users?name=Maik&page2&pageSize=5&orderBy=name&order=desc
* **Json Response**
* [
    {"id":1,
     "name":Maik Gabriel Anton Furtado,
     "email": maik@gabriel.com,
     "role":user }

  {"id":2,
     "name":Maik Gabriel Furtado,
     "email": anton@gabriel.com,
     "role":user }
  ]


     


      
  
