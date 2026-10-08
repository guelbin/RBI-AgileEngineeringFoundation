
# GENAI 2.2.4 - AI-Assisted Test Monitoring and Control for Sprint 5 Holtesting

## Background

The TTT426 team is executing Sprint 6 test activities against **ToolShop Holtesting V6** ([https://holtesting.practicesoftwaretesting.com/](https://holtesting.practicesoftwaretesting.com/)). Over ten working days, testers recorded execution results for fifteen suites per day (user stories, regression, checkout E2E, API security, smoke/sanity, and cross-browser).

Daily status meetings take too long when someone manually reads every execution report. The test manager wants an AI-assisted monitoring brief that summarizes progress, defect trends, and risks — but every metric must be traceable to the source logs. Your task is to apply generative AI to test monitoring and control using the provided execution data.

## Reference
- ISTQB GenAI – 2.2.4 Test Monitoring and Control with Generative AI
- ToolShop V6: [https://holtesting.practicesoftwaretesting.com/](https://holtesting.practicesoftwaretesting.com/)
- Sprint 6 execution logs: `courses/TestBusters-LearningLab/ISTQB-2026/TTT426-the-testproject/testexecutionTTT426/sprint5-holtesting/`
  - `day01/` … `day10/` — one markdown report per suite (e.g. `03-US3100-payu-payment-execution.md`, `11-US4510-regression-execution.md`, `13-API-api-security-execution.md`)
- Each report contains: execution summary (Passed / Failed / Blocked / Not Executed), open defects, and per-test-case results


## Link to the Transfer Task File
https://github.com/rgroetz2/TBLL-AgileEngineeringFoundation/blob/main/courses/TestBusters-LearningLab/ISTQB-2026/genAI/transferTasks/Chapter2/ISTQB-GenAI-2.2.4_Test_Monitoring_and_Control_with_Generative_AI_20260713.md

---

# Outcome

## 1. Monitoring Window and Data Collection

The selected monitoring window covers three consecutive days:

- `day03`
- `day04`
- `day05`

Each selected day contains 15 test-suite reports. Therefore, a total of 45 reports were included in the monitoring window.

The execution summaries and open-defect tables were collected from all 15 suite reports for each day and consolidated into one input file. No calculations or corrections were performed during the collection step.

The collected source excerpts are available here:

[Monitoring Log Excerpts – day03 to day05](G114-supporting-files/01_Monitoring_Log_Excerpts_day03-day05.md)

> **Scope note:** The task Background refers to Sprint 6, while the task title, source folder and execution reports refer to Sprint 5 Holtesting. The analysis follows the Sprint 5 designation used in the source reports.

## 2. Supporting Files

The prompts and generated monitoring briefs are documented in the following supporting files:

1. [Structured Prompt – Version 1](G114-supporting-files/02_Structured_Prompt_V1.md)
2. [Initial Monitoring Brief – Version 1](G114-supporting-files/03_Initial_Monitoring_Brief_V1_day03-day05.md)
3. [Improved Structured Prompt – Version 2](G114-supporting-files/04_Improved_Structured_Prompt_V2.md)
4. [Refined Monitoring Brief – Version 2](G114-supporting-files/05_Refined_Monitoring_Brief_V2_day03-day05.md)


## 3. Initial GenAI Analysis

The collected execution summaries and open-defect tables were submitted to the GenAI tool using the first structured prompt.

The prompt instructed the model to:

- calculate suite-level and daily test progress metrics;
- calculate totals and pass rates for each day;
- compare the progress across `day03`, `day04`, and `day05`;
- identify new, recurring, and unresolved High-severity defects;
- flag test suites containing Blocked or Not Executed tests;
- propose exactly two test-control actions;
- produce a stakeholder-ready summary and metrics tables.

The complete prompt is available in:

[Structured Prompt – Version 1](G114-supporting-files/02_Structured_Prompt_V1.md)

The initial AI-generated monitoring brief is available in:

[Initial Monitoring Brief – Version 1](G114-supporting-files/03_Initial_Monitoring_Brief_V1_day03-day05.md)

At this stage, the generated monitoring brief had not yet been validated. Therefore, all metrics, defect statements, risk flags, and trend claims were subsequently checked against the source reports.

---

## 4. Verification Log

The first AI-generated monitoring brief was manually verified against the collected source reports. Daily totals, suite-level metrics, pass rates, defect IDs, severity information, risk flags, and defect trends were checked.

Correct statements were marked as **Verified**. Incorrect calculations or claims were marked as **Corrected**, together with the verified value or explanation.

### 4.1 Verification Log – day03

| **Claim Checked** | **AI Output** | **Verification Result / Correction** | **Status** |
|---|---|---|---|
| Suite-level figures for `day03` | Planned, Passed, Failed, Blocked, and Not Executed per test suite | All figures match the 15 source reports from `day03`. | Verified |
| Daily totals for `day03` | Total 90, Passed 65, Failed 9, Blocked 5, Not Executed 11 | The totals match the source reports. | Verified |
| Execution Progress for `day03` | 87.8% | `(65 + 9 + 5) / 90 × 100 = 87.8%` | Verified |
| Pass Rate for `day03` | 72.2%, based on `65 / 90` | The formula used is not suitable for the Pass Rate definition applied in this report. Correction: `65 / (65 + 9) × 100 = 87.8%`. | Corrected |
| Suite-level Pass Rates for `day03` | Calculated as `Passed / Planned` | The AI calculated all suite-level Pass Rates using `Passed / Planned`. They must be recalculated using `Passed / (Passed + Failed)`. | Corrected |
| High-defect Risk Flags for `day03` | Test suites with open High-severity defects were flagged. | According to the source reports, the flagged test suites do contain open High-severity defects. | Verified |

#### Corrected Suite-Level Pass Rates for day03

| **Test Suite** | **AI Output** | **Correct Value** |
|---|---:|---:|
| `US2300-czech-language` | 87.5% | 100.0% |
| `US3100-payu-payment` | 77.8% | 87.5% |
| `US4200-delivery-costs` | 33.3% | 100.0% |
| `US4510-regression` | 60.0% | 85.7% |
| `CHK-checkout-e2e` | 80.0% | 100.0% |
| `SMK-smoke-sanity` | 80.0% | 100.0% |
| `XBR-cross-browser` | 60.0% | 75.0% |
---

### 4.2 Verification Log – day04

| **Claim Checked** | **AI Output** | **Verification Result / Correction** | **Status** |
|---|---|---|---|
| Suite-level figures for `day04` | Planned, Passed, Failed, Blocked, and Not Executed per test suite | The checked figures match the 15 source reports from `day04`. | Verified |
| Daily totals for `day04` | Total 90, Passed 70, Failed 12, Blocked 3, Not Executed 5 | The totals match the source reports. | Verified |
| Execution Progress for `day04` | 94.4% | `(70 + 12 + 3) / 90 × 100 = 94.4%` | Verified |
| Pass Rate for `day04` | 77.8% | Correction: `70 / (70 + 12) × 100 = 85.4%`. | Corrected |
| High-defect and Blocked/Not-Executed Risk Flags | The affected test suites were flagged. | The Risk Flags and figures match the source reports. | Verified |

#### Corrected Suite-Level Pass Rates for day04

| **Test Suite** | **AI Output** | **Correct Value** |
|---|---:|---:|
| `US3100-payu-payment` | 66.7% | 75.0% |
| `US4200-delivery-costs` | 44.4% | 100.0% |
| `US4510-regression` | 80.0% | 88.9% |
---

### 4.3 Verification Log – day05

| **Claim Checked** | **AI Output** | **Verification Result / Correction** | **Status** |
|---|---|---|---|
| Suite-level figures for `day05` | Planned, Passed, Failed, Blocked, and Not Executed per test suite | The checked figures match the 15 source reports from `day05`. | Verified |
| Daily totals for `day05` | Total 90, Passed 79, Failed 5, Blocked 2, Not Executed 4 | The totals match the source reports. | Verified |
| Execution Progress for `day05` | 95.6% | `(79 + 5 + 2) / 90 × 100 = 95.6%` | Verified |
| Pass Rate for `day05` | 87.8% | Correction: `79 / (79 + 5) × 100 = 94.0%`. | Corrected |
| High-defect and Blocked/Not-Executed Risk Flags | The affected test suites were flagged. | The Risk Flags and figures match the source reports. | Verified |

#### Corrected Suite-Level Pass Rates for day05

| **Test Suite** | **AI Output** | **Correct Value** |
|---|---:|---:|
| `US4200-delivery-costs` | 55.6% | 100.0% |
| `US1001-playwright-guide` | 33.3% | 50.0% |
| `US4510-regression` | 90.0% | 100.0% |

---

### 4.4 Defect and Trend Verification

The defect IDs, severity values, summaries, related stories, and status information reported by the AI were compared with the Open Defects tables in the source reports.

| **Claim Checked** | **AI Output** | **Verification Result / Correction** | **Status** |
|---|---|---|---|
| Unique Open Defect IDs | 15 unique Open Defect ID strings were reported for each day. | The source reports contain 15 unique ID strings on `day03`, `day04`, and `day05`. | Verified |
| New defects after the `day03` baseline | No new unique Defect ID appeared on `day04` or `day05`. | All 15 ID strings from `day03` also appear on `day04` and `day05`. No additional ID string was found. | Verified |
| Recurring defects | All 15 Defect ID strings recur on both `day04` and `day05`. | The cross-day comparison confirms that the same 15 ID strings appear on all three days and remain Open. | Verified |
| Unresolved High-severity defects | `DEF-S5-001`, `DEF-S5-005`, `DEF-S5-008`, and `DEF-S5-011` remain Open throughout the monitoring window. | The IDs, High-severity classification, and Open status were confirmed in the source reports. The ambiguous use of `DEF-S5-005` is documented separately below. | Verified |
| Ambiguous Defect References | `DEF-S5-003`, `DEF-S5-004`, and `DEF-S5-005` are reused with different summaries. The AI stated that only `DEF-S5-005` also has a different severity. | The different summaries were confirmed. However, both `DEF-S5-004` and `DEF-S5-005` have conflicting severity values. | Corrected |

#### Verified Unresolved High-Severity Defects

| **Defect ID** | **Summary** | **Related Story** | **Status during `day03`–`day05`** |
|---|---|---|---|
| `DEF-S5-001` | PayU redirect returns 502 on holtesting staging | `US3100` | Open |
| `DEF-S5-005` | Language switcher missing on checkout page | `US2300` | Open |
| `DEF-S5-008` | Heavy delivery tier applied at 9.9 kg | `US4200` | Open |
| `DEF-S5-011` | API invoices endpoint returns all users invoices | API | Open |

#### Ambiguous Defect References

| **Defect ID** | **First Use** | **Playwright Use** | **Verification Result** |
|---|---|---|---|
| `DEF-S5-003` | Medium – “Zásilkovna shown for US shipping address” | Medium – “Failure in Playwright Test Guide” | Different summary; same severity |
| `DEF-S5-004` | Low – “Build date format inconsistent in footer” | Medium – “Failure in Playwright Test Guide” | Different summary and severity |
| `DEF-S5-005` | High – “Language switcher missing on checkout page” | Medium – “Failure in Playwright Test Guide” | Different summary and severity |

The AI correctly identified that all three Defect IDs were reused with different summaries. However, its statement that only `DEF-S5-005` had a conflicting severity was incorrect. The severity also differs for `DEF-S5-004`. This claim was therefore marked as **Corrected**.


### 4.5 Verification of the Test-Control Actions

The two test-control actions proposed by the AI were verified against the source reports and the validated metrics.

| **Claim Checked** | **Verification Result** | **Status** |
|---|---|---|
| Test-control action 1: Prioritise High-severity defects and perform targeted retesting | The four identified High-severity defects, `DEF-S5-001`, `DEF-S5-005`, `DEF-S5-008`, and `DEF-S5-011`, remain Open throughout the monitoring window. Prioritising these defects and subsequently retesting the affected suites is therefore supported by the source data. Before retesting `DEF-S5-005`, its correct assignment must be confirmed using its Summary, Severity, and Related Story because the ID is used ambiguously. | Verified |
| Test-control action 2: Concentrate test capacity on the remaining B/NE suites | On `day05`, the test suites `US4200-delivery-costs`, `US1001-playwright-guide`, and `US4510-regression` contain a combined total of 2 Blocked and 4 Not Executed tests. With 1 Blocked and 3 Not Executed tests, `US4200-delivery-costs` alone accounts for four of the six outstanding test results. The proposed reallocation of test capacity is therefore supported by the source data. | Verified |

Both proposed test-control actions are consistent with the verified metrics and defect information. No correction was required for these two recommendations.

---

## 5. Prompt Refinement and Comparison of Results

Based on the verification findings, the initial prompt was refined. Version 2 explicitly defined the Pass Rate formula, strengthened the traceability requirements, and required ambiguous defect references to be reported systematically.

The same collected source data was analysed again using the improved prompt.

- [Improved Structured Prompt – Version 2](G114-supporting-files/04_Improved_Structured_Prompt_V2.md)
- [Refined Monitoring Brief – Version 2](G114-supporting-files/05_Refined_Monitoring_Brief_V2_day03-day05.md)

The improved Version 2 prompt serves as a reusable template for future daily test-status reporting.

| Verification Item | Version 1 | Version 2 | Assessment |
|---|---|---|---|
| Pass Rate | Calculated as `Passed / Planned` | Calculated as `Passed / (Passed + Failed)` | Corrected |
| Blocked and Not Executed | Correctly reported for each suite and day | Correctly retained and additionally presented in a separate overview | Verified and retained |
| Ambiguous Defect References | Mentioned in a general Traceability Note | Explicitly identified and analysed in separate tables | Expanded and clarified |
| Risk Flags | General statements such as “High defect open” were used without specifying the related Defect ID | Specific Defect IDs and ambiguous references were reported directly for the affected test suites | More detailed and traceable |
| Traceability | Source-based metrics and a general traceability statement were provided | Defect metadata, Risk Flags, and ambiguous references were documented more systematically | Improved |
| Test-Control Actions | Two actions were proposed and supported by the monitoring data | Exactly two actions were retained and supported by the corrected metrics | Retained and refined |

---


## 6. Final Validated Monitoring Brief for day05

### 6.1 Stakeholder Summary

On `day05`, 86 of the 90 planned tests had reached an execution status. This represents an Execution Progress of 95.6%. A total of 79 tests Passed, 5 Failed, 2 were Blocked, and 4 were Not Executed.

The corrected Pass Rate is 94.0%. Despite the high level of execution progress, sprint exit readiness cannot yet be confirmed. Four High-severity defects remain Open, and six tests do not yet have a conclusive result. In addition, the source data contains ambiguous defect references. The source does not define numerical sprint exit thresholds.

### 6.2 Progress Snapshot

| Metric | Result for `day05` |
|---|---:|
| Planned | 90 |
| Tests with an execution status (Passed + Failed + Blocked) | 86 of 90 |
| Passed | 79 |
| Failed | 5 |
| Blocked | 2 |
| Not Executed | 4 |
| Execution Progress | 95.6% |
| Pass Rate | 94.0% |

**Calculations:**

- Execution Progress: `(79 + 5 + 2) / 90 × 100 = 95.6%`
- Pass Rate: `79 / (79 + 5) × 100 = 94.0%`

### 6.3 Top Three Risks

| Risk | Evidence from the Source Reports | Impact |
|---|---|---|
| Four High-severity defects remain Open | `DEF-S5-001`, `DEF-S5-005`, `DEF-S5-008`, and `DEF-S5-011` remain Open on `day05`. They affect payment redirection, checkout language switching, delivery pricing, and invoice API access. | The high Execution Progress does not demonstrate that these significant product risks have been resolved. |
| Remaining Blocked and Not Executed tests | On `day05`, 2 Blocked and 4 Not Executed tests remain in `US4200-delivery-costs`, `US1001-playwright-guide`, and `US4510-regression`. `US4200` alone contains 1 Blocked and 3 Not Executed tests, as well as the Open High-severity defect `DEF-S5-008`. | The remaining gaps reduce test coverage and create uncertainty regarding sprint exit readiness. |
| Ambiguous defect references | `DEF-S5-003`, `DEF-S5-004`, and `DEF-S5-005` are used with different summaries, related stories, and, in some cases, different severity values. | The ambiguity may result in incorrect trend analysis, incorrect prioritisation, or retesting against the wrong defect. |

The underlying evidence is documented in the [collected monitoring log excerpts](G114-supporting-files/01_Monitoring_Log_Excerpts_day03-day05.md).

### 6.4 Recommended Test-Control Actions

#### Action 1: Prioritise High-severity defects and perform targeted retesting

`DEF-S5-001`, `DEF-S5-005`, `DEF-S5-008`, and `DEF-S5-011` should be analysed and resolved as a priority. After a fix is reported, the affected test suites and relevant regression coverage should be executed again. Before retesting `DEF-S5-005`, its correct assignment must be confirmed using its Summary, Severity, and Related Story.

**Rationale:** All four High-severity defects remain Open throughout the monitoring window. Resolving them is therefore more important for exit readiness than further improvement of the overall execution rate.

#### Action 2: Concentrate test capacity on the remaining B/NE suites

Available test capacity should be concentrated on `US4200-delivery-costs`, `US1001-playwright-guide`, and `US4510-regression`. The causes of the two Blocked tests should be clarified, and the four Not Executed tests should be completed.

**Rationale:** These three test suites contain all remaining Blocked and Not Executed tests on `day05`. `US4200` alone accounts for four of the six outstanding test results and also contains the Open High-severity defect `DEF-S5-008`.

### 6.5 Lessons Learned

For future sprints, the calculation rules for metrics such as Execution Progress and Pass Rate should be defined before monitoring begins. In addition, Defect IDs should be unique and contain consistent Summary, Severity, and Related Story information. This would reduce manual corrections and improve the reliability of AI-assisted monitoring reports.