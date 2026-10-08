# ISTQB GenAI – 2.2.1 – Test Analysis

## Prompt for GenAI

The product under test is the ToolShop demo webshop:

https://practicesoftwaretesting.com/

Generate risk-based test conditions for the following user story and acceptance criteria.

For each test condition:

* Assign a risk level (High, Medium, Low).
* Assign a priority (P1, P2, P3).
* Reference the related acceptance criterion.
* State any assumptions explicitly.

---

## User Story

### US2350 – Provide Product Articles in Czech Language

**User Story**

As a customer from the Czech Republic, I want to read product information in Czech so that I can understand the products and make informed purchasing decisions.

**Description**

To support the Czech market expansion, the webshop shall provide Czech-language product content for selected articles and product categories.

### Acceptance Criteria

* **ACC-01:** Product titles for supported articles are displayed in Czech when the customer selects the Czech language.
* **ACC-02:** Product descriptions for supported articles are displayed in Czech when the Czech language is active.
* **ACC-03:** Product specifications and technical details are displayed in Czech for supported products.
* **ACC-04:** Product categories included in the Czech market scope provide Czech-language content for all assigned products.
* **ACC-05:** Customers can switch between Czech and other supported languages without losing product context.
* **ACC-06:** Products without available Czech translations display a defined fallback language according to the webshop configuration.
* **ACC-07:** Czech product content is displayed consistently on product listing pages and product detail pages.
* **ACC-08:** Special Czech characters and language-specific formatting are displayed correctly in all product content fields.
* **ACC-09:** Search results display Czech product titles and descriptions when the webshop language is set to Czech.
* **ACC-10:** Czech-language product content is visible during the complete customer journey, including product detail, cart, and checkout overview pages.

---

## Assumptions

* Supported articles/products refer only to products included in the Czech market rollout and having approved Czech translations.
* The webshop already supports language switching and localization.
* A fallback language (e.g., English or German) is configured.
* Product Listing Pages (PLP), Product Detail Pages (PDP), Cart, Checkout Overview and Search are within scope.
* Search indexes support localized product content.

---

## AI Generated Risk-Based Test Conditions

| ID    | Test Condition                                                                                                            | Risk Level | Priority | AC Reference |
| ----- | ------------------------------------------------------------------------------------------------------------------------- | :--------: | :------: | :----------: |
| TC-01 | Verify that product titles of supported products are displayed in Czech when Czech language is selected.                  |    High    |    P1    |    ACC-01    |
| TC-02 | Verify that product descriptions of supported products are displayed in Czech when Czech language is active.              |    High    |    P1    |    ACC-02    |
| TC-03 | Verify that product specifications and technical details of supported products are displayed in Czech.                    |    High    |    P1    |    ACC-03    |
| TC-04 | Verify that all products assigned to Czech-supported categories provide Czech-language content.                           |    High    |    P1    |    ACC-04    |
| TC-05 | Verify that switching from another language to Czech retains the currently viewed product page.                           |   Medium   |    P2    |    ACC-05    |
| TC-06 | Verify that switching from Czech to another supported language retains the currently viewed product page.                 |   Medium   |    P2    |    ACC-05    |
| TC-07 | Verify that products without Czech translations display the configured fallback language.                                 |    High    |    P1    |    ACC-06    |
| TC-08 | Verify that no empty content fields are displayed when Czech translations are unavailable and fallback language is used.  |    High    |    P1    |    ACC-06    |
| TC-09 | Verify that Czech product titles are displayed consistently on both product listing pages and product detail pages.       |   Medium   |    P2    |    ACC-07    |
| TC-10 | Verify that Czech product descriptions are displayed consistently on both product listing pages and product detail pages. |   Medium   |    P2    |    ACC-07    |
| TC-11 | Verify that Czech-specific characters (e.g., č, ř, š, ž, ý, ě) are displayed correctly in all product content fields.     |    High    |    P1    |    ACC-08    |
| TC-12 | Verify that Czech-language formatting and text rendering are displayed correctly without encoding issues.                 |   Medium   |    P2    |    ACC-08    |
| TC-13 | Verify that search results display Czech product titles when Czech language is selected.                                  |    High    |    P1    |    ACC-09    |
| TC-14 | Verify that search results display Czech product descriptions when Czech language is selected.                            |    High    |    P1    |    ACC-09    |
| TC-15 | Verify that Czech-language product content remains visible on the product detail page throughout the customer journey.    |    High    |    P1    |    ACC-10    |
| TC-16 | Verify that Czech-language product content remains visible and consistent in the shopping cart.                           |    High    |    P1    |    ACC-10    |
| TC-17 | Verify that Czech-language product content remains visible and consistent in the checkout overview page.                  |    High    |    P1    |    ACC-10    |

---

## Traceability Matrix

| Acceptance Criterion | Test Conditions     |
| -------------------- | ------------------- |
| ACC-01               | TC-01               |
| ACC-02               | TC-02               |
| ACC-03               | TC-03               |
| ACC-04               | TC-04               |
| ACC-05               | TC-05, TC-06        |
| ACC-06               | TC-07, TC-08        |
| ACC-07               | TC-09, TC-10        |
| ACC-08               | TC-11, TC-12        |
| ACC-09               | TC-13, TC-14        |
| ACC-10               | TC-15, TC-16, TC-17 |

---

## Risk Assessment Rationale

* **High (P1):** Incorrect or missing Czech content directly impacts customer understanding, purchasing decisions, and market readiness.
* **Medium (P2):** Issues affecting consistency, language switching, or presentation quality may degrade the user experience but do not completely block purchases.
* **Low (P3):** No low-risk conditions were identified because all acceptance criteria contribute directly to the Czech market launch and customer-facing functionality.
