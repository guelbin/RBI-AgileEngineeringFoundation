# Map Test Levels on Toolshop Checkout

## Title

Map Test Levels on Toolshop Checkout

## Background

Toolshop at [https://practicesoftwaretesting.com/](https://practicesoftwaretesting.com/) delivers a full checkout flow: cart, billing details, payment, and order confirmation. Building and testing this flow involves work at different scopes — from isolated code units to business-ready validation. ISTQB section 2.2.1 defines five test levels to organize these activities so testing stays comprehensive without unnecessary overlap.

## Reference

- ISTQB FL – 2.2.1 Test Levels
- Toolshop: [https://practicesoftwaretesting.com/](https://practicesoftwaretesting.com/)
- Sprint 5 documentation: [https://github.com/testsmith-io/practice-software-testing/tree/main/docs](https://github.com/testsmith-io/practice-software-testing/tree/main/docs)

## Tasks

1. Open Toolshop, add one product to the cart, and navigate to [https://practicesoftwaretesting.com/checkout](https://practicesoftwaretesting.com/checkout). Note two things you would verify on the checkout page (for example: billing form fields, payment method options).
2. Open the Sprint 5 docs and find one checkout-related API endpoint (for example: `POST /carts` or cart quantity update).
3. Complete the table below for the **checkout feature** — one short answer per cell.


| Test level | Test object on Toolshop | Test objective | Who typically performs it | One example test |
| ---------- | ----------------------- | -------------- | --------------------------- | ---------------- |
| Component testing | | | | |
| Component integration testing | | | | |
| System testing | | | | |
| System integration testing | | | | |
| Acceptance testing | | | | |


4. Write **one sentence** explaining which test level you actually performed in step 1 and why the other levels need different environments or roles.

## Expected Outcome

The completed table (all 5 rows) plus one sentence about which level you performed and why the others differ.

## Syllabus Text

Test levels are groups of test activities organized and managed together. Each test level is an instance of the test process, performed at a given phase of development — from individual components to complete systems.

The syllabus describes five test levels:

- **Component testing** (unit testing) — tests components in isolation; often uses test harnesses or unit test frameworks; normally performed by developers.
- **Component integration testing** — tests interfaces and interactions between components; depends on integration strategy (bottom-up, top-down, big-bang).
- **System testing** — tests overall behavior and capabilities of the entire system; includes functional end-to-end tasks and non-functional characteristics; often performed by an independent test team against system specifications.
- **System integration testing** — tests interfaces between the system under test and other systems or external services; requires test environments similar to production.
- **Acceptance testing** — validates readiness for deployment; confirms the system fulfills business needs; ideally performed by intended users (UAT, operational, contractual, regulatory, alpha, beta).

Test levels are distinguished by attributes such as test object, test objectives, test basis, defects and failures, and approach and responsibilities — to avoid overlapping test activities.
