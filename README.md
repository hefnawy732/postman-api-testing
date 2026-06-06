# API Testing Portfolio (Postman)

## Overview

This project demonstrates API testing using Postman across CRUD operations, authentication workflows, response validation, performance checks, and error handling scenarios.

Note: For Project screenshots: https://drive.google.com/drive/folders/14R1YZBxqkU6wP8D51jKXZf96C4TkfQWZ?usp=sharing

## APIs Used

* DummyJSON
* Postman Echo API
* Mock Servers

## Test Coverage

### Functional Testing

* GET Requests
* POST Requests
* DELETE Requests

### Authentication Testing

* Successful Login "Fetching token
* Missing Token (401)
* Forbidden Access (403)

### Response Validation

* Required Fields
* Data Types
* Empty Responses
* Generated IDs

### Performance Testing

* Response Time Validation

### Error Handling
* 301 Moved Permanently
* 400 Bad Request
* 401 Unauthorized
* 403 Forbidden
* 404 Not Found
* 405 Method Not Allowed
* 415 Unsupported Media Type
* 422 Unprocessable Entity (Simulated)
* 429 Too Many Requests
* 500 Internal Server Error

## Sample Assertions

### Status Code Validation

```javascript
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```

### Response Time Validation

```javascript
pm.test("Response time is under 2 seconds", function () {
    pm.expect(pm.response.responseTime).to.be.below(2000);
});
```

### Required Field Validation

```javascript
pm.test("Each user has required fields", function () {
    users.forEach(user => {
        pm.expect(user).to.have.property("id");
        pm.expect(user).to.have.property("email");
    });
});
```

## Status Codes Demonstrated

| Status Code | Description            |
| ----------- | ---------------------- |
| 200         | OK                     |
| 201         | Created                |
| 204         | No Content             |
| 301         | Moved Permanently      |
| 400         | Bad Request            |
| 401         | Unauthorized           |
| 403         | Forbidden              |
| 404         | Not Found              |
| 405         | Method Not Allowed     |
| 409         | conflict               |
| 415         | Unsupported Media Type |
| 422         | Unprocessable Entity   |
| 429         | Too Many Requests      |
| 500         | Internal Server Error  |

## Project Structure

```text
API Testing Portfolio
│
├── GET Users
│   ├── Success (200)
│   ├── Invalid Endpoint (404)
│   ├── Invalid Parameter (400)
│   ├── Moved Permanently (301)
│
├── POST User
│   ├── Success Creation (201)
│   ├── Missing required fields - (400 Bad request)
│
├── Authentication
│   ├── Login Success
│   ├── Missing Token (401)
│   └── Forbidden Access (403)
│
├── DELETE User
│   ├── Successful Delete
│   └── Resource Not Found
│   └── Deleting the entire resource path - (405 Method Not Allowed)   
│
└── Other statuses
    ├── Invalid request type - (415)
    └── Duplicate data - (409 Conflict)
    └── Invalid business rules - (422)
    └── Internal server error - (500)
    └── Rate limit - (429)
```

## Skills Demonstrated

* API Testing
* Postman Test Scripts
* Mock Servers
* Authentication & Authorization
* Error Handling
* Response Validation
* Performance Testing
* Technical Troubleshooting
* REST API Fundamentals
