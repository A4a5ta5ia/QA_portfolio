# QA Engineer Portfolio | Kozub A.S.

Welcome! This repository showcases my practical experience in Manual QA Testing, covering Web UI, API, and Database layers.

---

## 📨 Contacts & Resume
*   **Email:** [anastasia.kozub779@gmail.com](mailto:anastasia.kozub779@gmail.com)
*   **LinkedIn:** www.linkedin.com/in/anastasia-kozub-2bb6b5289
*   **Resume (PDF):** [Download My CV](./Anastasia Kozub_QA_CV.pdf)

---

## 🛠️ Tech Stack & Tools
*   **Testing Techniques:** Boundary Value Analysis (BVA), Equivalence Partitioning (EP), Pairwise Testing, State Transition.
*   **API Testing:** Postman (Collections, Environments), Swagger, REST Architecture, HTTP Methods and Status Codes.
*   **Traffic Interception (Proxy):** Charles Proxy / Fiddler (Analyzing HTTP/HTTPS traffic, Breakpoints).
*   **Web Testing:** Chrome DevTools (DOM architecture, Network tab inspection).
*   **Databases:** MySQL (SELECT, JOIN, WHERE, filtering and data verification).
*   **Process and Tools:** Git/GitHub, Agile (Scrum/Kanban), Qase.io, Jira.

---

## 📁 Practical Projects

### 🌐 Project 1: Animal Shelter Platform (Comprehensive Web Testing)
Full-cycle manual testing of a pet adoption web application aimed at ensuring a stable user flow from search to pet booking.
*   **Scope:** Pet adoption forms, blog module, subscription/contact footer forms, UI/UX consistency, and layout alignment via Chrome DevTools.
*   **Artifacts and Documentation:** [Open Checklists and Bug Reports in Google Sheets](https://docs.google.com/spreadsheets/d/17sm_H91vU9bzLXVqQHxAl_Ccw9fQM9Cssa_qpc75ztg/edit?usp=sharing) — full test documentation, tracking, and exact steps to reproduce for all issues can be found here.
*   **Metrics:** 137 bugs found (3 Critical, 4 Major, 102 Medium, 28 Minor).

**Selected Bug Examples (Short Overview):**
*   **[BUG_49] Critical | Backend Error Handling:** "Ask about dogs" form returns a POST 200 OK status code in DevTools Network tab, but displays a raw system configuration error to the user instead of a success message.
*   **[BUG_51] Major | Missing Idempotency:** The footer form allows multiple duplicate submissions of identical valid data consecutively without any validation, which risks overloading the server database.
*   **[BUG_102] Medium | Date Validation Defect:** "Pet booking" date field accepts invalid calendar dates, allowing a user to pick February 29th on a non-leap year (e.g., 2027).

---

### 🛒 Project 2: E-Commerce Shop Application (UI and Logic Testing)
Deep testing of the Catalogue, Complex Filtering, and Pagination modules of an online shop.
*   **Scope:** Filter persistence after page updates, complex filtering combinations, items-per-page limits, and navigation controls.
*   **Test Design Applied:** *Pairwise Testing* was used to combine 4 distinct filter variables (Manufacturer, Price range, Sorting method, Items per page). This optimized coverage, reducing hundreds of combinations.
*   **Artifacts & Documentation:** [https://docs.google.com/spreadsheets/d/1VecvZgAwSym-dUQ6bVynhKOMuNzm5BdNeEBnUA34Pos/edit?usp=sharing].
*   **Metrics:** 14 bugs found (2 Major, 10 Medium, 2 Minor).

**Selected Bug Examples (Short Overview):**
*   **[BUG_CAT_09] Major | UI Crash on Boundary Value:** Inputting negative values (e.g., from -13 to -900) into the price range filter completely breaks the structure, causing all filters and products to disappear from the screen.
*   **[BUG_CAT_03] Major | Input Validation Failure:** Entering "0" into the price range fields is completely ignored by the system; the filters auto-clear and display the full catalog instead of showing free products.
*   **[BUG_CAT_13] Medium | Reset State Defect:** The "Reset Filters" button partially fails — it successfully resets price inputs but leaves "Sorting" and "Items per page" dropdown values unchanged.

---

### 🌐 Project 3: API Testing and Validation (REST API Petstore)
Full-cycle API testing of a Petstore service aimed at verifying backend business logic, status codes, data structures, and system stability under invalid inputs.

* **Scope and Approaches:** Functional positive and negative testing of REST endpoints (GET, POST, PUT, DELETE) utilizing Boundary Value Analysis and Equivalence Partitioning for input parameters. Verification of JSON schemas, data persistence, and error handling mechanisms.
* **Artifacts and Documentation:**
    * [Open Test Run and Execution Status in Qase.io](https://app.qase.io/public/report/a2007fb324e8712a38eb9594f9c64d96c218fe6d) — complete test suite execution with detailed steps.
    * [Download API Bug Reports (CSV)](./api-petstore/api_bug_reports_petstore.csv) — comprehensive document containing all bugs found during API execution.
    * [Download Postman Collection](./api-petstore/Pet Store.postman_collection.json) — local file for request execution.
* **Metrics:** 79 test cases executed in total: 31 Passed, 48 Failed.
* **Selected Bug Examples:**
    * **[API_BUG_D44] Major: Validation Failure on Enum Values:** Server returns 200 OK instead of 400 Bad Request when adding a new pet with a value not included in the enum list for the "status" field.
    * **[API_BUG_D39] Major: Server Crash on Invalid Data Type:** Server returns 500 Internal Server Error instead of 400 Bad Request when an integer value is passed inside the category "name" field.
    * **[API_BUG_D34] Minor: Missing Required Field Handling:** Server returns 200 OK instead of 400 Bad Request when adding a new pet with a tag object containing only an "id" field while missing the mandatory "name" field.
