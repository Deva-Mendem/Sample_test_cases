## Test Case ID
TC002

## Title
Add Product To Cart

## Description
Search for a product on OpenCart, open the product page, add it to the shopping cart, and verify the cart contents.

## Test Data
| Field | Value |
| --- | --- |
| Username / Email | ${APP_USERNAME} |
| Password | ${APP_PASSWORD} |
| Product Name | iPhone |
| Search Term | iPhone |
| Quantity | 1 |

## Test Steps
| Step | Action | Expected Result |
| --- | --- | --- |
| 1 | Navigate to the application | Home page loads |
| 2 | Search for the product | Search results are shown |
| 3 | Open the product details page | Product page loads |
| 4 | Add the product to cart | Success message / cart updates |
| 5 | Open the shopping cart | Cart page is displayed |
| 6 | Verify the product is in the cart | Product name appears in cart |
