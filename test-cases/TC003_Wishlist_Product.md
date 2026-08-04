## Test Case ID
TC003

## Title
Wishlist a Product

## Description
Search for a product on OpenCart, add it to the wish list, open the wish list, and verify the product is listed.

## Test Data
| Field | Value |
| --- | --- |
| Username / Email | ${APP_USERNAME} |
| Password | ${APP_PASSWORD} |
| Product Name | iPhone |
| Search Term | iPhone |

## Test Steps
| Step | Action | Expected Result |
| --- | --- | --- |
| 1 | Navigate to the application | Home page loads |
| 2 | Search for the product | Search results are shown |
| 3 | Open the product details page | Product page loads |
| 4 | Add the product to the wish list | Wish list is updated |
| 5 | Open the wish list | Wish List page is displayed |
| 6 | Verify the product is in the wish list | Product name appears in wish list |
