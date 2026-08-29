# 🛒 E-Commerce QA & Test Case Portfolio

Welcome to my Software Testing and Quality Assurance portfolio repository! This project demonstrates professional manual testing capabilities, requirement analysis, structured test case creation, and bug tracking workflows.

---

## 📌 Project Overview
- **Target Application:** E-Commerce Platform (Swag Labs / Sample System)
- **Scope:** Functional Testing, Boundary Value Analysis (BVA), API Testing, Security Basics, and UI/UX Verification.
- **Total Test Cases Covered:** 28 structured test cases.

---

## 📋 Comprehensive Test Cases Suite

### 1. Login - Valid Credentials
- **Business Rule:** Registered users must be able to log into the application using valid email and password credentials.
- **Endpoint:** `POST /api/v1/login`
- **Expected Result:** Status Code `200 OK` $\rightarrow$ Return authentication token and user profile data.

### 2. Login - Invalid Password
- **Business Rule:** The system must reject login attempts and deny access when an incorrect password is provided.
- **Endpoint:** `POST /api/v1/login`
- **Expected Result:** Status Code `401 Unauthorized` $\rightarrow$ Return error message: "Invalid email or password."

### 3. User Registration - Mandatory Fields Validation
- **Business Rule:** New user registration requires all mandatory fields (name, email, password) to be filled out.
- **Endpoint:** `POST /api/v1/register`
- **Expected Result:** Status Code `400 Bad Request` $\rightarrow$ Return validation error for missing password field.

### 4. User Registration - Duplicate Email Prevention
- **Business Rule:** The system must not allow duplicate accounts to be created using an email address that already exists in the database.
- **Endpoint:** `POST /api/v1/register`
- **Expected Result:** Status Code `409 Conflict` $\rightarrow$ Return error: "Email address is already registered."

### 5. Password Policy - Minimum Length
- **Business Rule:** User passwords must contain at least 8 characters to meet baseline security standards.
- **Test Value:** `Abc12` (5 chars) $\rightarrow$ Invalid (`400 Bad Request`). `Abcdef12` (8 chars) $\rightarrow$ Valid (`200 OK`).

### 6. Product Catalog - Retrieve All Products
- **Business Rule:** Authenticated users should be able to view the full catalog of available products.
- **Endpoint:** `GET /api/v1/products`
- **Expected Result:** Status Code `200 OK` $\rightarrow$ Return a JSON array containing all active product listings.

### 7. Product Details - Invalid ID
- **Business Rule:** Requesting a product with a non-existent identifier must return a proper not-found status.
- **Endpoint:** `GET /api/v1/products/99999`
- **Expected Result:** Status Code `404 Not Found` $\rightarrow$ Return error: "Product not found."

### 8. Shopping Cart - Add Item
- **Business Rule:** Users must be able to add valid products and specified quantities to their shopping cart.
- **Endpoint:** `POST /api/v1/cart/items`
- **Expected Result:** Status Code `201 Created` $\rightarrow$ Return updated cart contents and item count.

### 9. Shopping Cart - Negative Quantity Validation
- **Business Rule:** Cart item quantities must be greater than zero; negative numbers or zero should be rejected.
- **Endpoint:** `POST /api/v1/cart/items`
- **Expected Result:** Status Code `400 Bad Request` $\rightarrow$ Return error: "Quantity must be at least 1."

### 10. Shopping Cart - Remove Item
- **Business Rule:** Users can remove existing items from their shopping cart.
- **Endpoint:** `DELETE /api/v1/cart/items/prod_123`
- **Expected Result:** Status Code `200 OK` $\rightarrow$ Item removed successfully.

### 11. Checkout - Empty Cart Validation
- **Business Rule:** Users cannot proceed to checkout if their shopping cart is empty.
- **Endpoint:** `POST /api/v1/checkout`
- **Expected Result:** Status Code `400 Bad Request` $\rightarrow$ Return error: "Cannot checkout with an empty cart."

### 12. Checkout - Valid Order Placement
- **Business Rule:** Users with items in their cart and valid shipping details can successfully place an order.
- **Endpoint:** `POST /api/v1/checkout`
- **Expected Result:** Status Code `201 Created` $\rightarrow$ Return order confirmation ID and status `Pending`.

### 13. Order History - Retrieve User Orders
- **Business Rule:** Users can view their historical orders and order statuses.
- **Endpoint:** `GET /api/v1/orders`
- **Expected Result:** Status Code `200 OK` $\rightarrow$ Return a list of past orders.

### 14. User Profile - Update Details
- **Business Rule:** Users can update their profile information such as phone number or display name.
- **Endpoint:** `PUT /api/v1/user/profile`
- **Expected Result:** Status Code `200 OK` $\rightarrow$ Return updated profile object.

### 15. User Profile - Unauthorized Access
- **Business Rule:** Protected profile endpoints must reject requests lacking a valid authentication token.
- **Endpoint:** `GET /api/v1/user/profile` (No Auth Header)
- **Expected Result:** Status Code `401 Unauthorized`.

### 16. Address Management - Add Shipping Address
- **Business Rule:** Users can add new shipping addresses to their address book.
- **Endpoint:** `POST /api/v1/user/addresses`
- **Expected Result:** Status Code `201 Created` $\rightarrow$ Return newly created address ID.

### 17. Address Management - Missing Postal Code
- **Business Rule:** Creating a shipping address requires mandatory fields like city and postal code.
- **Endpoint:** `POST /api/v1/user/addresses`
- **Expected Result:** Status Code `400 Bad Request`.

### 18. Wishlist - Add Product
- **Business Rule:** Users can save items to a personal wishlist for later purchase.
- **Endpoint:** `POST /api/v1/wishlist`
- **Expected Result:** Status Code `201 Created`.

### 19. Wishlist - Duplicate Entry Handling
- **Business Rule:** Adding an item that already exists in the wishlist should not create duplicate entries.
- **Endpoint:** `POST /api/v1/wishlist`
- **Expected Result:** Status Code `409 Conflict` or `200 OK` (Item already in wishlist).

### 20. Pagination API - Handling Large Datasets
- **Business Rule:** When querying a list of items, the API must support pagination parameters (`page` and `limit`).
- **Endpoint:** `GET /api/v1/products?page=1&limit=10`
- **Expected Result:** Status Code `200 OK` $\rightarrow$ Return 10 items per page with metadata.

### 21. File Upload API - Format and Size Validation
- **Business Rule:** Uploads must accept only allowed formats (e.g., `.png`, `.jpg`) and enforce a max size limit.
- **Endpoint:** `POST /api/v1/upload`
- **Expected Result:** Status Code `400 Bad Request` for invalid files.

### 22. Search and Filtering API
- **Business Rule:** Users can filter and search product lists using query parameters.
- **Endpoint:** `GET /api/v1/products?search=laptop&category=electronics`
- **Expected Result:** Status Code `200 OK` $\rightarrow$ Return filtered list.

### 23. Password Reset - Token Expiration
- **Business Rule:** Password reset links sent via email must expire after a specific time frame.
- **Expected Result:** Show error: "Password reset token has expired."

### 24. Cross-Origin Resource Sharing (CORS) Configuration
- **Business Rule:** The API must restrict unauthorized cross-origin requests.
- **Expected Result:** Status Code `403 Forbidden` for unapproved origins.

### 25. Security - SQL Injection Prevention
- **Business Rule:** Input fields must properly sanitize user input to prevent malicious SQL command injection.
- **Expected Result:** Input sanitized, database access denied (`400/401`).

### 26. UI/UX & Session - Inactivity Timeout
- **Business Rule:** User sessions must automatically terminate after a specified period of inactivity.
- **Expected Result:** Redirected to login page after timeout.

### 27. Security - Cross-Site Scripting (XSS) Prevention
- **Business Rule:** User input fields rendering data must sanitize HTML and JavaScript inputs.
- **Expected Result:** Script tags neutralized/escaped safely.

### 28. Localization and Multi-Language Support
- **Business Rule:** The application must correctly switch UI labels and layout direction (LTR/RTL).
- **Expected Result:** Text translates and layout aligns properly.

---

## 🛠️ Tools & Technologies Used
- **Manual Testing & Test Case Management**
- **Jira** (For Bug Tracking & Issue Management)
- **Trello** (For Task & Board Organization)
- **Postman** (For REST API Testing & Endpoint Validation)

---

## 📄 License
This project is open-source and available for portfolio and recruitment display purposes.
