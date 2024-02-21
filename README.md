## BE-Test
An explanation of chosen tools and how to test the API.

*The list of pre-registered emails in the database is available in section 4 of this document.

*Sensitive data for local testing, such as keys and passwords, are only available in the **.env** file sent by email.


### 1. Choices explanation

- API: REST;
- Database: MongoDB:

    Since there is no information about all user data that should be stored besides email and password, a non-relational database like MongoDB brings some flexibility and the possibility of storing new fields later, without much effort.

    Additionally, MongoDB was chosen due to its ease of implementation and native user authentication methods, making it possible to quickly enable login with email/password, web tokens, and other login providers, as well as other authentication-related functionalities (password recovery, confirmation email and password encryption).

### 2. Created API

The created API has a single POST route, which receives a user's email and password and attempts to log in. The server will return different messages in the following situations:

1. Successful login ( status: 200 ): Returns a success message, the generated web token for authentication, and some basic information about the user.
2. Incorrect user ( status: 404 ): Returns the error message "User not found".
3. Incorrect password ( status: 401 ): Returns the error message "Invalid credentials".

### 3. Testing

#### 3.1 Remote testing

The API is currently running on a cloud server, so the login route created can be accessed via the URL https://cmc-test-project-415003.rj.r.appspot.com/api/auth/login. There is no defined get route, so if accessed via a browser, there will only be an error message.

Each test should be a POST route, with the same URL mentioned above. The request body must contain a JSON object with an email and a password, as shown in the structure below. Make changes to the provided email and password to verify the different server responses.

 ````   {  "email": "antoneslima@gmail.com",  "password": "testpassword"    } ````

#### 3.2 Local Testing
If it is preferable to perform tests locally, the API code will be available in the repository at the link https://github.com/anktony/BE-test-cmc.git.  
  
Steps:

1. Download repository;
2. Install dependencies in the project root: ``npm install``;
3. Start the server on port 3000: ``npm start``;
4. In this case, the test URL should be http://localhost:3000/api/auth/login;
5. The structure of the tests should be identical to that provided in the Remote Testing subsection.

### 4. Registered Users
{ "email": "john.doe@example.com", "password": "password1" }  
{ "email": "jane.doe@example.com", "password": "password2" }  
{ "email": "alice.smith@example.com", "password": "password3" }  
{ "email": "bob.johnson@example.com", "password": "password4" }  
{ "email": "emily.brown@example.com", "password": "password5" }  
{ "email": "michael.wilson@example.com", "password": "password6" }  
{ "email": "jessica.lee@example.com", "password": "password7" }  
{ "email": "william.taylor@example.com", "password": "password8" }  
{ "email": "olivia.anderson@example.com", "password": "password9" }   
{ "email": "james.thomas@example.com", "password": "password10" }  
{ "email": "antoneslima@gmail.com", "password": "testpassword" }  
