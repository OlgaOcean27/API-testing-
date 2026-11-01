### _API Test Cases — User API_
---
#### 1. Overview

This document contains test cases designed to verify the functionality of the User API of the Practice Software Testing demo application.

#### **Application:** Practice Software Testing  
#### **API Type:** REST API  
#### **Base URL:** `https://api.practicesoftwaretesting.com`  
#### **Testing Tool:** Postman  
#### **Documentation:** Swagger

### 2. Testing Scope:

_The testing scope includes the following API operations:_

- User Registration
- User Login
- Retrieving Current User Information
- Retrieving User by ID
- Updating User Information
- Partially Updating User Information
- Deleting a User

### 3. Test Design Techniques

_The following test design techniques are applied:_

- **Equivalence Partitioning:** Dividing input data into valid and invalid groups.
- **Boundary Value Analysis:** Checking values at and around input boundaries.
- **Error Guessing:** Designing tests based on common errors and potential failure points.
- **Positive Testing:** Verifying expected behavior with valid input data.
- **Negative Testing:** Verifying how the API handles invalid input or unauthorized requests.

### 4. Test Case Structure

_Each test case includes:_

- Test Case ID
- Title
- Priority
- Test Type
- Preconditions
- Test Data
- Test Steps
- Expected Result
- Actual Result
- Status

### 5. Test Execution Statuses

- **Not Run:** _The test case has not been executed._
- **Pass:** _Actual result matches the expected result._
- **Fail:** _Actual result differs from the expected result._
- **Blocked:** _Test execution cannot proceed because of a dependency or environment issue._

---
---
## 6. **Test Cases** :
---
---
### TC-001: User Management: Register a new user with valid data.
---
- **Priority:** High 
- **Type:** High  
- **Preconditions:**
 - 1. The test user has not been registered in the system.
 - 2. The Postman collection Practice Software Testing — User API is available.
 - 3. The Postman environment is configured with the API base URL: https://api.practicesoftwaretesting.com
 - 4. A unique email address is available for registration.

**Test Data:**
 1. Method: POST
 2. Endpoint: /users/register
 3. Authorization: No Auth
 4. Request Body: Valid user data in JSON format, according to the Swagger schema.
 5. Email: A unique email address that has not been registered previously.
 6. Swagger(User): https://api.practicesoftwaretesting.com/api/documentation?utm_source=chatgpt.com#/User/storeUser 

**Steps:**
- 1. Open the Postman collection.
- 2. Select the `Register New User request`.
- 3. Verify that the request URL is `{{baseURL}}/users/register`.
- 4. Set Authorization to `No Auth`.
- 5. Open the request `Body` tab and select `raw` and `JSON`. 
- 6. Add a valid `JSON` request body using the required fields specified in `Swagger`
- 7. Verify that the `Content-Type` header is set to `application/json`
- 8. Send the request
- 9. Review the response status code and response body.
      
**Expected Result:**
- 1. The API returns the successful HTTP status code specified in `Swagger`. 
- 2. The response confirms that the new user has been successfully registered.
- 3. The response body is returned in the expected format.
- 4. The registered user can subsequently be used in other User API test cases, where applicable."

**Actual Result:** 
- 1. The API returned HTTP status code `200` OK.
- 2. The response confirmed that the new user was successfully registered.
- 3. The response body was returned in `JSON` format.
- 4. The user was successfully created and can be used for subsequent API tests."

**Status:** PASS

---
---
### TC-002: xxx
---
- **Priority:** xxx 
- **Type:** xxx  
- **Preconditions:** xxx

**Test Data:**
- xxx
- xxx
- xxx

**Steps:**
1. xxx
2. xxx
3. xxx
4. xxx

**Expected Result:**
- xxx
- xxx
- xxx

**Actual Result:** xxx

**Status:** xxx

---
---
### TC-003: xxx
---
- **Priority:** xxx 
- **Type:** xxx  
- **Preconditions:** xxx

**Test Data:**
- xxx
- xxx
- xxx

**Steps:**
1. xxx
2. xxx
3. xxx
4. xxx

**Expected Result:**
- xxx
- xxx
- xxx

**Actual Result:** xxx

**Status:** xxx

---
---
### TC-004: xxx
---
- **Priority:** xxx 
- **Type:** xxx  
- **Preconditions:** xxx

**Test Data:**
- xxx
- xxx
- xxx

**Steps:**
1. xxx
2. xxx
3. xxx
4. xxx

**Expected Result:**
- xxx
- xxx
- xxx

**Actual Result:** xxx

**Status:** xxx

---
---
### TC-005: xxx
---
- **Priority:** xxx 
- **Type:** xxx  
- **Preconditions:** xxx

**Test Data:**
- xxx
- xxx
- xxx

**Steps:**
1. xxx
2. xxx
3. xxx
4. xxx

**Expected Result:**
- xxx
- xxx
- xxx

**Actual Result:** xxx

**Status:** xxx

---
---
### TC-006: xxx
---
- **Priority:** xxx 
- **Type:** xxx  
- **Preconditions:** xxx

**Test Data:**
- xxx
- xxx
- xxx

**Steps:**
1. xxx
2. xxx
3. xxx
4. xxx

**Expected Result:**
- xxx
- xxx
- xxx

**Actual Result:** xxx

**Status:** xxx

---
---
### TC-007: xxx
---
- **Priority:** xxx 
- **Type:** xxx  
- **Preconditions:** xxx

**Test Data:**
- xxx
- xxx
- xxx

**Steps:**
1. xxx
2. xxx
3. xxx
4. xxx

**Expected Result:**
- xxx
- xxx
- xxx

**Actual Result:** xxx

**Status:** xxx

---
---
### TC-008: xxx
---
- **Priority:** xxx 
- **Type:** xxx  
- **Preconditions:** xxx

**Test Data:**
- xxx
- xxx
- xxx

**Steps:**
1. xxx
2. xxx
3. xxx
4. xxx

**Expected Result:**
- xxx
- xxx
- xxx

**Actual Result:** xxx

**Status:** xxx

---
---
### TC-009: xxx
---
- **Priority:** xxx 
- **Type:** xxx  
- **Preconditions:** xxx

**Test Data:**
- xxx
- xxx
- xxx

**Steps:**
1. xxx
2. xxx
3. xxx
4. xxx

**Expected Result:**
- xxx
- xxx
- xxx

**Actual Result:** xxx

**Status:** xxx

---
---
### TC-010: xxx
---
- **Priority:** xxx 
- **Type:** xxx  
- **Preconditions:** xxx

**Test Data:**
- xxx
- xxx
- xxx

**Steps:**
1. xxx
2. xxx
3. xxx
4. xxx

**Expected Result:**
- xxx
- xxx
- xxx

**Actual Result:** xxx

**Status:** xxx

---
---
### TC-011: xxx
---
- **Priority:** xxx 
- **Type:** xxx  
- **Preconditions:** xxx

**Test Data:**
- xxx
- xxx
- xxx

**Steps:**
1. xxx
2. xxx
3. xxx
4. xxx

**Expected Result:**
- xxx
- xxx
- xxx

**Actual Result:** xxx

**Status:** xxx

---
---
### TC-012: xxx
---
- **Priority:** xxx 
- **Type:** xxx  
- **Preconditions:** xxx

**Test Data:**
- xxx
- xxx
- xxx

**Steps:**
1. xxx
2. xxx
3. xxx
4. xxx

**Expected Result:**
- xxx
- xxx
- xxx

**Actual Result:** xxx

**Status:** xxx

---
---
### TC-013: xxx
---
- **Priority:** xxx 
- **Type:** xxx  
- **Preconditions:** xxx

**Test Data:**
- xxx
- xxx
- xxx

**Steps:**
1. xxx
2. xxx
3. xxx
4. xxx

**Expected Result:**
- xxx
- xxx
- xxx

**Actual Result:** xxx

**Status:** xxx

---
---
### TC-014: xxx
---
- **Priority:** xxx 
- **Type:** xxx  
- **Preconditions:** xxx
  
**Test Data:**
- xxx
- xxx
- xxx

**Steps:**
1. xxx
2. xxx
3. xxx
4. xxx

**Expected Result:**
- xxx
- xxx
- xxx

**Actual Result:** xxx

**Status:** xxx

---
---
### TC-015: xxx
---
- **Priority:** xxx 
- **Type:** xxx  
- **Preconditions:** xxx

**Test Data:**
- xxx
- xxx
- xxx

**Steps:**
1. xxx
2. xxx
3. xxx
4. xxx

**Expected Result:**
- xxx
- xxx
- xxx

**Actual Result:** xxx

**Status:** xxx

---
---
### TC-016: xxx
---
- **Priority:** xxx 
- **Type:** xxx  
- **Preconditions:** xxx

**Test Data:**
- xxx
- xxx
- xxx

**Steps:**
1. xxx
2. xxx
3. xxx
4. xxx

**Expected Result:**
- xxx
- xxx
- xxx

**Actual Result:** xxx

**Status:** xxx

---
---
### TC-017: xxx
---
- **Priority:** xxx 
- **Type:** xxx  
- **Preconditions:** xxx

**Test Data:**
- xxx
- xxx
- xxx

**Steps:**
1. xxx
2. xxx
3. xxx
4. xxx

**Expected Result:**
- xxx
- xxx
- xxx

**Actual Result:** xxx

**Status:** xxx

---
---
### TC-018: xxx
---
- **Priority:** xxx 
- **Type:** xxx  
- **Preconditions:** xxx

**Test Data:**
- xxx
- xxx
- xxx

**Steps:**
1. xxx
2. xxx
3. xxx
4. xxx

**Expected Result:**
- xxx
- xxx
- xxx

**Actual Result:** xxx

**Status:** xxx

---
---
### TC-019: xxx
---
- **Priority:** xxx 
- **Type:** xxx  
- **Preconditions:** xxx

**Test Data:**
- xxx
- xxx
- xxx

**Steps:**
1. xxx
2. xxx
3. xxx
4. xxx

**Expected Result:**
- xxx
- xxx
- xxx

**Actual Result:** xxx

**Status:** xxx

---
---
### TC-020: xxx
---
- **Priority:** xxx 
- **Type:** xxx  
- **Preconditions:** xxx

**Test Data:**
- xxx
- xxx
- xxx

**Steps:**
1. xxx
2. xxx
3. xxx
4. xxx

**Expected Result:**
- xxx
- xxx
- xxx

**Actual Result:** xxx

**Status:** xxx

---
---
### TC-021: xxx
---
- **Priority:** xxx 
- **Type:** xxx  
- **Preconditions:** xxx

**Test Data:**
- xxx
- xxx
- xxx

**Steps:**
1. xxx
2. xxx
3. xxx
4. xxx

**Expected Result:**
- xxx
- xxx
- xxx

**Actual Result:** xxx

**Status:** xxx

---
---
### TC-022: xxx
---
- **Priority:** xxx 
- **Type:** xxx  
- **Preconditions:** xxx

**Test Data:**
- xxx
- xxx
- xxx

**Steps:**
1. xxx
2. xxx
3. xxx
4. xxx

**Expected Result:**
- xxx
- xxx
- xxx

**Actual Result:** xxx

**Status:** xxx

---
---
### TC-023: xxx
---
- **Priority:** xxx 
- **Type:** xxx  
- **Preconditions:** xxx

**Test Data:**
- xxx
- xxx
- xxx

**Steps:**
1. xxx
2. xxx
3. xxx
4. xxx

**Expected Result:**
- xxx
- xxx
- xxx

**Actual Result:** xxx

**Status:** xxx

---
---
### TC-024: xxx
---
- **Priority:** xxx 
- **Type:** xxx  
- **Preconditions:** xxx

**Test Data:**
- xxx
- xxx
- xxx

**Steps:**
1. xxx
2. xxx
3. xxx
4. xxx

**Expected Result:**
- xxx
- xxx
- xxx

**Actual Result:** xxx

**Status:** xxx

---
---
### TC-025: xxx
---
- **Priority:** xxx 
- **Type:** xxx  
- **Preconditions:** xxx

**Test Data:**
- xxx
- xxx
- xxx

**Steps:**
1. xxx
2. xxx
3. xxx
4. xxx

**Expected Result:**
- xxx
- xxx
- xxx

**Actual Result:** xxx

**Status:** xxx

---
---
### TC-026: xxx
---
- **Priority:** xxx 
- **Type:** xxx  
- **Preconditions:** xxx

**Test Data:**
- xxx
- xxx
- xxx

**Steps:**
1. xxx
2. xxx
3. xxx
4. xxx

**Expected Result:**
- xxx
- xxx
- xxx

**Actual Result:** xxx

**Status:** xxx

---
---
### TC-027: xxx
---
- **Priority:** xxx 
- **Type:** xxx  
- **Preconditions:** xxx

**Test Data:**
- xxx
- xxx
- xxx

**Steps:**
1. xxx
2. xxx
3. xxx
4. xxx

**Expected Result:**
- xxx
- xxx
- xxx

**Actual Result:** xxx

**Status:** xxx

---
---
### TC-028: xxx
---
- **Priority:** xxx 
- **Type:** xxx  
- **Preconditions:** xxx

**Test Data:**
- xxx
- xxx
- xxx

**Steps:**
1. xxx
2. xxx
3. xxx
4. xxx

**Expected Result:**
- xxx
- xxx
- xxx

**Actual Result:** xxx

**Status:** xxx

---
---
### TC-029: xxx
---
- **Priority:** xxx 
- **Type:** xxx  
- **Preconditions:** xxx

**Test Data:**
- xxx
- xxx
- xxx

**Steps:**
1. xxx
2. xxx
3. xxx
4. xxx

**Expected Result:**
- xxx
- xxx
- xxx

**Actual Result:** xxx

**Status:** xxx

---
---
### TC-030: xxx
---
- **Priority:** xxx 
- **Type:** xxx  
- **Preconditions:** xxx

**Test Data:**
- xxx
- xxx
- xxx

**Steps:**
1. xxx
2. xxx
3. xxx
4. xxx

**Expected Result:**
- xxx
- xxx
- xxx

**Actual Result:** xxx

**Status:** xxx

---
---
### TC-031: xxx
---
- **Priority:** xxx 
- **Type:** xxx  
- **Preconditions:** xxx

**Test Data:**
- xxx
- xxx
- xxx

**Steps:**
1. xxx
2. xxx
3. xxx
4. xxx

**Expected Result:**
- xxx
- xxx
- xxx

**Actual Result:** xxx

**Status:** xxx

---

