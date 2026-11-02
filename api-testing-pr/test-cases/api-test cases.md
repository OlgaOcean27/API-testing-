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
#  **Test Cases** :
---
---
### TC-001: User Management: Register a new user with valid data.
---
- **Priority:** _High_ 
- **Type:** _Positive_

**Preconditions:**
 1. The test user has not been registered in the system.
 2. The Postman collection Practice Software Testing — User API is available.
 3. The Postman environment is configured with the API base URL: `https://api.practicesoftwaretesting.com`
 4. A unique email address is available for registration.

**Test Data:**
 1. Method: POST
 2. Endpoint: /users/register
 3. Authorization: No Auth
 4. Request Body: Valid user data in JSON format, according to the Swagger schema.
 5. Email: A unique email address that has not been registered previously.
 6. Swagger(User): `https://api.practicesoftwaretesting.com/api/documentation?#/User/storeUser`

**Steps:**
 1. Open the Postman collection.
 2. Select the `Register New User request`.
 3. Verify that the request URL is `{{baseURL}}/users/register`.
 4. Set Authorization to `No Auth`.
 5. Open the request `Body` tab and select `raw` and `JSON`. 
 6. Add a valid `JSON` request body using the required fields specified in `Swagger`
 7. Verify that the `Content-Type` header is set to `application/json`
 8. Send the request
 9. Review the response status code and response body.
      
**Expected Result:**
 1. The API returns the successful HTTP status code specified in `Swagger`. 
 2. The response confirms that the new user has been successfully registered.
 3. The response body is returned in the expected format.
 4. The registered user can subsequently be used in other User API test cases, where applicable.

**Actual Result:** 
 1. The API returned HTTP status code `200` OK.
 2. The response confirmed that the new user was successfully registered.
 3. The response body was returned in `JSON` format.
 4. The user was successfully created and can be used for subsequent API tests.

**Status:** PASS

---
---
### TC-002: User Management: Register a new user with an empty `first_name`
---
- **Priority:** High 
- **Type:** Negative  
- **Preconditions:**
1. The test user has not been registered in the system.
2. The Postman collection Practice Software Testing — User API is available.
3. The Postman environment is configured with the API base URL: `https://api.practicesoftwaretesting.com`.
4. A unique email address is available for registration."

**Test Data:**
1. Method: POST
2. Endpoint: /users/register
3. Authorization: No Auth
4. Request Body: Valid user data in `JSON` format, according to the `Swagger` schema, with an empty `first_name` value.
5. Email: A unique email address that has not been registered previously.
6. Swagger(User): `https://api.practicesoftwaretesting.com/api/documentation?#/User/storeUser`.

**Steps:**
1. Open the Postman collection.
2. Select the `Register New User request`.
3.  Verify that the request URL is `{{baseURL}}/users/register`.
4. Set Authorization to `No Auth`.
5. Open the request `Body` tab and select `raw` and `JSON`. 
6. Add a valid `JSON` request body based on the required fields specified in `Swagger`. Set the `first_name` field to an empty string `("")`.
7. Verify that the `Content-Type` header is set to `application/json`.
8. Send the request.
9. Review the response status code and response body.

**Expected Result:**
1. The API rejects the registration request because the `first_name` field is empty.
2. The response confirms that the new user has not been successfully registered.
3. The API returns an appropriate validation error.

**Actual Result:** 
1. The API rejected the registration request because the `first_name` field is empty.
2. The API returned `422` status. [Unprocessable Content].
3. The response confirmed that the new user has not been successfully registered.

**Status:** PASS

---
---
### TC-003: User Management: Register a new user with an empty `last_name`
---
- **Priority:** High 
- **Type:** Negative  
- **Preconditions:**
1. The test user has not been registered in the system.
2. The Postman collection Practice Software Testing — User API is available.
3. The Postman environment is configured with the API base `URL: https://api.practicesoftwaretesting.com`.
4. A unique email address is available for registration.

**Test Data:**
1. Method: POST
2. Endpoint: /users/register
3. Authorization: No Auth
4. Request Body: Valid user data in `JSON` format, according to the `Swagger` schema, with an empty `last_name` value.
5. Email: A unique email address that has not been registered previously.
6. Swagger(User): `https://api.practicesoftwaretesting.com/api/documentation?#/User/storeUser`.

**Steps:**
1. Open the Postman collection.
2. Select the `Register New User request`.
3. Verify that the request URL is `{{baseURL}}/users/register`.
4. Set Authorization to `No Auth`.
5. Open the request `Body` tab and select `raw` and `JSON`. 
6. Add a valid `JSON` request body based on the required fields specified in `Swagger`. Set the `last_name` field to an empty string `("")`.
7. Verify that the `Content-Type` header is set to `application/json`.
8. Send the request.
9. Review the response status code and response body.

**Expected Result:**
1. The API rejects the registration request because the `last_name` field is empty.
2. The response confirms that the new user has not been successfully registered.
3. The API returns an appropriate validation error.

**Actual Result:** 
1. The API rejected the registration request because the `last_name` field is empty.
2. The API returned `422` status. [Unprocessable Content].
3. The response confirmed that the new user has not been successfully registered.

**Status:** PASS

---
---
### TC-004: User Management: Register a new user with a 40-character `first_name`.
---
- **Priority:** High 
- **Type:** Positive  
- **Preconditions:**
1. The test user has not been registered in the system.
2. The Postman collection Practice Software Testing – User API is available.
3. The Postman environment is configured with the API base URL: `https://api.practicesoftwaretesting.com`.
4. A unique email address is available for registration.

**Test Data:**
1. Method: POST
2. Endpoint: /users/register
3. Authorization: No Auth
4. Request Body: Valid user data in `JSON` format, according to the `Swagger` schema.
5. Email: A unique email address that has not been registered previously.
6. Swagger(User): `https://api.practicesoftwaretesting.com/api/documentation?#/User/storeUser`. 
7. `first_name`: A string containing exactly 40 characters.

**Steps:**
1. Open the Postman collection.
2. Select the `Register New User request`.
3. Verify that the request URL is `{{baseURL}}/users/register`.
4. Set Authorization to `No Auth`.
5. Open the request `Body` tab and select `raw` and `JSON`. 
6. Add a valid JSON request body based on the required fields specified in Swagger. Set the `first_name field` to a string containing exactly 40 characters.
7. Verify that the `Content-Type` header is set to `application/json`.
8. Send the request.
9. Review the response status code and response body.

**Expected Result:**
1. The API accepts the registration request, as the `first_name` field contains exactly 40 characters and does not exceed the permitted limit.
2. The response confirms that the new user has been successfully registered.
3. The API returns the expected successful HTTP status code.

**Actual Result:** 
1. The API accepted the registration request with a `first_name` value containing exactly 40 characters.
2. The API returned `200` status. 
3. The response confirmed that the new user has been successfully registered.

**Status:** PASS

---
---
### TC-005: User Management: Register a new user with a 41-character `first_name.
---
- **Priority:** High 
- **Type:** Negative  
- **Preconditions:**
1. The test user has not been registered in the system.
2. The Postman collection Practice Software Testing — User API is available.
3. The Postman environment is configured with the API base URL: `https://api.practicesoftwaretesting.com`.
4. A unique email address is available for registration.

**Test Data:**
1. Method: POST
2. Endpoint: /users/register
3. Authorization: No Auth
4. Request Body: Valid user data in `JSON` format, according to the `Swagger` schema.
5. Email: A unique email address that has not been registered previously.
6. Swagger(User): `https://api.practicesoftwaretesting.com/api/documentation?#/User/storeUser` 
7. `first_name`: A string containing exactly 41 characters.
   
**Steps:**
1. Open the Postman collection.
2. Select the `Register New User request`.
3. Verify that the request URL is `{{baseURL}}/users/register`.
4. Set Authorization to `No Auth`.
5. Open the request `Body` tab and select `raw` and `JSON`. 
6. Add a valid JSON request body based on the required fields specified in Swagger. Set the `first_name field` to a string containing exactly 41 characters.
7. Verify that the `Content-Type` header is set to `application/json`
8. Send the request
9. Review the response status code and response body.

**Expected Result:**
1. The API rejects the registration request because the `first_name` field exceeds the 40-character limit.
2. The response confirms that the new user has not been successfully registered.
3. The API returns the expected error HTTP status code.

**Actual Result:** 
1. The API rejected the registration request with a `first_name` value containing exactly 41 characters.
2. The API returned `422` error status. 
3. The response confirmed that the new user has not been successfully registered.

**Status:** PASS

---
---
### TC-006: User Management: Register a new user with a 39-character `first_name`
---
- **Priority:** High 
- **Type:** Positive  
- **Preconditions:**
1. The test user has not been registered in the system.
2. The Postman collection Practice Software Testing — User API is available.
3. The Postman environment is configured with the API base URL: `https://api.practicesoftwaretesting.com`
4. A unique email address is available for registration.

**Test Data:**
1. Method: POST
2. Endpoint: /users/register
3. Authorization: No Auth
4. Request Body: Valid user data in `JSON` format, according to the `Swagger` schema.
5. Email: A unique email address that has not been registered previously.
6. Swagger(User): `https://api.practicesoftwaretesting.com/api/documentation?#/User/storeUser`  
7. `first_name`: A string containing exactly 39 characters.

**Steps:**
1. Open the Postman collection.
2. Select the `Register New User request`.
3. Verify that the request URL is `{{baseURL}}/users/register`.
4. Set Authorization to `No Auth`.
5. Open the request `Body` tab and select `raw` and `JSON`. 
6. Add a valid JSON request body based on the required fields specified in Swagger. Set the `first_name field` to a string containing exactly 39 characters.
7. Verify that the `Content-Type` header is set to `application/json`
8. Send the request
9. Review the response status code and response body.

**Expected Result:**
1. The API accepts the registration request because the `first_name` field contains exactly 39 characters, which is within the allowed limit.
2. The response confirms that the new user has been successfully registered.
3. The API returns the expected successful HTTP status code.

**Actual Result:** 
1. The API accepted the registration request with a `first_name` value containing exactly 39 characters.
2. The API returned `200` status. 
3. The response confirmed that the new user has been successfully registered.

**Status:** PASS

---
---
### TC-007: User Management: Register a new user with a 1 character `first_name`
---
- **Priority:** High 
- **Type:** Positive  
- **Preconditions:**
1. The test user has not been registered in the system.
2. The Postman collection Practice Software Testing – User API is available.
3. The Postman environment is configured with the API base URL: `https://api.practicesoftwaretesting.com`
4. A unique email address is available for registration.

**Test Data:**
1. Method: POST
2. Endpoint: /users/register
3. Authorization: No Auth
4. Request Body: Valid user data in `JSON` format, according to the `Swagger` schema.
5. Email: A unique email address that has not been registered previously.
6. Swagger(User): `https://api.practicesoftwaretesting.com/api/documentation?#/User/storeUser`  
7. `first_name`: A string containing exactly 1 characters.

**Steps:**
1. Open the Postman collection.
2. Select the `Register New User request`.
3. Verify that the request URL is `{{baseURL}}/users/register`.
4. Set Authorization to `No Auth`.
5. Open the request `Body` tab and select `raw` and `JSON`. 
6. Add a valid JSON request body based on the required fields specified in Swagger. Set the `first_name field` to a string containing exactly 1 character.
7. Verify that the `Content-Type` header is set to `application/json`
8. Send the request
9. Review the response status code and response body.

**Expected Result:**
1. The API accepts the registration request because the `first_name` field contains exactly 1 character, which is within the allowed limit.
2. The response confirms that the new user has been successfully registered.
3. The API returns the expected successful HTTP status code.

**Actual Result:** 
1. The API accepted the registration request with a `first_name` value containing exactly 1 character.
2. The API returned `200` status. 
3. The response confirmed that the new user has been successfully registered.

**Status:** PASS

---
---
### TC-008: User Management: Register a new user with a first_name containing spaces
---
- **Priority:** High 
- **Type:** Positive  
- **Preconditions:**
1. The test user has not been registered in the system.
2. The Postman collection Practice Software Testing – User API is available.
3. The Postman environment is configured with the API base URL: `https://api.practicesoftwaretesting.com` 
4. A unique email address is available for registration.

**Test Data:**
1. Method: POST
2. Endpoint: /users/register
3. Authorization: No Auth
4. Request Body: Valid user data in `JSON` format, according to the `Swagger` schema.
5. Email: A unique email address that has not been registered previously.
6. Swagger(User): `https://api.practicesoftwaretesting.com/api/documentation?#/User/storeUser`  
7. The `first_name` field contains two or more name parts separated by a space. The total length does not exceed 40 characters.

**Steps:**
1. Open the Postman collection.
2. Select the `Register New User request`.
3. Verify that the request URL is `{{baseURL}}/users/register`.
4. Set Authorization to `No Auth`.
5. Open the request `Body` tab and select `raw` and `JSON`. 
6. Add a valid JSON request body based on the required fields specified in Swagger. Set the `first_name field` to a string containing two or more valid values ​​separated by spaces.
7. Verify that the `Content-Type` header is set to `application/json`
8. Send the request
9. Review the response status code and response body.

**Expected Result:**
1. The API accepts the registration request because the `first_name` field contains a name with two or more parts separated by a space, and the total length does not exceed 40 characters.
2. The response confirms that the new user has been successfully registered.
3. The API returns the expected successful HTTP status code.

**Actual Result:** 
1. The API accepted the registration request because the `first_name` field contains a name with two or more parts separated by a space, and the total length does not exceed 40 characters.
2. The API returned `200` status. 
3. The response confirmed that the new user has been successfully registered.

**Status:** PASS

---
---
### TC-009: User Management: Register a new user with a hyphenated `first_name`
---
- **Priority:** High 
- **Type:** Positive  
- **Preconditions:**
1. The test user has not been registered in the system.
2. The Postman collection Practice Software Testing – User API is available.
3. The Postman environment is configured with the API base URL: `https://api.practicesoftwaretesting.com` 
4. A unique email address is available for registration.

**Test Data:**
1. Method: POST
2. Endpoint: /users/register
3. Authorization: No Auth
4. Request Body: Valid user data in `JSON` format, according to the `Swagger` schema.
5. Email: A unique email address that has not been registered previously.
6. Swagger(User): `https://api.practicesoftwaretesting.com/api/documentation?#/User/storeUser` 
7. The `first_name` field contains two or more name parts separated by a hyphen. The total length does not exceed 40 characters.

**Steps:**
1. Open the Postman collection.
2. Select the `Register New User request`.
3. Verify that the request URL is `{{baseURL}}/users/register`.
4. Set Authorization to `No Auth`.
5. Open the request `Body` tab and select `raw` and `JSON`. 
6. Add a valid JSON request body based on the required fields specified in Swagger. Set the `first_name` field to a hyphenated name consisting of two name parts.
7. Verify that the `Content-Type` header is set to `application/json`
8. Send the request
9. Review the response status code and response body.

**Expected Result:**
1. The API accepts the registration request because the `first_name` field contains a hyphenated name, and the total length does not exceed 40 characters.
2. The response confirms that the new user has been successfully registered.
3. The API returns the expected successful HTTP status code.

**Actual Result:** 
1. The API accepted the registration request because the `first_name` field contains a hyphenated name, and the total length does not exceed 40 characters.
2. The API returned `200` status. 
3. The response confirmed that the new user has been successfully registered.

**Status:** PASS

---
---
### TC-010: User Management: Register a new user with a URL as the `first_name` value
---
- **Priority:** High 
- **Type:** Negative  
- **Preconditions:**
1. The test user has not been registered in the system.
2. The Postman collection Practice Software Testing – User API is available.
3. The Postman environment is configured with the API base URL: `https://api.practicesoftwaretesting.com` 
4. A unique email address is available for registration.

**Test Data:**
1. Method: POST
2. Endpoint: /users/register
3. Authorization: No Auth
4. Request Body: Valid user data in `JSON` format, according to the `Swagger` schema.
5. Email: A unique email address that has not been registered previously.
6. Swagger(User): `https://api.practicesoftwaretesting.com/api/documentation?#/User/storeUser`  
7. The `first_name` field contains a URL [example `https://www.youtube.com/` ]. The total length does not exceed 40 characters.

**Steps:**
1. Open the Postman collection.
2. Select the `Register New User request`.
3. Verify that the request URL is `{{baseURL}}/users/register`.
4. Set Authorization to `No Auth`.
5. Open the request `Body` tab and select `raw` and `JSON`. 
6. Add a valid JSON request body based on the required fields specified in Swagger. Set the `first_name` field to a URL value.
7. Verify that the `Content-Type` header is set to `application/json`
8. Send the request
9. Review the response status code and response body.

**Expected Result:**
1. The API rejects the registration request because the `first_name` field contains a `URL` instead of a person's name.
2. The response contains an appropriate validation error.

**Actual Result:** 
1. The API accepted the registration request with a URL in the `first_name` field.
2. The API returned HTTP `201` Created.
3. The response confirmed that the new user was successfully registered.

**Status:** _Fail_ – (potential validation issue based on a UX assumption; requirements not confirmed)

---
---
### TC-011: User Management: Register a new user with special characters in the `first_name` field
---
- **Priority:** High 
- **Type:** Negative  
- **Preconditions:**
1. The test user has not been registered in the system.
2. The Postman collection Practice Software Testing – User API is available.
3. The Postman environment is configured with the API base URL: `https://api.practicesoftwaretesting.com`
4. A unique email address is available for registration.

**Test Data:**
1. Method: POST
2. Endpoint: /users/register
3. Authorization: No Auth
4. Request Body: Valid user data in `JSON` format, according to the `Swagger` schema.
5. Email: A unique email address that has not been registered previously.
6. Swagger(User): `https://api.practicesoftwaretesting.com/api/documentation?#/User/storeUser`  
7. The `first_name` field contains special characters [example: `]\@±&~#` ]. The total length does not exceed 40 characters.

**Steps:**
1. Open the Postman collection.
2. Select the `Register New User request`.
3. Verify that the request URL is `{{baseURL}}/users/register`.
4. Set Authorization to `No Auth`.
5. Open the request `Body` tab and select `raw` and `JSON`. 
6. Add a valid JSON request body based on the required fields specified in Swagger. Set the `first_name` field to special symbols.
7. Verify that the `Content-Type` header is set to `application/json`
8. Send the request
9. Review the response status code and response body.

**Expected Result:**
1. The API rejects the registration request because the `first_name` field contains `special symbols` instead of a person's name.
2. The response contains an appropriate validation error.

**Actual Result:** 
1. The API accepted the registration request with special symbols in the `first_name` field.
2. The API returned HTTP `201` Created.
3. The response confirmed that the new user was successfully registered.

**Status:** _Fail_ – (potential validation issue based on a UX assumption; requirements not confirmed)

---
---
### TC-012: User Management: Register a new user with numbers in the `first_name` field
---
- **Priority:** High 
- **Type:** Negative  
- **Preconditions:**
1. The test user has not been registered in the system.
2. The Postman collection Practice Software Testing – User API is available.
3. The Postman environment is configured with the API base URL: `https://api.practicesoftwaretesting.com`
4. A unique email address is available for registration.

**Test Data:**
1. Method: POST
2. Endpoint: /users/register
3. Authorization: No Auth
4. Request Body: Valid user data in `JSON` format, according to the `Swagger` schema.
5. Email: A unique email address that has not been registered previously.
6. Swagger(User): `https://api.practicesoftwaretesting.com/api/documentation?#/User/storeUser`  
7. The `first_name` field contains only numeric characters (example: "12345"). The total length does not exceed 40 characters.

**Steps:**
1. Open the Postman collection.
2. Select the `Register New User request`.
3. Verify that the request URL is `{{baseURL}}/users/register`.
4. Set Authorization to `No Auth`.
5. Open the request `Body` tab and select `raw` and `JSON`. 
6. Add a valid JSON request body based on the required fields specified in Swagger. Set the `first_name` field to numeric characters.
7. Verify that the `Content-Type` header is set to `application/json`
8. Send the request
9. Review the response status code and response body.

**Expected Result:**
1. The API rejects the registration request because the `first_name` field contains numeric value instead of a person's name.
2. The response contains an appropriate validation error.

**Actual Result:** 
1. The API accepted the registration request with a numeric value in the `first_name` field.
2. The API returned HTTP `201` Created.
3. The response confirmed that the new user was successfully registered.

**Status:** _Fail_ – potential validation issue based on a UX assumption; requirements not confirmed)

---
---
### TC-013: User Management: Register a new user with Arabic characters in the `first_name` field
---
- **Priority:** Medium 
- **Type:** Positive  
- **Preconditions:**
1. The test user has not been registered in the system.
2. The Postman collection Practice Software Testing – User API is available.
3. The Postman environment is configured with the API base URL: `https://api.practicesoftwaretesting.com`
4. A unique email address is available for registration.

**Test Data:**
1. Method: POST
2. Endpoint: /users/register
3. Authorization: No Auth
4. Request Body: Valid user data in `JSON` format, according to the `Swagger` schema.
5. Email: A unique email address that has not been registered previously.
6. Swagger(User): `https://api.practicesoftwaretesting.com/api/documentation?#/User/storeUser`  
7. The `first_name` field contains only Arabic characters (e.g., "أحمد"). The total length does not exceed 40 characters. 

**Steps:**
1. Open the Postman collection.
2. Select the `Register New User request`.
3. Verify that the request URL is `{{baseURL}}/users/register`.
4. Set Authorization to `No Auth`.
5. Open the request `Body` tab and select `raw` and `JSON`. 
6. Add a valid JSON request body based on the required fields specified in Swagger. Set the `first_name` field to an Arabic name ("أحمد").
7. Verify that the `Content-Type` header is set to `application/json`
8. Send the request
9. Review the response status code and response body.

**Expected Result:**
1. The API accepts the registration request because the `first_name` field contains Arabic characters, and the total length does not exceed 40 characters.
2. The response confirms that the new user has been successfully registered.
3. The API returns the expected successful HTTP status code.

**Actual Result:** 
1. The API accepted the registration request because the `first_name` field contains Arabic characters, and the total length does not exceed 40 characters.
2. The response confirmed that the new user has been successfully registered.
3. The API returns the expected successful HTTP status code 201.

**Status:** PASS

---
---
### TC-014: User Management: Register a new user with Chinese characters in the `first_name` field
---
- **Priority:** Medium 
- **Type:** Positive  
- **Preconditions:**
1. The test user has not been registered in the system.
2. The Postman collection Practice Software Testing – User API is available.
3. The Postman environment is configured with the API base URL: `https://api.practicesoftwaretesting.com` 
4. A unique email address is available for registration.
  
**Test Data:**
1. Method: POST
2. Endpoint: /users/register
3. Authorization: No Auth
4. Request Body: Valid user data in `JSON` format, according to the `Swagger` schema.
5. Email: A unique email address that has not been registered previously.
6. Swagger(User): `https://api.practicesoftwaretesting.com/api/documentation?#/User/storeUser`    
7. The `first_name` field contains only Chinese characters (e.g., "张伟"). The total length does not exceed 40 characters.

**Steps:**
1. Open the Postman collection.
2. Select the `Register New User request`.
3. Verify that the request URL is `{{baseURL}}/users/register`.
4. Set Authorization to `No Auth`.
5. Open the request `Body` tab and select `raw` and `JSON`. 
6. 6. Add a valid JSON request body based on the required fields specified in Swagger. Set the `first_name` field to a Chinese name ("张伟").
7. Verify that the `Content-Type` header is set to `application/json`
8. Send the request
9. Review the response status code and response body.

**Expected Result:**
1. The API accepts the registration request because the `first_name` field contains Chinese characters, and the total length does not exceed 40 characters.
2. The response confirms that the new user has been successfully registered.
3. The API returns the expected successful HTTP status code.

**Actual Result:** 
1. The API accepted the registration request because the `first_name` field contains Chinese characters, and the total length does not exceed 40 characters.
2. The response confirmed that the new user has been successfully registered.
3. The API returned the expected successful HTTP status code 201.

**Status:** PASS

---
---
### TC-015: User Management: Register a new user with Hindi characters in the first_name field
---
- **Priority:** Medium 
- **Type:** Positive  
- **Preconditions:**
1. The test user has not been registered in the system.
2. The Postman collection Practice Software Testing – User API is available.
3. The Postman environment is configured with the API base URL: `https://api.practicesoftwaretesting.com` 
4. A unique email address is available for registration.

**Test Data:**
1. Method: POST
2. Endpoint: /users/register
3. Authorization: No Auth
4. Request Body: Valid user data in `JSON` format, according to the `Swagger` schema.
5. Email: A unique email address that has not been registered previously.
6. Swagger(User): `https://api.practicesoftwaretesting.com/api/documentation?#/User/storeUser`   
7. The `first_name` field contains only Hindi characters (example: "आरव"). The total length does not exceed 40 characters.

**Steps:**
1. Open the Postman collection.
2. Select the `Register New User request`.
3. Verify that the request URL is `{{baseURL}}/users/register`.
4. Set Authorization to `No Auth`.
5. Open the request `Body` tab and select `raw` and `JSON`. 
6. Add a valid JSON request body based on the required fields specified in Swagger. Set the `first_name` field to Hindi name ""आरव""
7. Verify that the `Content-Type` header is set to `application/json`
8. Send the request
9. Review the response status code and response body.

**Expected Result:**
1. The API accepts the registration request because the `first_name` field contains Hindi characters, and the total length does not exceed 40 characters.
2. The response confirms that the new user has been successfully registered.
3. The API returns the expected successful HTTP status code.

**Actual Result:** 
1. The API accepted the registration request because the `first_name` field contains Hindi characters, and the total length does not exceed 40 characters.
2. The response confirmed that the new user has been successfully registered.
3. The API returned the expected successful HTTP status code 201.

**Status:** PASS

---
---
### TC-016: User Management: Register a new user with Cyrillic characters in the first_name field
---
- **Priority:** Medium 
- **Type:** Positive  
- **Preconditions:**
1. The test user has not been registered in the system.
2. The Postman collection Practice Software Testing – User API is available.
3. The Postman environment is configured with the API base URL: `https://api.practicesoftwaretesting.com` 
4. A unique email address is available for registration.

**Test Data:**
1. Method: POST
2. Endpoint: /users/register
3. Authorization: No Auth
4. Request Body: Valid user data in `JSON` format, according to the `Swagger` schema.
5. Email: A unique email address that has not been registered previously.
6. Swagger(User): `https://api.practicesoftwaretesting.com/api/documentation?#/User/storeUser`    
7. The `first_name` field contains only Cyrillic characters (example: "Анна"). The total length does not exceed 40 characters.

**Steps:**
1. Open the Postman collection.
2. Select the `Register New User request`.
3. Verify that the request URL is `{{baseURL}}/users/register`.
4. Set Authorization to `No Auth`.
5. Open the request `Body` tab and select `raw` and `JSON`. 
6. Add a valid JSON request body based on the required fields specified in Swagger. Set the `first_name` field to Cyrillic name "Анна".
7. Verify that the `Content-Type` header is set to `application/json`
8. Send the request
9. Review the response status code and response body.

**Expected Result:**
1. The API accepts the registration request because the `first_name` field contains Cyrillic characters, and the total length does not exceed 40 characters.
2. The response confirms that the new user has been successfully registered.
3. The API returns the expected successful HTTP status code.

**Actual Result:** 
1. The API accepted the registration request because the `first_name` field contains Cyrillic characters, and the total length does not exceed 40 characters.
2. The response confirmed that the new user has been successfully registered.
3. The API returned the expected successful HTTP status code 201.

**Status:** PASS

---
---
### TC-017: User Management: Register a new user with a whitespace-only `first_name`
---
- **Priority:** Medium 
- **Type:** Negative  
- **Preconditions:**
1. The test user has not been registered in the system.
2. The Postman collection Practice Software Testing – User API is available.
3. The Postman environment is configured with the API base URL: `https://api.practicesoftwaretesting.com` 
4. A unique email address is available for registration.

**Test Data:**
1. Method: POST
2. Endpoint: /users/register
3. Authorization: No Auth
4. Request Body: Valid user data in JSON format, according to the Swagger schema.
5. Email: A unique email address that has not been registered previously.
6. The `first_name` field contains a single whitespace character (" ").
7. Swagger(User): `https://api.practicesoftwaretesting.com/api/documentation?#/User/storeUser`

**Steps:**
1. Open the Postman collection.
2. Select the Register New User request.
3. Verify that the request URL is `{{baseURL}}/users/register`.
4. Set Authorization to No Auth.
5. Open the request `Body` tab and select raw and `JSON`.
6. Add a valid `JSON` request body based on the required fields specified in `Swagger`. Set the `first_name` field to a single space ("" "").
7. Verify that the `Content-Type` header is set to `application/json`.
8. Send the request.
9. Review the response status code and response body.

**Expected Result:**
1. The API rejects the registration request because the `first_name` field contains only whitespace characters and does not contain a name.
2. The response contains an appropriate validation error.
3. The user is not registered.

**Actual Result:** 
1. The API rejected the registration request with a whitespace-only `first_name` value.
2. The API returned HTTP `422` Unprocessable Content.
3. The response contained a validation error.

**Status:** PASS

---
---
### TC-018: User Management: Register a new user with a 20-character `last_name`
---
- **Priority:** High 
- **Type:** Positive  
- **Preconditions:**
1. The test user has not been registered in the system.
2. The Postman collection Practice Software Testing – User API is available.
3. The Postman environment is configured with the API base URL: `https://api.practicesoftwaretesting.com` 
4. A unique email address is available for registration.

**Test Data:**
1. Method: POST
2. Endpoint: /users/register
3. Authorization: No Auth
4. Request Body: Valid user data in `JSON` format, according to the `Swagger` schema.
5. Email: A unique email address that has not been registered previously.
6. Swagger(User): `https://api.practicesoftwaretesting.com/api/documentation?#/User/storeUser` 
7. `last_name`: A string containing exactly 20 characters.

**Steps:**
1. Open the Postman collection.
2. Select the `Register New User request`.
3. Verify that the request URL is `{{baseURL}}/users/register`.
4. Set Authorization to `No Auth`.
5. Open the request `Body` tab and select `raw` and `JSON`. 
6. Add a valid JSON request body based on the required fields specified in Swagger. Set the `last_name field` to a string containing exactly 20 characters.
7. Verify that the `Content-Type` header is set to `application/json`
8. Send the request
9. Review the response status code and response body.

**Expected Result:**
1. The API accepts the registration request because the `last_name` field contains exactly 20 charactersand does not exceed the permitted limit.
2. The response confirms that the new user has been successfully registered.
3. The API returns the expected successful HTTP status code.

**Actual Result:** 
1. The API accepted the registration request with a `last_name` value containing exactly 20 characters.
2. The API returned `200` status. 
3. The response confirmed that the new user has been successfully registered.

**Status:** PASS

---
---
### TC-019: User Management: Register a new user with a 21-character `last_name`
---
- **Priority:** High 
- **Type:** Negative  
- **Preconditions:**
1. The test user has not been registered in the system.
2. The Postman collection Practice Software Testing – User API is available.
3. The Postman environment is configured with the API base URL: `https://api.practicesoftwaretesting.com`
4. A unique email address is available for registration.

**Test Data:**
1. Method: POST
2. Endpoint: /users/register
3. Authorization: No Auth
4. Request Body: Valid user data in `JSON` format, according to the `Swagger` schema.
5. Email: A unique email address that has not been registered previously.
6. Swagger(User): `https://api.practicesoftwaretesting.com/api/documentation?#/User/storeUser` 
7. `last_name`: A string containing exactly 21 characters.

**Steps:**
1. Open the Postman collection.
2. Select the `Register New User request`.
3. Verify that the request URL is `{{baseURL}}/users/register`.
4. Set Authorization to `No Auth`.
5. Open the request `Body` tab and select `raw` and `JSON`. 
6. Add a valid JSON request body based on the required fields specified in Swagger. Set the `last_name` field to a string containing exactly 21 characters.
7. Verify that the `Content-Type` header is set to `application/json`
8. Send the request
9. Review the response status code and response body.

**Expected Result:**
1. The API rejects the registration request because the `first_name` field exceeds the 20-character limit.
2. The response confirms that the new user has not been successfully registered.
3. The API returns the expected error HTTP status code.

**Actual Result:** 
1. The API rejected the registration request with a `last_name` value containing exactly 21 characters.
2. The API returned `422` error status. 
3. The response confirmed that the new user has not been successfully registered.

**Status:** PASS

---
---
### TC-020: User Management: Register a new user with a 19-character `last_name`
---
- **Priority:** High 
- **Type:** Positive  
- **Preconditions:**
1. The test user has not been registered in the system.
2. The Postman collection Practice Software Testing – User API is available.
3. The Postman environment is configured with the API base URL: `https://api.practicesoftwaretesting.com`
4. A unique email address is available for registration.

**Test Data:**
1. Method: POST
2. Endpoint: /users/register
3. Authorization: No Auth
4. Request Body: Valid user data in `JSON` format, according to the `Swagger` schema.
5. Email: A unique email address that has not been registered previously.
6. Swagger(User): `https://api.practicesoftwaretesting.com/api/documentation?#/User/storeUser`  
7. `last_name`: A string containing exactly 19 characters.

**Steps:**
1. Open the Postman collection.
2. Select the `Register New User request`.
3. Verify that the request URL is `{{baseURL}}/users/register`.
4. Set Authorization to `No Auth`.
5. Open the request `Body` tab and select `raw` and `JSON`. 
6. Add a valid JSON request body based on the required fields specified in Swagger. Set the `last_name` field to a string containing exactly 19 characters.
7. Verify that the `Content-Type` header is set to `application/json`
8. Send the request
9. Review the response status code and response body.

**Expected Result:**
1. The API accepts the registration request because the `last_name` field contains exactly 19 characters, which is within the allowed limit.
2. The response confirms that the new user has been successfully registered.
3. The API returns the expected successful HTTP status code.

**Actual Result:** 
1. The API accepted the registration request with a `last_name` value containing exactly 19 characters.
2. The API returned `200` status. 
3. The response confirmed that the new user has been successfully registered.

**Status:** PASS

---
---
### TC-021: User Management: Register a new user with a 1 character `last_name`
---
- **Priority:** High 
- **Type:** Positive  
- **Preconditions:**
1. The test user has not been registered in the system.
2. The Postman collection Practice Software Testing – User API is available.
3. The Postman environment is configured with the API base URL: `https://api.practicesoftwaretesting.com`
4. A unique email address is available for registration.
  
**Test Data:**
1. Method: POST
2. Endpoint: /users/register
3. Authorization: No Auth
4. Request Body: Valid user data in `JSON` format, according to the `Swagger` schema.
5. Email: A unique email address that has not been registered previously.
6. Swagger(User): `https://api.practicesoftwaretesting.com/api/documentation?#/User/storeUser`  
7. `last_name`: A string containing exactly 1 characters.

**Steps:**
1. Open the Postman collection.
2. Select the `Register New User request`.
3. Verify that the request URL is `{{baseURL}}/users/register`.
4. Set Authorization to `No Auth`.
5. Open the request `Body` tab and select `raw` and `JSON`. 
6. Add a valid JSON request body based on the required fields specified in Swagger. Set the `last_name` field to a string containing exactly 1 character.
7. Verify that the `Content-Type` header is set to `application/json`
8. Send the request
9. Review the response status code and response body.

**Expected Result:**
1. The API accepts the registration request because the `last_name` field contains exactly 1 character, which is within the allowed limit.
2. The response confirms that the new user has been successfully registered.
3. The API returns the expected successful HTTP status code.

**Actual Result:** 
1. The API accepted the registration request with a `last_name` value containing exactly 1 character.
2. The API returned `200` status. 
3. The response confirmed that the new user has been successfully registered.

**Status:** PASS

---
---
### TC-022: User Management: Register a new user with a `last_name` containing spaces
---
- **Priority:** High 
- **Type:** Positive  
- **Preconditions:**
1. The test user has not been registered in the system.
2. The Postman collection Practice Software Testing – User API is available.
3. The Postman environment is configured with the API base URL: `https://api.practicesoftwaretesting.com` 
4. A unique email address is available for registration.

**Test Data:**
1. Method: POST
2. Endpoint: /users/register
3. Authorization: No Auth
4. Request Body: Valid user data in `JSON` format, according to the `Swagger` schema.
5. Email: A unique email address that has not been registered previously.
6. Swagger(User): `https://api.practicesoftwaretesting.com/api/documentation?#/User/storeUser`  
7. The `last_name` field contains two or more name parts separated by a space. The total length does not exceed 20 characters.

**Steps:**
1. Open the Postman collection.
2. Select the `Register New User request`.
3. Verify that the request URL is `{{baseURL}}/users/register`.
4. Set Authorization to `No Auth`.
5. Open the request `Body` tab and select `raw` and `JSON`. 
6. Add a valid JSON request body based on the required fields specified in Swagger. Set the `last_name` field to a string containing two or more valid values ​​separated by spaces.
7. Verify that the `Content-Type` header is set to `application/json`
8. Send the request
9. Review the response status code and response body.

**Expected Result:**
1. The API accepts the registration request because the `last_name` field contains a last name with two or more parts separated by a space, and the total length does not exceed 20 characters.
2. The response confirms that the new user has been successfully registered.
3. The API returns the expected successful HTTP status code.

**Actual Result:**
1. The API accepted the registration request because the `last_name` field contains a last name with two or more parts separated by a space, and the total length does not exceed 20 characters.
2. The API returned `200` status. 
3. The response confirmed that the new user has been successfully registered.

**Status:** PASS

---
---
### TC-023: User Management: Register a new user with a hyphenated `last_name`
---
- **Priority:** High 
- **Type:** Positive  
- **Preconditions:**
1. The test user has not been registered in the system.
2. The Postman collection Practice Software Testing – User API is available.
3. The Postman environment is configured with the API base URL: `https://api.practicesoftwaretesting.com` 
4. A unique email address is available for registration.

**Test Data:**
1. Method: POST
2. Endpoint: /users/register
3. Authorization: No Auth
4. Request Body: Valid user data in `JSON` format, according to the `Swagger` schema.
5. Email: A unique email address that has not been registered previously.
6. Swagger(User): `https://api.practicesoftwaretesting.com/api/documentation?#/User/storeUser` 
7. The `last_name` field contains two or more name parts separated by a hyphen. The total length does not exceed 20 characters.

**Steps:**
1. Open the Postman collection.
2. Select the `Register New User request`.
3. Verify that the request URL is `{{baseURL}}/users/register`.
4. Set Authorization to `No Auth`.
5. Open the request `Body` tab and select `raw` and `JSON`. 
6. Add a valid JSON request body based on the required fields specified in Swagger. Set the `last_name` field to a hyphenated name consisting of two name parts.
7. Verify that the `Content-Type` header is set to `application/json`
8. Send the request
9. Review the response status code and response body.

**Expected Result:**
1. The API accepts the registration request because the `last_name` field contains a hyphenated last name, and the total length does not exceed 20 characters.
2. The response confirms that the new user has been successfully registered.
3. The API returns the expected successful HTTP status code.

**Actual Result:** 
1. The API accepted the registration request because the `last_name` field contains a hyphenated last name, and the total length does not exceed 20 characters.
2. The API returned `200` status. 
3. The response confirmed that the new user has been successfully registered.

**Status:** PASS

---
---
### TC-024: User Management: Register a new user with a URL as the `last_name` value
---
- **Priority:** High 
- **Type:** Negative  
- **Preconditions:**
1. The test user has not been registered in the system.
2. The Postman collection Practice Software Testing – User API is available.
3. The Postman environment is configured with the API base URL: `https://api.practicesoftwaretesting.com` 
4. A unique email address is available for registration.

**Test Data:**
1. Method: POST
2. Endpoint: /users/register
3. Authorization: No Auth
4. Request Body: Valid user data in `JSON` format, according to the `Swagger` schema.
5. Email: A unique email address that has not been registered previously.
6. Swagger(User): `https://api.practicesoftwaretesting.com/api/documentation?#/User/storeUser`  
7. The `last_name` field contains a URL [example `https://tinyurl.com` ]. The total length does not exceed 20 characters.

**Steps:**
1. Open the Postman collection.
2. Select the `Register New User request`.
3. Verify that the request URL is `{{baseURL}}/users/register`.
4. Set Authorization to `No Auth`.
5. Open the request `Body` tab and select `raw` and `JSON`. 
6. Add a valid JSON request body based on the required fields specified in Swagger. Set the `last_name` field to a URL value.
7. Verify that the `Content-Type` header is set to `application/json`
8. Send the request
9. Review the response status code and response body.

**Expected Result:**
1. The API rejects the registration request because the `last_name` field contains a `URL` instead of a person's last name.
2. The response contains an appropriate validation error.

**Actual Result:** 
1. The API accepted the registration request with a URL in the `last_name` field.
2. The API returned HTTP `201` Created.
3. The response confirmed that the new user was successfully registered.

**Status:** _Fail_ (potential validation issue based on a UX assumption; requirements not confirmed)

---
---
### TC-025: User Management: Register a new user with special characters in the `last_name` field
---
- **Priority:** High 
- **Type:** Negative  
- **Preconditions:**
1. The test user has not been registered in the system.
2. The Postman collection Practice Software Testing – User API is available.
3. The Postman environment is configured with the API base URL: `https://api.practicesoftwaretesting.com`
4. A unique email address is available for registration.

**Test Data:**
1. Method: POST
2. Endpoint: /users/register
3. Authorization: No Auth
4. Request Body: Valid user data in `JSON` format, according to the `Swagger` schema.
5. Email: A unique email address that has not been registered previously.
6. Swagger(User): `https://api.practicesoftwaretesting.com/api/documentation?#/User/storeUser`  
7. The `last_name` field contains special characters [example: `]\@±&~#`  ]. The total length does not exceed 20 characters.

**Steps:**
1. Open the Postman collection.
2. Select the `Register New User request`.
3. Verify that the request URL is `{{baseURL}}/users/register`.
4. Set Authorization to `No Auth`.
5. Open the request `Body` tab and select `raw` and `JSON`. 
6. Add a valid JSON request body based on the required fields specified in Swagger. Set the `last_name` field to special symbols.
7. Verify that the `Content-Type` header is set to `application/json`
8. Send the request
9. Review the response status code and response body.

**Expected Result:**
1. The API rejects the registration request because the `last_name` field contains `special symbols` instead of a person's last name.
2. The response contains an appropriate validation error.

**Actual Result:** 
1. The API accepted the registration request with special symbols in the `last_name` field.
2. The API returned HTTP `201` Created.
3. The response confirmed that the new user was successfully registered.

**Status:** _Fail_ (potential validation issue based on a UX assumption; requirements not confirmed)

---
---
### TC-026: User Management: Register a new user with numbers in the `last_name` field
---
- **Priority:** High 
- **Type:** Negative  
- **Preconditions:**
1. The test user has not been registered in the system.
2. The Postman collection Practice Software Testing – User API is available.
3. The Postman environment is configured with the API base URL: `https://api.practicesoftwaretesting.com` 
4. A unique email address is available for registration.

**Test Data:**
1. Method: POST
2. Endpoint: /users/register
3. Authorization: No Auth
4. Request Body: Valid user data in `JSON` format, according to the `Swagger` schema.
5. Email: A unique email address that has not been registered previously.
6. Swagger(User): `https://api.practicesoftwaretesting.com/api/documentation?#/User/storeUser`  
7. The `last_name` field contains only numeric characters (example: "12345"). The total length does not exceed 20 characters.

**Steps:**
1. Open the Postman collection.
2. Select the `Register New User request`.
3. Verify that the request URL is `{{baseURL}}/users/register`.
4. Set Authorization to `No Auth`.
5. Open the request `Body` tab and select `raw` and `JSON`. 
6. Add a valid JSON request body based on the required fields specified in Swagger. Set the `last_name` field to numeric characters.
7. Verify that the `Content-Type` header is set to `application/json`
8. Send the request
9. Review the response status code and response body.

**Expected Result:**
1. The API rejects the registration request because the `last_name` field contains numeric value instead of a person's last name.
2. The response contains an appropriate validation error.

**Actual Result:** 
1. The API accepted the registration request with a numeric value in the `last_name` field.
2. The API returned HTTP `201` Created.
3. The response confirmed that the new user was successfully registered.

**Status:** _Fail_ (potential validation issue based on a UX assumption; requirements not confirmed)

---
---
### TC-027: User Management: Register a new user with Arabic characters in the `last_name` field
---
- **Priority:** Medium 
- **Type:** Positive  
- **Preconditions:**
1. The test user has not been registered in the system.
2. The Postman collection Practice Software Testing – User API is available.
3. The Postman environment is configured with the API base URL: `https://api.practicesoftwaretesting.com` 
4. A unique email address is available for registration.

**Test Data:**
1. Method: POST
2. Endpoint: /users/register
3. Authorization: No Auth
4. Request Body: Valid user data in `JSON` format, according to the `Swagger` schema.
5. Email: A unique email address that has not been registered previously.
6. Swagger(User): `https://api.practicesoftwaretesting.com/api/documentation?#/User/storeUser`    
7. The `last_name` field contains only Arabic characters (e.g., "محمد"). The total length does not exceed 20 characters. 

**Steps:**
1. Open the Postman collection.
2. Select the `Register New User request`.
3. Verify that the request URL is `{{baseURL}}/users/register`.
4. Set Authorization to `No Auth`.
5. Open the request `Body` tab and select `raw` and `JSON`. 
6. Add a valid JSON request body based on the required fields specified in Swagger. Set the `last_name` field to an Arabic name ("محمد").
7. Verify that the `Content-Type` header is set to `application/json`
8. Send the request
9. Review the response status code and response body.

**Expected Result:**
1. The API accepts the registration request because the `last_name` field contains Arabic characters, and the total length does not exceed 20 characters.
2. The response confirms that the new user has been successfully registered.
3. The API returns the expected successful HTTP status code.

**Actual Result:** 
1. The API accepted the registration request because the `last_name` field contains Arabic characters, and the total length does not exceed 20 characters.
2. The response confirmed that the new user has been successfully registered.
3. The API returns the expected successful HTTP status code 201.

**Status:** PASS

---
---
### TC-028: User Management: Register a new user with Chinese characters in the `last_name` field
---
- **Priority:** Medium 
- **Type:** Positive  
- **Preconditions:**
1. The test user has not been registered in the system. 
2. The Postman collection Practice Software Testing – User API is available.
3. The Postman environment is configured with the API base URL: `https://api.practicesoftwaretesting.com` 
4. A unique email address is available for registration.

**Test Data:**
1. Method: POST
2. Endpoint: /users/register 
3. Authorization: No Auth
4. Request Body: Valid user data in `JSON` format, according to the `Swagger` schema.
5. Email: A unique email address that has not been registered previously.
6. Swagger(User): `https://api.practicesoftwaretesting.com/api/documentation?#/User/storeUser`    
7. The `last_name` field contains only Chinese characters (e.g., "张"). The total length does not exceed 20 characters.

**Steps:**
1. Open the Postman collection.
2. Select the `Register New User request`.
3. Verify that the request URL is `{{baseURL}}/users/register`.
4. Set Authorization to `No Auth`.
5. Open the request `Body` tab and select `raw` and `JSON`. 
6. 6. Add a valid JSON request body based on the required fields specified in Swagger. Set the `last_name` field to a Chinese last name ("张").
7. Verify that the `Content-Type` header is set to `application/json`
8. Send the request
9. Review the response status code and response body.

**Expected Result:**
1. The API accepts the registration request because the `last_name` field contains Chinese characters, and the total length does not exceed 20 characters.
2. The response confirms that the new user has been successfully registered.
3. The API returns the expected successful HTTP status code.

**Actual Result:** 
1. The API accepted the registration request because the `last_name` field contains Chinese characters, and the total length does not exceed 20 characters.
2. The response confirmed that the new user has been successfully registered.
3. The API returned the expected successful HTTP status code 201.

**Status:** PASS

---
---
### TC-029: User Management: Register a new user with Hindi characters in the `last_name` field
---
- **Priority:** Medium 
- **Type:** Positive  
- **Preconditions:**
1. The test user has not been registered in the system.
2. The Postman collection Practice Software Testing – User API is available.
3. The Postman environment is configured with the API base URL: `https://api.practicesoftwaretesting.com` 
4. A unique email address is available for registration.

**Test Data:**
1. Method: POST
2. Endpoint: /users/register
3. Authorization: No Auth
4. Request Body: Valid user data in `JSON` format, according to the `Swagger` schema.
5. Email: A unique email address that has not been registered previously.
6. Swagger(User): `https://api.practicesoftwaretesting.com/api/documentation?#/User/storeUser`   
7. The `last_name` field contains only Hindi characters (example: "शर्मा"). The total length does not exceed 20 characters.

**Steps:**
1. Open the Postman collection.
2. Select the `Register New User request`.
3. Verify that the request URL is `{{baseURL}}/users/register`.
4. Set Authorization to `No Auth`.
5. Open the request `Body` tab and select `raw` and `JSON`. 
6. Add a valid JSON request body based on the required fields specified in Swagger. Set the `last_name` field to Hindi last name "शर्मा"
7. Verify that the `Content-Type` header is set to `application/json`
8. Send the request
9. Review the response status code and response body.

**Expected Result:**
1. The API accepts the registration request because the `last_name` field contains Hindi characters, and the total length does not exceed 20 characters.
2. The response confirms that the new user has been successfully registered.
3. The API returns the expected successful HTTP status code.

**Actual Result:** 
1. The API accepted the registration request because the `last_name` field contains Hindi characters, and the total length does not exceed 20 characters.
2. The response confirmed that the new user has been successfully registered.
3. The API returned the expected successful HTTP status code 201.

**Status:** PASS

---
---
### TC-030: User Management: Register a new user with Cyrillic characters in the `last_name` field
---
- **Priority:** Medium 
- **Type:** Positive  
- **Preconditions:**
1. The test user has not been registered in the system.
2. The Postman collection Practice Software Testing – User API is available.
3. The Postman environment is configured with the API base URL: `https://api.practicesoftwaretesting.com` 
4. A unique email address is available for registration.

**Test Data:**
1. Method: POST
2. Endpoint: /users/register
3. Authorization: No Auth
4. Request Body: Valid user data in `JSON` format, according to the `Swagger` schema.
5. Email: A unique email address that has not been registered previously.
6. Swagger(User): `https://api.practicesoftwaretesting.com/api/documentation?#/User/storeUser`    
7. The `last_name` field contains only Cyrillic characters (example: "Иванова"). The total length does not exceed 20 characters.

**Steps:**
1. Open the Postman collection.
2. Select the `Register New User request`.
3. Verify that the request URL is `{{baseURL}}/users/register`.
4. Set Authorization to `No Auth`.
5. Open the request `Body` tab and select `raw` and `JSON`. 
6. Add a valid JSON request body based on the required fields specified in Swagger. Set the `last_name` field to Cyrillic last name "Иванова".
7. Verify that the `Content-Type` header is set to `application/json`
8. Send the request
9. Review the response status code and response body.

**Expected Result:**
1. The API accepts the registration request because the `last_name` field contains Cyrillic characters, and the total length does not exceed 20 characters.
2. The response confirms that the new user has been successfully registered.
3. The API returns the expected successful HTTP status code.

**Actual Result:** 
1. The API accepted the registration request because the `last_name` field contains Cyrillic characters, and the total length does not exceed 20 characters.
2. The response confirmed that the new user has been successfully registered.
3. The API returned the expected successful HTTP status code 201.

**Status:** PASS

---
---
### TC-031: User Management: Register a new user with a whitespace-only last_name
---
- **Priority:** Medium 
- **Type:** Negative  
- **Preconditions:**
1. The test user has not been registered in the system.
2. The Postman collection Practice Software Testing – User API is available.
3. The Postman environment is configured with the API base URL: `https://api.practicesoftwaretesting.com` 
4. A unique email address is available for registration. 

**Test Data:**
1. Method: POST
2. Endpoint: /users/register 
3. Authorization: No Auth
4. Request Body: Valid user data in JSON format, according to the Swagger schema.
5. Email: A unique email address that has not been registered previously.
6. The `last_name` field contains a single whitespace character (" ").
7. Swagger(User): `https://api.practicesoftwaretesting.com/api/documentation?#/User/storeUser`   

**Steps:**
1. Open the Postman collection.
2. Select the Register New User request.
3. Verify that the request URL is `{{baseURL}}/users/register`.
4. Set Authorization to No Auth.
5. Open the request `Body` tab and select raw and `JSON`.
6. Add a valid `JSON` request body based on the required fields specified in `Swagger`. Set the `last_name` field to a single space ("" "").
7. Verify that the `Content-Type` header is set to `application/json`.
8. Send the request.
9. Review the response status code and response body.

**Expected Result:**
1. The API rejects the registration request because the `last_name` field contains only whitespace characters and does not contain a last name.
2. The response contains an appropriate validation error.
3. The user is not registered.

**Actual Result:** 
1. The API rejected the registration request with a whitespace-only `last_name` value.
2. The API returned HTTP `422` Unprocessable Content.
3. The response contained a validation error.

**Status:** PASS

---

