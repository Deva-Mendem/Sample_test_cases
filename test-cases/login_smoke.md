## Test Case ID
login_smoke

## Title
Login smoke (the-internet)

## Description
Simple login smoke test against the-internet.herokuapp.com (no OpenCart site profile required for discover).

## Test Data
| Field | Value |
| --- | --- |
| Username / Email | tomsmith |
| Password | SuperSecretPassword! |

## Test Steps
| Step | Action | Expected Result |
| --- | --- | --- |
| 1 | Navigate to the login page | Login form is displayed |
| 2 | Enter a valid email in the username field | Username is entered |
| 3 | Enter a valid password in the password field | Password is entered |
| 4 | Click the Login button | Secure area page is shown |
| 5 | Verify the post-login page | Success banner is visible |
