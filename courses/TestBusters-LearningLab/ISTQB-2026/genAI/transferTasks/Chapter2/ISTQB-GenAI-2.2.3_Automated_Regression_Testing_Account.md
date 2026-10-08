
### 1. Title
Create a set of regression tests with GenAI for the profile/account feature.

---

### 2. Syllabus Reference
ISTQB GenAI – 2.2.3 Automated Regression Testing with Generative AI

---

### 3. Learning Objective
Use GenAI to create a set of regressions tests (T1-T5) and automate the T1.

---

### 4. Context / Scenario
For V6 some code changes in the profile feature was necessary. The field validation is now available for each field and the password will now be stored in SHA-256 instead of MD-5. 

Create a set of regression test via GenAI to validate that these changes do not lead to regression. 

---

### 5. Task Instructions
1. Provide change notes and relevant feature context to GenAI.
2. Ask for impacted components and potential side effects.
3. Build a regression subset including smoke + high-risk tests.
4. Mark each selected test with rationale.
5. List tests intentionally excluded and why.

---

### 6. Expected Outcome / Deliverable
A  md file where all tests are listed that are regression relevant according to step #5.

---

### 7. Timebox
NA

---

### 8. Hints (Optional)
- Prioritize business-critical paths first.
- Keep “excluded tests” explicit for transparency.
