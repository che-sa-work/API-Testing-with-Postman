# API Testing with Postman

## Online Loan Application API

This project demonstrates API testing techniques using Postman for a fictional Online Loan Application System.

The objective is to validate API functionality, request and response data, status codes, validation rules, authentication, error handling, and integration behavior.

> **Note:** This is a fictional portfolio project created for demonstration purposes. No confidential company data or production APIs are used.

---

## 🧪 Testing Scope

The following API operations are covered:

* Authentication
* Customer retrieval
* Customer creation
* Loan application creation
* Loan application retrieval
* Loan application update
* Loan application cancellation
* Input validation
* Negative testing
* Error handling
* Response validation

---

## 🔧 Tools

* Postman
* REST API
* JSON
* Git
* GitHub

---

## 📂 Project Structure

```text
api-testing-postman/
│
├── collection/
│   └── loan-application-api.postman_collection.json
│
├── environments/
│   └── qa-environment.postman_environment.json
│
├── test-scenarios/
│   └── api-test-scenarios.md
│
├── test-cases/
│   └── api-test-cases.md
│
├── bug-reports/
│   └── api-bug-reports.md
│
└── test-summary-report/
    └── api-test-summary-report.md
```

---

# API Endpoints

## Authentication

### Login

```http
POST /api/v1/auth/login
```

Used to authenticate the customer and obtain an access token.

---

## Customers

### Get Customer

```http
GET /api/v1/customers/{customerId}
```

Retrieves customer information.

### Create Customer

```http
POST /api/v1/customers
```

Creates a new customer.

---

## Loan Applications

### Create Loan Application

```http
POST /api/v1/loans
```

Creates a new loan application.

### Get Loan Application

```http
GET /api/v1/loans/{loanId}
```

Retrieves loan application information.

### Update Loan Application

```http
PUT /api/v1/loans/{loanId}
```

Updates an existing loan application.

### Cancel Loan Application

```http
PATCH /api/v1/loans/{loanId}/status
```

Updates the application status.

---

# What I Validate

### HTTP Status Codes

Examples:

```text
200 OK
201 Created
400 Bad Request
401 Unauthorized
404 Not Found
409 Conflict
500 Internal Server Error
```

### Response Body

I validate:

* Required fields
* Data types
* Field values
* IDs
* Status values
* Error messages
* Response structure

### Request Validation

I validate:

* Required parameters
* Headers
* Authentication
* Request body
* Data types
* Invalid values
* Boundary values

### Integration Validation

API responses are compared against expected application behavior and, where applicable, the corresponding UI data.

---

# Testing Approach

The API testing approach includes:

1. Review API documentation.
2. Identify endpoints and expected behavior.
3. Prepare positive and negative scenarios.
4. Configure authentication.
5. Execute API requests.
6. Validate HTTP status codes.
7. Validate response body and required fields.
8. Validate error handling.
9. Verify data consistency.
10. Document defects.
11. Retest fixes.
12. Perform regression testing.

---

# Sample Test Flow

```text
Login
  ↓
Obtain Access Token
  ↓
Get Customer
  ↓
Create Loan Application
  ↓
Retrieve Loan Application
  ↓
Update Application
  ↓
Verify Status
  ↓
Cancel Application
```

---

# Key QA Focus

This project demonstrates practical experience in:

* REST API testing
* Postman
* Request/response validation
* Positive testing
* Negative testing
* Boundary testing
* Authentication testing
* Integration testing
* Defect investigation
* Regression testing
* Test documentation
