# 2.2.2 - Design and Implement AI-Assisted Checkout Test Cases

## Reference to ISTQB Syllabus Chapter

ISTQB GenAI – 2.2.2 Test Design and Test Implementation with Generative AI

## Link to the Transfer Task File

https://github.com/rgroetz2/RBI-AgileEngineeringFoundation/blob/main/courses/TestBusters-LearningLab/ISTQB-2026/genAI/transferTasks-Outcome/ISTQB-GenAI-2.2.2_Test_Design_and_Test_Implementation_with_Generative_AI_20260728_Serife

## Outcome

### Learning Summary

This transfer task demonstrated how Generative AI can support test design activities for a real webshop flow. AI-generated test cases provided a useful starting point, but manual review and refinement were necessary to make them executable on the actual application.

| Concept | One-line Takeaway |
|----------|----------|
| AI-Assisted Test Design | AI can quickly generate initial test ideas. |
| Prompt Quality | More specific prompts produce more useful test cases. |
| Test Refinement | AI-generated tests require tester review and improvement. |
| Test Execution | Real system behavior must be verified through execution. |
| Prompt Iteration | Weakly specified tests can be improved through prompt refinement. |

> Treat AI-generated test cases as draft artifacts that require tester review before execution.

---

# Confirmation from Feature Documentation

The feature documentation lists the following functionalities that were considered during test design:

- Search
- Filter
- Cart
- Checkout Flow

---

# Refined Test Cases

| Test ID | Type | Functionality | Priority | Preconditions | Test Steps | Test Data | Expected Result |
|----------|----------|----------|----------|----------|----------|----------|----------|
| TC-POS-01 | Positive | Search | High | User is on the product page. | 1. Enter "pliers" into the search field.<br>2. Click Search. | Search Keyword: pliers | Search returns 4 matching products: Combination Pliers, Pliers, Long Nose Pliers and Slip Joint Pliers. |
| TC-POS-02 | Positive | Filter | High | User is on the product catalog page. | 1. Open Filter section.<br>2. Select Category → Hand Tools → Pliers. | Category Filter: Pliers | Product list is filtered and 5 plier-related products are displayed. |
| TC-POS-03 | Positive | Checkout Flow | Critical | Product "Pliers" is already in the cart. | 1. Open cart.<br>2. Proceed to checkout.<br>3. Select Login.<br>4. Enter valid credentials.<br>5. Continue checkout process. | Email: customer@practicesoftwaretesting.com<br>Password: welcome01 | User is successfully authenticated and can proceed to the next checkout step. |
| TC-NEG-01 | Negative | Search | Medium | User is on the product page. | 1. Enter search keyword.<br>2. Click Search. | Search Keyword: XYZ123NOTFOUND | No products are displayed. |
| TC-NEG-02 | Negative | Cart | High | Product "Pliers" is already in the cart. | 1. Open cart.<br>2. Enter quantity 100.<br>3. Update cart. | Quantity = 100 | Warning message "You can order at most 99 of this product." is displayed and quantity is automatically changed to 99. |
| TC-NEG-03 | Negative | Checkout Flow | Critical | Product "Pliers" is already in the cart. | 1. Open cart.<br>2. Proceed to checkout.<br>3. Select "Continue as Guest".<br>4. Leave mandatory fields empty.<br>5. Click Continue as Guest. | Email = Empty<br>First Name = Empty<br>Last Name = Empty | Validation messages are displayed: "Email ist verpflichtend", "Vorname ist verpflichtend" and "Nachname ist verpflichtend". User remains on the same page. |

---

# Execution Evidence

## Executed Test Case 1

### TC-POS-02 – Filter Products by Category

| Item | Result |
|--------|--------|
| Expected Result | Product list is filtered and 5 plier-related products are displayed. |
| Actual Result | After selecting Category → Hand Tools → Pliers, the application displayed 5 matching products. |
| Status | PASS |

---

## Executed Test Case 2

### TC-NEG-02 – Quantity Limit Validation

| Item | Result |
|--------|--------|
| Expected Result | Warning message is displayed and quantity is adjusted to the maximum allowed value. |
| Actual Result | Warning message "You can order at most 99 of this product." was displayed and the quantity was automatically changed from 100 to 99. |
| Status | PASS |

---

# Prompt Refinement Example

## Original Prompt

Create 6 test cases for an e-commerce checkout flow covering search, product detail, cart quantity update, and checkout form validation.

## Improved Prompt

Create executable test cases for Practice Software Testing. Use the product "Pliers", include concrete test data, exact validation behavior, and measurable expected UI outcomes.

## Regenerated Test Case

### Original Version

| Test ID | TC-NEG-02 |
|----------|----------|
| Expected Result | System rejects invalid quantity. |

### Improved Version

| Test ID | TC-NEG-02 |
|----------|----------|
| Expected Result | Warning message "You can order at most 99 of this product." is displayed and quantity is automatically changed to 99. |

---

# Comparison Notes

- The original AI-generated test case used a generic invalid quantity scenario.
- The refined prompt produced a more specific and executable test case.
- The regenerated test case includes concrete test data (quantity = 100).
- The expected result now contains the actual application behavior observed during execution.
- The improved version is easier to verify as Pass or Fail.

---

# Conclusion

Generative AI accelerated the creation of checkout test cases and provided useful initial coverage. Manual review and execution against the real webshop were required to transform generic outputs into executable tests. The refined test cases covered Search, Filter, Cart and Checkout Flow and reflected the actual behavior of the application.