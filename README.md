# GrowAI Postman API Automation Project

## Project Overview
This project contains API automation test cases created using Postman for validating Login functionality using the ReqRes API.

Base URL:
https://reqres.in

---

## Technologies Used
- Postman
- JavaScript (Postman Test Scripts)
- REST API Testing
- JSON

---

## Collection Name
GrowAI_Postman_Project

---

## Test Scenarios Covered

### 1. Valid Login
- Verify successful login with valid credentials
- Validate status code is 200
- Validate token is returned

### 2. Invalid Login
- Verify login with invalid credentials
- Validate status code is 400
- Validate error message

### 3. Missing Password
- Verify login without password
- Validate status code is 400
- Validate error message "Missing password"

### 4. Missing Email
- Verify login without email
- Validate status code is 400
- Validate error message

---

## Environment Variables Used

| Variable Name | Value |
|---|---|
| base_url | https://reqres.in |
| Valid_email | eve.holt@reqres.in |
| Valid_password | cityslicka |
| Invalid_email | wrong.email@reqres.in |
| Invalid_password | wrongpassword |

---

## Request URL

```text
{{base_url}}/api/login
```

---

## Sample Request Body

### Valid Login
```json
{
  "email": "{{Valid_email}}",
  "password": "{{Valid_password}}"
}
```

### Invalid Login
```json
{
  "email": "{{Invalid_email}}",
  "password": "{{Invalid_password}}"
}
```

---

## Assertions Used

### Status Code Validation
```javascript
pm.response.to.have.status(200);
```

```javascript
pm.response.to.have.status(400);
```

### Response Validation
```javascript
pm.expect(jsonData.token).to.eql("QpwL5tke4Pnpja7X4");
```

```javascript
pm.expect(jsonData.error).to.eql("user not found");
```

---

## Notes
- Some API responses from ReqRes differ from the expected project requirement.
- Example:
  - Expected: "invalid credentials"
  - Actual API Response: "user not found"

---

## How to Run the Project

1. Open Postman
2. Import Collection JSON file
3. Create Environment Variables
4. Select Environment
5. Open Request
6. Click Send
7. Verify Test Results

---

## Author
Snehal Manjarekar