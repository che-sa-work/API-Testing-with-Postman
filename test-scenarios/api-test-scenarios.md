# API Test Scenarios

## Online Loan Application API

| ID         | Endpoint       | Scenario                                              | Type       | Priority |
| ---------- | -------------- | ----------------------------------------------------- | ---------- | -------- |
| API-TS-001 | Login          | Verify user can authenticate with valid credentials   | Positive   | Critical |
| API-TS-002 | Login          | Verify invalid credentials are rejected               | Negative   | High     |
| API-TS-003 | Login          | Verify missing username is rejected                   | Negative   | High     |
| API-TS-004 | Login          | Verify missing password is rejected                   | Negative   | High     |
| API-TS-005 | Customer       | Retrieve existing customer                            | Positive   | High     |
| API-TS-006 | Customer       | Retrieve non-existing customer                        | Negative   | Medium   |
| API-TS-007 | Customer       | Create customer with valid information                | Positive   | High     |
| API-TS-008 | Customer       | Create customer with missing required fields          | Negative   | High     |
| API-TS-009 | Customer       | Create customer with duplicate email                  | Negative   | High     |
| API-TS-010 | Loan           | Create loan application with valid data               | Positive   | Critical |
| API-TS-011 | Loan           | Create loan application with missing required fields  | Negative   | High     |
| API-TS-012 | Loan           | Create loan with amount below minimum                 | Boundary   | High     |
| API-TS-013 | Loan           | Create loan with amount above maximum                 | Boundary   | High     |
| API-TS-014 | Loan           | Retrieve existing loan application                    | Positive   | High     |
| API-TS-015 | Loan           | Retrieve non-existing loan application                | Negative   | Medium   |
| API-TS-016 | Loan           | Update existing loan application                      | Positive   | High     |
| API-TS-017 | Loan           | Update loan with invalid data                         | Negative   | High     |
| API-TS-018 | Loan           | Update non-existing loan                              | Negative   | Medium   |
| API-TS-019 | Loan           | Cancel an existing loan application                   | Positive   | High     |
| API-TS-020 | Authentication | Request protected endpoint without token              | Negative   | Critical |
| API-TS-021 | Authentication | Request protected endpoint with expired token         | Negative   | High     |
| API-TS-022 | Validation     | Verify invalid data type is rejected                  | Negative   | Medium   |
| API-TS-023 | Validation     | Verify unsupported loan product is rejected           | Negative   | Medium   |
| API-TS-024 | Error Handling | Verify API returns appropriate error response         | Negative   | High     |
| API-TS-025 | Regression     | Verify previously working endpoints after API changes | Regression | Critical |
