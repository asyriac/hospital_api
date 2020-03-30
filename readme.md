# Getting started

To get the Node server running locally:

- Clone this repo
- npm install to install all required dependencies
- Install MongoDB
- Change the enviroment variables in config folder as required
- npm run start the local server

# Application Structure

- server.js - The entry point to our application. This file defines our express server and connects it to MongoDB using mongoose. It also requires the routes and models we'll be using in the application.

- config/ - This folder contains configuration for mongodb.
- routes/ - This folder contains the route definitions for our API.
- models/ - This folder contains the schema definitions for our Mongoose models.
- controllers/ - This folder contains the actions to be performed on the routes.
- middleware/ - This folder contains middlewares.

# API

## API to register a doctor

URL [POST]: /api/v1/doctors/register

```
//request
{
  "name" : "John",
  "email": "john@gmail.com",
  "password": "password"
}

//response
{
    "success": true,
    "body": {
        "_id": "5e82241efb2a341348b00d46",
        "name": "John",
        "email": "john@gmail.com",
        "password": "$2a$10$uNDLGldwSsxY0cXgmDFWhu/k0cUkuNQxa4vR2ehW9PGKB5urx1bjO",
        "__v": 0
    },
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjVlODIyNDFlZmIyYTM0MTM0OGIwMGQ0NiIsImlhdCI6MTU4NTU4NzIzMCwiZXhwIjoxNTg4MTc5MjMwfQ.xcN_AhtkGjghRORIhQgqS94-WEchLjBahV-RpL0qCZk"
}
```

## API to login a doctor

URL [POST]: /api/v1/doctors/login

```
//request
{
  "email": "john@gmail.com",
  "password": "password"
}

//response
{
    "success": true,
    "body": {
        "_id": "5e82241efb2a341348b00d46",
        "name": "John",
        "email": "john@gmail.com",
        "password": "$2a$10$uNDLGldwSsxY0cXgmDFWhu/k0cUkuNQxa4vR2ehW9PGKB5urx1bjO",
        "__v": 0
    },
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjVlODIyNDFlZmIyYTM0MTM0OGIwMGQ0NiIsImlhdCI6MTU4NTU4NzIzMCwiZXhwIjoxNTg4MTc5MjMwfQ.xcN_AhtkGjghRORIhQgqS94-WEchLjBahV-RpL0qCZk"
}
```

--- Template---

## API to register a doctor

URL [POST]: /api/v1/doctors/register

```
//request
{
  name: John,
  email: john@gmail.com,
  password: password
}

//response
{
    "success": true,
    "body": {
        "_id": "5e82241efb2a341348b00d46",
        "name": "John",
        "email": "john@gmail.com",
        "password": "$2a$10$uNDLGldwSsxY0cXgmDFWhu/k0cUkuNQxa4vR2ehW9PGKB5urx1bjO",
        "__v": 0
    },
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjVlODIyNDFlZmIyYTM0MTM0OGIwMGQ0NiIsImlhdCI6MTU4NTU4NzIzMCwiZXhwIjoxNTg4MTc5MjMwfQ.xcN_AhtkGjghRORIhQgqS94-WEchLjBahV-RpL0qCZk"
}
```
