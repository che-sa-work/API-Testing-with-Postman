# API Test Cases

## API-001 — Successful Login

**Endpoint**

```http
POST /api/v1/auth/login
```

**Priority:** Critical

### Request

```json
{
  "username": "test.customer@example.com",
  "password": "ValidPassword123"
}
```

### Expected Status

```text
200 OK
```

### Expected Response

```json
{
  "token": "<access-token>",
  "expiresIn": 3600
}
```

### Validation

* Status code is 200.
* Token is present.
* Token is not empty.
* `expiresIn` is returned.
* Response content type is JSON.

---

# API-002 — Invalid Login

**Endpoint**

```http
POST /api/v1/auth/login
```

### Request

```json
{
  "username": "test.customer@example.com",
  "password": "WrongPassword"
}
```

### Expected Status

```text
401 Unauthorized
```

### Expected Behavior

* Authentication fails.
* Access token is not returned.
* Appropriate error message is returned.

---

# API-003 — Get Customer

**Endpoint**

```http
GET /api/v1/customers/CUST-1001
```

### Expected Status

```text
200 OK
```

### Validation

Verify:

* Customer ID
* First name
* Last name
* Email
* Employment status
* Customer status

The response should contain the expected customer information.

---

# API-004 — Customer Not Found

**Endpoint**

```http
GET /api/v1/customers/CUST-9999
```

### Expected Status

```text
404 Not Found
```

### Expected Response

```json
{
  "errorCode": "CUSTOMER_NOT_FOUND",
  "message": "Customer not found"
}
```

---

# API-005 — Create Customer

**Endpoint**

```http
POST /api/v1/customers
```

### Request

```json
{
  "firstName": "Juan",
  "lastName": "Santos",
  "email": "juan.santos@example.com",
  "employmentStatus": "EMPLOYED"
}
```

### Expected Status

```text
201 Created
```

### Validation

* Customer is successfully created.
* Unique customer ID is returned.
* Email matches the submitted value.
* Customer status is set correctly.

---

# API-006 — Create Customer With Missing Required Field

### Request

```json
{
  "firstName": "Juan",
  "lastName": "Santos",
  "email": "juan.santos@example.com"
}
```

Employment status is intentionally omitted.

### Expected Status

```text
400 Bad Request
```

### Expected Behavior

The API should reject the request and identify the missing required field.

---

# API-007 — Create Loan Application

**Endpoint**

```http
POST /api/v1/loans
```

### Request

```json
{
  "customerId": "CUST-1001",
  "loanProduct": "PERSONAL",
  "requestedAmount": 100000,
  "termMonths": 24
}
```

### Expected Status

```text
201 Created
```

### Validation

* Loan ID is generated.
* Customer ID is correct.
* Requested amount is correct.
* Loan product is correct.
* Initial application status is correct.

---

# API-008 — Loan Amount Below Minimum

### Request

```json
{
  "customerId": "CUST-1001",
  "loanProduct": "PERSONAL",
  "requestedAmount": 49999,
  "termMonths": 24
}
```

### Expected Status

```text
400 Bad Request
```

### Expected Behavior

The API should reject the request because the requested amount is below the configured minimum.

---

# API-009 — Loan Amount Above Maximum

### Request

```json
{
  "customerId": "CUST-1001",
  "loanProduct": "PERSONAL",
  "requestedAmount": 500001,
  "termMonths": 24
}
```

### Expected Status

```text
400 Bad Request
```

### Expected Behavior

The API should reject the request because the requested amount exceeds the configured maximum.

---

# API-010 — Unauthorized Request

**Endpoint**

```http
GET /api/v1/customers/CUST-1001
```

Remove the Authorization header.

### Expected Status

```text
401 Unauthorized
```

### Expected Behavior

The API should reject the request because authentication credentials are missing.
