
### GET User

#### Description

Retrieve user information based on the provided user number.

#### Method

GET

#### Relative Path

```
/{number}
```

#### Parameters

- `number`: The unique number associated with the user.

#### Response

- Status Code: 200 OK
- Body: JSON object containing user information, including `sys_id`, `name`, and `email`.
- Status Code: 404 Not Found
- Body: JSON object with an error message if the user is not found.

---

### GET Users

#### Description

Retrieve information for all users or filter users by email.

#### Method

GET

#### Relative Path

```
?email={email}
```

#### Parameters

- `email` (optional): Filter users by email.

#### Response

- Status Code: 200 OK
- Body: JSON array containing information for all matching users.
- Status Code: 404 Not Found
- Body: JSON object with an error message if no users are found.

---

### POST create_user

#### Description

Create a new user with the provided name and email.

#### Method

POST

#### Relative Path

```
N/A
```

#### Body Parameters

- `name`: The name of the new user.
- `email`: The email address of the new user.


The purpose of this project is to create a basic backend application in ServiceNow, which can serve as a foundational backend for quick and easy frontend development. ServiceNow provides a powerful platform for developing enterprise applications, and by establishing a basic backend structure, developers can streamline the process of building frontend applications with ServiceNow as the backend.

This backend application includes four main functionalities: retrieving user information by user number, retrieving all users or filtering users by email, creating a new user, and deleting a user record. These functionalities cover essential CRUD (Create, Read, Update, Delete) operations, offering a solid foundation for building more complex applications.

By providing a pre-built backend with commonly used functionalities, developers can focus more on frontend development, user experience, and application logic, rather than spending time on backend setup and implementation. This project aims to simplify the development process, accelerate project timelines, and facilitate rapid prototyping and iteration of frontend applications on the ServiceNow platform.

#### Response

- Status Code: 201 Created
- Body: JSON object containing the number of the newly created user.
- Status Code: 400 Bad Request
- Body: JSON object with an error message if either `name` or `email` is missing in the request body.

---

### DELETE user

#### Description

Delete a user record based on the provided email.

#### Method

DELETE

#### Relative Path

```
?email={email}
```

#### Parameters

- `email`: The email address associated with the user to be deleted.

#### Response

- Status Code: 200 OK
- Body: JSON object with a success message indicating the number of records deleted.
- Status Code: 404 Not Found
- Body: JSON object with an error message if no record is found to delete.
