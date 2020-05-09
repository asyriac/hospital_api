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
- test/ - This folder contains the unit tests for the api routes.

# API

## API to register a doctor

URL [POST]: /api/v1/doctors/register

ACCESS : Public

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

ACCESS : Public

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

## API to register a patient

URL [POST]: /api/v1/register_patient

ACCESS : Private

```
//request
{
  "name": "Doe",
  "phone": "123456789"
}

//response
{
    "success": true,
    "body": {
        "reports": [],
        "_id": "5e82254a43104d3f1ca53470",
        "name": "doe@gmail.com",
        "phone": "123456789",
        "__v": 0
    }
}
```

## API to create a report

URL [POST]: /api/v1/patients/:id/create_report

ACCESS : Private

```
//request
{
  "status" : "Symptoms-Quarantine"
}
//response
{
    "success": true,
    "body": {
        "_id": "5e8225c9e5c2340d6069505e",
        "patient": "5e82254a43104d3f1ca53470",
        "doctor": "5e821cc1647d1d2e403efcad",
        "status": "Symptoms-Quarantine",
        "date": "2020-03-30T17:00:57.726Z",
        "__v": 0
    }
}
```

## API to fetch all reports of a patient

URL [GET]: /api/v1/patients/:id/all_reports

ACCESS : Public

```
//response
{
    "success": true,
    "body": {
        "patient_name": "Doe",
        "phone": "123456789",
        "reports": [
            {
                "doctor": "John",
                "status": "Negative"
            },
            {
                "doctor": "Jacob",
                "status": "Negative"
            },
            {
                "doctor": "John",
                "status": "Negative"
            },
            {
                "doctor": "Steve",
                "status": "Symptoms-Quarantine"
            },
            {
                "doctor": "Brad",
                "status": "Positive-Admit"
            }
        ]
    }
}
```

## API to fetch all reports based on status

URL [GET]: /api/v1/reports/:status

ACCESS : Public

```

//response
{
    "success": true,
    "body": {
        "caseCount": 3,
        "report": [
            {
                "doctor": "John",
                "patient": {
                    "name": "Doe",
                    "phone": "123456789"
                }
            },
            {
                "doctor": "Steve",
                "patient": {
                    "name": "Steve",
                    "phone": "3234146789"
                }
            },
            {
                "doctor": "John",
                "patient": {
                    "name": "Steve",
                    "phone": "652145678"
                }
            }
        ]
    }
}
```
