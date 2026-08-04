## Test Case ID
TC001

## Title
User Login with Valid Credentials

## Description
Log into OpenCart with a valid email and password, then verify the account page is shown.

## Test Data
| Field | Value |
| --- | --- |
| Username / Email | ${APP_USERNAME} |
| Password | ${APP_PASSWORD} |

## Test Steps
| Step | Action | Expected Result |
| --- | --- | --- |
| 1 | Navigate to the account login page | Login form is displayed |
| 2 | Enter a valid email in the E-Mail Address field | Email is entered |
| 3 | Enter a valid password in the Password field | Password is entered |
| 4 | Click the Login button | User is authenticated |
| 5 | Verify the post-login account page | Account dashboard / My Account is visible |
