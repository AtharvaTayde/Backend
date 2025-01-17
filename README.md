# Backend API Documentation

## `/users/register` Endpoint

### Description

Registers a new user by creating a user account with the provided information.

### HTTP Method

`POST`

### Request Body

The request body should be in JSON format and include the following fields:

- **fullname** (object):
  - `firstname` (string): User's first name (minimum 3 characters).
  - `lastname` (string): User's last name (minimum 3 characters).
- **email** (string): User's email address (must be valid).
- **password** (string): User's password (minimum 6 characters).

### Example Response

- `user` (object):
  - `fullname` (object).
    - `firstname` (string, required): User's first name (minimum 3 characters).
    - `lastname` (string, optional): User's last name (minimum 3 characters).
  - `email` (string, required): User's email address (must be valid).
  - `password` (string, required): User's password (minimum 6 characters).
- `token`(String): JWT Token

## `/users/login` Endpoint

### Description

Authenticates a user using their email and password, returning a jwt token upon success.

### HTTP Method

`POST`

### Request Body

The request body should be in JSON format and include the following fields:

- **email** (string): User's email address (must be valid).
- **password** (string): User's password (minimum 6 characters).

### Example Response

- `user` (object):
  - `fullname` (object).
    - `firstname` (string, required): User's first name (minimum 3 characters).
    - `lastname` (string, optional): User's last name (minimum 3 characters).
  - `email` (string, required): User's email address (must be valid).
- `token`(String): JWT Token


## `/users/profile` Endpoint

### Description

Retrieves the profile information of the authenticated user.

### HTTP Method

`GET`

### Authentication


Requires a valid JWT token in the Authorization header:

- **Authorization** (string): Bearer token for authentication.

### Example Response

- `user` (object):
  - `fullname` (object).
    - `firstname` (string, required): User's first name.
    - `lastname` (string, required): User's last name.
  - `email` (string, required): User's email address.

## `/users/logout` Endpoint

### Description

Logs out the current user and blacklist the token provided in cookie or headers

### HTTP Method

`GET`

### Authentication

Requires a valid JWT token in the Authorization header or cookie:


