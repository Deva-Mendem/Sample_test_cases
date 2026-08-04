## Test Case ID
TC004

## Title
Search a Product

## Description
Search for a product on OpenCart and verify matching results are returned.

## Test Data
| Field | Value |
| --- | --- |
| Username / Email | ${APP_USERNAME} |
| Password | ${APP_PASSWORD} |
| Search Term | iPhone |
| Product Name | iPhone |

## Test Steps
| Step | Action | Expected Result |
| --- | --- | --- |
| 1 | Navigate to the application | Home page loads |
| 2 | Enter a search term in the search field | Search term is entered |
| 3 | Submit the search | Search results page loads |
| 4 | Verify search results are shown | Product results are visible |
