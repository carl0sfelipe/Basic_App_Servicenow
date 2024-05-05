# ServiceNow Basic Backend App

This project aims to provide a basic backend application in ServiceNow, facilitating quick and efficient frontend development by offering foundational backend functionalities. Developers can clone this project and use it as a basis for building frontend applications, streamlining the development process and accelerating project timelines.

## Functionality

This backend application supports the following functionalities:

### 1. GET User

Retrieve user information based on the provided user number.

- **Method:** GET
- **Relative Path:** `/{number}`
- **Parameters:**
  - `number`: The unique number associated with the user.
- **Response:**
  - Status Code: 200 OK
    - Body: JSON object containing user information, including `sys_id`, `name`, and `email`.
  - Status Code: 404 Not Found
    - Body: JSON object with an error message if the user is not found.

### 2. GET Users

Retrieve information for all users or filter users by email.

- **Method:** GET
- **Relative Path:** `?email={email}`
- **Parameters:**
  - `email` (optional): Filter users by email.
- **Response:**
  - Status Code: 200 OK
    - Body: JSON array containing information for all matching users.
  - Status Code: 404 Not Found
    - Body: JSON object with an error message if no users are found.

### 3. POST create_user

Create a new user with the provided name, email, and password.

- **Method:** POST
- **Relative Path:** N/A
- **Body Parameters:**
  - `name`: The name of the new user.
  - `email`: The email address of the new user.
  - `password`: The password of the new user.
- **Response:**
  - Status Code: 201 Created
    - Body: JSON object containing the number of the newly created user.
  - Status Code: 400 Bad Request
    - Body: JSON object with an error message if either `name`, `email`, or `password` is missing in the request body.

### 4. DELETE user

Delete a user record based on the provided email.

- **Method:** DELETE
- **Relative Path:** `?email={email}`
- **Parameters:**
  - `email`: The email address associated with the user to be deleted.
- **Response:**
  - Status Code: 200 OK
    - Body: JSON object with a success message indicating the number of records deleted.
  - Status Code: 404 Not Found
    - Body: JSON object with an error message if no record is found to delete.

### 5. POST login

Authenticate a user based on the provided email and password.

- **Method:** POST
- **Relative Path:** `/login`
- **Body Parameters:**
  - `email`: The email address of the user.
  - `password`: The password of the user.
- **Response:**
  - Status Code: 200 OK
    - Body: JSON object with a success message indicating successful login and the user's unique identifier (`user_id`).
  - Status Code: 401 Unauthorized
    - Body: JSON object with an error message if the provided password is invalid.
  - Status Code: 404 Not Found
    - Body: JSON object with an error message if the user is not found.

## Usage

To use this backend application, simply clone the repository and deploy it in your ServiceNow instance. Once deployed, you can start making requests to the provided endpoints to interact with the backend functionalities.
