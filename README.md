# 🛒 E-Commerce QA & Test Case Portfolio

Welcome to the Software Testing and Quality Assurance portfolio repository! This project showcases comprehensive manual testing documentation, boundary value analysis (BVA), equivalence partitioning (EP), API testing endpoints, and security validation workflows for the Swag Labs e-commerce platform.

---

## 📌 Project Overview
- **Target Application:** Swag Labs E-Commerce Platform
- **Scope:** Functional Testing, Boundary Value Analysis, API Testing, Security, and UI/UX Verification.
- **Total Test Cases Covered:** 29 structured test cases.

---

## 📋 Comprehensive Test Cases Suite

* **Test Case 1: Age Validation** – Validates that the user age falls strictly between 18 and 60 using Equivalence Partitioning (EP) and Boundary Value Analysis (BVA).
* **Test Case 2: Password Length Validation** – Enforces password length boundaries between 8 and 16 characters.
* **Test Case 3: API - Verify Submitting Form with Valid Fields** – Tests form submission via API with valid payload data returning `200 OK` or `201 Created`.
* **Test Case 4: API - Verify Submitting Form with Missing Name Field** – Validates that omitting the mandatory name field triggers a `400 Bad Request` or `422 Unprocessable Entity`.
* **Test Case 5: API - Verify Submitting Form with Student Status** – Verifies successful processing and eligibility application when `is_student` is set to true.
* **Test Case 6: Decision Table - Promo Code & Membership Validation** – Evaluates combination rules for Premium/Standard memberships and promo code discounts.
* **Test Case 7: Login Screen - Failed Login Attempts & Account Lockout** – Locks user accounts for 15 minutes after 3 consecutive failed login attempts.
* **Test Case 8: Decision Table Testing (General Form Rules)** – Tests complex condition matrices combining age, password length, and membership tiers.
* **Test Case 9: Negative Test Case - Invalid Email Format** – Rejects email formats missing the `@` symbol or domain components.
* **Test Case 10: API Negative Test Case - Unauthorized Access** – Denies access (`401 Unauthorized`) to protected endpoints when the authorization token is missing.
* **Test Case 11: UI/UX Field Validation - Required Fields** – Triggers form validation error messages when required fields (Name, Email, Password) are blank.
* **Test Case 12: API Negative Test Case - Invalid Method / Method Not Allowed** – Rejects incorrect HTTP methods (e.g., GET instead of POST) with a `405 Method Not Allowed` status.
* **Test Case 13: Boundary Value Analysis - Maximum Age Limit** – Tests exact boundary limits around the maximum registration age of 60 years.
* **Test Case 14: Password Character Complexity Validation** – Enforces strong password rules requiring uppercase letters, lowercase letters, numbers, and special characters.
* **Test Case 15: API - Verify Duplicate Email Registration** – Prevents duplicate accounts by returning `409 Conflict` when registering with an existing email.
* **Test Case 16: API - Update User Profile Data** – Allows authorized users to update profile details via valid PUT/PATCH requests.
* **Test Case 17: API Delete User Account** – Permanently deletes user records via a valid DELETE request to the account endpoint (`200 OK` / `204 No Content`).
* **Test Case 18: UI/UX Navigation - Logout Functionality** – Clears active user sessions, redirects to the login screen, and blocks browser back-button access.
* **Test Case 19: UI/UX - Remember Me Functionality** – Persists authentication state across browser restarts when "Remember Me" is enabled.
* **Test Case 20: API - Rate Limiting (Too Many Requests)** – Mitigates brute-force attacks by limiting rapid consecutive login attempts and returning `429 Too Many Requests`.
* **Test Case 21: Pagination API - Handling Large Datasets** – Supports `page` and `limit` query parameters on list endpoints to optimize performance.
* **Test Case 22: File Upload API - Format and Size Validation** – Enforces file type rules (e.g., png/jpg) and a maximum size limit of 5MB.
* **Test Case 23: Search and Filtering API** – Validates that query parameters correctly filter and return matching records.
* **Test Case 24: Password Reset - Token Expiration** – Expires password reset links after a specified time frame for enhanced security.
* **Test Case 25: Cross-Origin Resource Sharing (CORS) Configuration** – Restricts unauthorized cross-origin requests by blocking unapproved frontend domains (`403 Forbidden`).
* **Test Case 26: Security - SQL Injection Prevention** – Sanitizes user inputs on login and search fields to block malicious database injection attempts.
* **Test Case 27: UI/UX & Session - Inactivity Timeout** – Automatically terminates user sessions after 20 minutes of inactivity to safeguard sensitive data.
* **Test Case 28: Security - Cross-Site Scripting (XSS) Prevention** – Neutralizes and escapes HTML and JavaScript payloads rendered in profile bios or comment sections.
* **Test Case 29: Localization and Multi-Language Support** – Correctly switches UI labels, messages, and layout directions (LTR for English, RTL for Arabic).

---

## 🛠️ Tools & Technologies Used
- **Manual Testing & Test Case Design** (Equivalence Partitioning & Boundary Value Analysis)
- **Jira** (Issue Tracking, Bug Reporting & Kanban Boards)
- **Trello** (Task Management & Board Organization)
- **Postman** (REST API Testing & Endpoint Validation)

---

## 📄 License
This portfolio project is open-source and structured for recruitment and professional demonstration purposes.
