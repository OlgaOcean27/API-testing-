## **API BR-004**: [PATCH] Password is not updated although the request returns 200 OK
---
#### _Description:_
---
##### – The `PATCH /users/{userId}` endpoint returns `200 OK` and a success response when a request containing a new password is submitted. However, the password does not appear to be updated.
– ##### The email address is updated successfully, but the user can still log in using the previous password. Authentication with the new password returns `401 Unauthorized`.
– ##### This behavior may indicate an inconsistency between the documented request schema and the actual endpoint behavior.
---
#### _Environment:_
---
- **Application:** Practice Software Testing
- **API Base URL:** `https://api.practicesoftwaretesting.com`
- **Tool:** Postman
- **Endpoint:** `PATCH /users/{userId}`
- OS: macOS 14.6
- Swagger: `https://api.practicesoftwaretesting.com/api/documentation?utm_source=chatgpt.com#/User`
---
### Severity: **Major** (provisional)
### Priority: **High** (provisional)
---
#### _Preconditions:_
---
- A registered user account exists.
- The user is authenticated.
- A valid access token is available.
---
#### _Steps to Reproduce:_
---
1. Send a _PATCH_ request to _/users/{userId}_.
2. Include a new email address and a new password in the JSON request body.
3. Check the response status and response body.
4. Send a _POST_ request to _/users/login_ using the updated email address and the new password.
5. Check the authentication response.
6. Repeat the login request using the updated email address and the previous password.
---   
#### _Actual Result:_
---
- The PATCH request returns _200 OK_.
- The response body indicates success: _{"success": true}_.
- The email address is updated successfully.
- Login with the new email address and new password returns _401 Unauthorized_.
- Login with the updated email address and previous password succeeds.
---
#### _Expected Result:_
---
- If password updates are supported by _PATCH /users/{userId}_, the new password should be saved and the user should be able to authenticate using the updated credentials.
- If password changes are not supported by this endpoint, the API documentation should clearly indicate this limitation and specify the dedicated endpoint for changing passwords.
--- 
#### _Attachments:_
---
- `https://drive.google.com/file/d/1v8cC_IQkZgoo3FGwXE8VkKpLGpZ3hwCJ/view?usp=sharing` — Login attempt request with the old password and old email successful `200 OK` response (before changing).
– `(https://drive.google.com/file/d/1VP_KoTWOHyoAgw_jdjJFOuhCSTCrvsL_/view?usp=sharing)` — PATCH request with the new password and successful `200 OK` response.
- `https://drive.google.com/file/d/1P-urihQc9ljtkVu26fS9logluf7s6s35/view?usp=sharing` — Login attempt with the updated email and new password (`401 Unauthorized`).
- `https://drive.google.com/file/d/18XtY56QD0locbpQoIWgFNxwod9VXuDa0/view?usp=sharing` — Login attempt with the updated email and previous password (successful authentication).
- `https://drive.google.com/file/d/1eREFfUKgBCfB2imp7HMiaNrcAMIQBTLy/view?usp=sharing` — Swagger documentation showing the PATCH request schema.
---
#### _Notes:_
---
- The behavior was reproduced with both a password-only PATCH request and a request containing both email and password.
- Further verification of the dedicated password-change endpoint may be required to determine whether this behavior is an implementation defect or an API documentation inconsistency.
- Sensitive data, including passwords and access tokens, must be masked in all attachments.
###### All attachments: `(https://drive.google.com/drive/folders/1h4VAmVJqWVmpfDigWdR8FX0of3DAFxxA?usp=sharing)`
---
