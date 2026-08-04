## Test Case ID
login_smoke

## Title
Login smoke (the-internet)

## Description
Simple login smoke test against https://the-internet.herokuapp.com/login — public demo page with known credentials.

## Test Data
| Field | Value |
| --- | --- |
| Username / Email | tomsmith |
| Password | SuperSecretPassword! |
| Base URL | https://the-internet.herokuapp.com/login |

## Test Steps
| Step | Action | Expected Result |
| --- | --- | --- |
| 1 | Navigate to https://the-internet.herokuapp.com/login | Login form is displayed |
| 2 | Enter tomsmith in the Username field | Username is entered |
| 3 | Enter SuperSecretPassword! in the Password field | Password is entered |
| 4 | Click the Login button | Secure area page is shown |
| 5 | Verify the post-login success banner | "You logged into a secure area!" is visible |
