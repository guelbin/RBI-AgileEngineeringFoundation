# Apply Review Types on Toolshop

## Reference to ISTQB Syllabus chapter

ISTQB FL – 3.2.4 Review Types

## Link to the transfer task file

[Apply Review Types on Toolshop](https://github.com/rgroetz2/TBLL-AgileEngineeringFoundation/blob/main/courses/TestBusters-LearningLab/ISTQB-2026/foundationLevel/transferTasks/Chapter%203/ISTQB-FL-3.2.4_Review_Types_20260405.md)

## Outcome

### Review Scope

**Feature flow:** Checkout – Cart Review  
**Toolshop version:** Sprint 5  
**Reviewed artifact:** Sprint 5 – Checkout Cart Review User Story and Acceptance Criteria (AC1–AC8)  
**Review type:** Technical Review  
**Timebox:** 30 minutes  

The Sprint 5 Checkout – Cart Review User Story was reviewed using a Technical Review approach.

The acceptance criteria were examined for clarity, completeness, consistency, and testability. Related acceptance criteria were also compared with each other to identify potential ambiguities or missing behavior.

This was a static review of the requirement artifact. The Toolshop application was not executed as part of this review.

### Review Observation Log

| ID | Steps | Input / Evidence | Expected Result | Actual Result / Observation | Risk / Quality Impact |
|---|---|---|---|---|---|
| OBS-01 | Review AC2 and check whether the allowed quantity values are clearly defined. | AC2 – Update quantity | The valid quantity range and behavior for invalid or boundary values should be clearly specified. | AC2 does not specify a minimum or maximum quantity or the behavior for values such as `0`, negative values, or very large quantities. | Developers and testers may interpret valid quantities differently. Boundary behavior cannot be tested consistently from the requirement. |
| OBS-02 | Compare AC4 and AC5 and check the expected checkout behavior when the cart is empty. | AC4 – Empty cart; AC5 – Proceed | The expected state of the Proceed action should be clear for both non-empty and empty carts. | AC4 defines the empty-cart message, while AC5 defines Proceed only when the cart contains at least one item. It is not specified whether Proceed should be hidden, disabled, or otherwise unavailable when the cart is empty. | The empty-cart UI may be implemented inconsistently, and testers do not have a clear expected result for this state. |
| OBS-03 | Compare AC6 and AC7 and check how the additional combined-product discount interacts with an existing product discount. | AC6 – Discount badge on items; AC7 – Combined product discount | The calculation basis for the additional 15% discount should be unambiguous when products already have individual discounts. | AC7 does not specify whether the additional 15% discount is calculated from the original item prices or from the already-discounted item prices defined in AC6. | Different interpretations may produce different final totals and inconsistent implementation and testing of the discount calculation. |
| OBS-04 | Compare the price information defined in AC1, AC6, and AC7. | AC1 – Cart contents displayed; AC6 – Discount badge on items; AC7 – Combined product discount | The relationship between item-level prices and cart-level totals should be clearly defined. | AC1 defines `Price` and `Total`, AC6 introduces original and discounted item prices, and AC7 introduces subtotal, discount amount, and final total. Their relationship is not fully defined. | Price information may be displayed or interpreted differently, particularly when multiple discounts apply. |

### Review Result Log

| Finding ID | Related Observation | Finding | Severity | Rework Owner | Follow-up Status |
|---|---|---|---|---|---|
| TR-01 | OBS-01 | Valid quantity range and invalid-value behavior are not specified in AC2. | Medium | Product Owner / Author | Open |
| TR-02 | OBS-02 | The expected behavior of the Proceed action when the cart is empty is not specified. | Medium | Product Owner / Author | Open |
| TR-03 | OBS-03 | The calculation basis for the additional 15% discount is unclear when individual product discounts already apply. | High | Product Owner / Author | Open |
| TR-04 | OBS-04 | The relationship between item-level and cart-level price information is not fully defined. | Medium | Product Owner / Author | Open |

### Review Follow-up

The findings should be clarified with the Product Owner or author of the User Story before implementation or final sprint testing.

After clarification, the affected acceptance criteria should be updated so that the expected behavior, boundary conditions, and discount calculation rules are explicit and testable.

The findings identified during this review represent potential defects or ambiguities in the requirement artifact. They do not confirm defects in the running Toolshop application because no dynamic testing was performed as part of this review.

### Learning Summary ###

This task helped me understand how the four review types described in ISTQB can be applied depending on the purpose and context of a review.

The four review types are:

- **Informal Review:** The least formal review type. It does not require a defined process, and documentation or a review meeting is optional. It is useful for quickly identifying potential defects, discussing ideas, and solving problems, and is commonly used in Agile teams.

- **Walkthrough:** A review normally led by the author of the work product. Reviewers prepare before the meeting, and the author walks the participants through the work product. It can be used to find potential defects, discuss alternatives, exchange ideas, and improve understanding of the work product.

- **Technical Review:** A review performed by technically qualified reviewers. It includes individual preparation and documented findings and may include a review meeting. Its purposes include identifying potential defects, evaluating the quality of the work product, discussing alternatives, and reaching consensus on technical issues.

- **Inspection:** The most formal review type. It follows a defined review process with specified roles, entry and exit criteria, individual preparation, documented findings, and metrics. The review meeting is led by a trained facilitator rather than the author.

For this task, I chose a **Technical Review** because the reviewed artifact was the Sprint 5 Checkout – Cart Review User Story and its acceptance criteria. The goal was to examine the requirements for clarity, completeness, consistency, and testability and to document concrete findings and their quality impact.

An **Informal Review** would have been less structured for the required review result log. A **Walkthrough** was less suitable because it is normally led by the author, while I was reviewing an existing Toolshop artifact as a reviewer. An **Inspection** would have introduced more formality, roles, criteria, and metrics than necessary for the narrow scope and 30-minute timebox. Therefore, a **Technical Review** provided an appropriate level of structure while still allowing the review to focus on technical and functional issues in the acceptance criteria.

During the review, I also learned that acceptance criteria should not only be reviewed individually. Comparing related criteria can reveal ambiguities that are not obvious when each criterion is read separately. For example, comparing AC6 and AC7 showed that the basis for calculating the additional 15% discount is not clearly specified when an individual product discount already exists.

Another important learning point was the difference between a review question and a finding. A question such as "What happens if the API does not respond?" is not automatically a finding. A finding should be supported by something that is missing, ambiguous, inconsistent, or insufficiently testable in the reviewed artifact.

Overall, this task helped me understand that selecting a review type depends on the purpose of the review, the required level of formality, the participants, and the work product being reviewed.