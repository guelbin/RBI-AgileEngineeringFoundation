# Validated Monitoring Report — ToolShop Holtesting

**Monitoring window:** `day03`, `day04`, `day05`  
**Source:** `Monitoring_Logauszuege_day03-day05.md`  
**Scope:** 15 test suites per day; 90 planned tests per day

## 1. Stakeholder Summary

Test progress improved substantially during the monitoring window. Execution Progress increased from 87.8% on `day03` to 94.4% on `day04` and 95.6% on `day05`. At the same time, the number of Passed tests increased from 65 to 79. The combined number of Blocked and Not Executed tests decreased from 16 to 6.

Result quality did not improve consistently throughout the window. Although more tests were executed on `day04`, the number of Failed tests increased from 9 to 12 and the Pass Rate decreased from 87.8% to 85.4%. On `day05`, the Pass Rate improved to 94.0%, while Failed decreased to 5, Blocked to 2, and Not Executed to 4.

Despite the positive overall trend, four defect ID strings recorded as High remained Open on all three days: `DEF-S5-001`, `DEF-S5-005`, `DEF-S5-008`, and `DEF-S5-011`. However, `DEF-S5-005` is an **Ambiguous Defect Reference**, because the same ID is also used with a different summary and Medium severity. In addition, six tests remained blocked or not executed across three suites on `day05`: 2 Blocked and 4 Not Executed. Whether this formally violates the sprint exit criteria is **Not clearly derivable from the source**, because no exit thresholds are provided.

## 2. Daily Totals

| Day | Planned | Passed | Failed | Blocked | Not Executed | Execution Progress | Pass Rate |
|---|---:|---:|---:|---:|---:|---:|---:|
| `day03` | 90 | 65 | 9 | 5 | 11 | 87.8% | 87.8% |
| `day04` | 90 | 70 | 12 | 3 | 5 | 94.4% | 85.4% |
| `day05` | 90 | 79 | 5 | 2 | 4 | 95.6% | 94.0% |

**Applied formulas**

- Planned = Passed + Failed + Blocked + Not Executed.
- Execution Progress = (Passed + Failed + Blocked) / Planned × 100.
- Pass Rate = Passed / (Passed + Failed) × 100. Blocked and Not Executed are excluded from the denominator.
- All percentages are rounded to one decimal place.

**Development across the monitoring window**

- `day03` → `day04`: Execution Progress +6.7 percentage points; Passed +5; Failed +3; Blocked −2; Not Executed −6; Pass Rate −2.5 percentage points.
- `day04` → `day05`: Execution Progress +1.1 percentage points; Passed +9; Failed −7; Blocked −1; Not Executed −1; Pass Rate +8.7 percentage points.
- `day03` → `day05`: Execution Progress +7.8 percentage points; Passed +14; Failed −4; Blocked −3; Not Executed −7; Pass Rate +6.2 percentage points.

## 3. Suite-Level Metrics

### day03

| Test Suite | Planned | Passed | Failed | Blocked | Not Executed | Execution Progress | Pass Rate | Risk Flag |
|---|---:|---:|---:|---:|---:|---:|---:|---|
| `US2300-czech-language` | 8 | 7 | 0 | 0 | 1 | 87.5% | 100.0% | AT RISK: B=0, NE=1; Open High: DEF-S5-005 (ambiguous); Ambiguous Defect Reference: DEF-S5-005 |
| `US2350-czech-products` | 8 | 6 | 2 | 0 | 0 | 100.0% | 75.0% | Failed=2 |
| `US3100-payu-payment` | 9 | 7 | 1 | 1 | 0 | 100.0% | 87.5% | AT RISK: B=1, NE=0; Failed=1; Open High: DEF-S5-001 |
| `US4200-delivery-costs` | 9 | 3 | 0 | 1 | 5 | 44.4% | 100.0% | AT RISK: B=1, NE=5; Open High: DEF-S5-008; Ambiguous Defect Reference: DEF-S5-003 |
| `US1007-new-logo` | 5 | 4 | 1 | 0 | 0 | 100.0% | 80.0% | Failed=1 |
| `US1008-remove-rentals` | 5 | 5 | 0 | 0 | 0 | 100.0% | 100.0% | No B/NE, Failed, High, or ambiguity flag |
| `US4350-version-number` | 5 | 3 | 2 | 0 | 0 | 100.0% | 60.0% | Failed=2; Ambiguous Defect Reference: DEF-S5-004 |
| `US1022-compliance-ready` | 5 | 5 | 0 | 0 | 0 | 100.0% | 100.0% | No B/NE, Failed, High, or ambiguity flag |
| `US1001-playwright-guide` | 3 | 0 | 1 | 2 | 0 | 100.0% | 0.0% | AT RISK: B=2, NE=0; Failed=1; Ambiguous Defect Reference: DEF-S5-003 |
| `US1003-angular-guide` | 3 | 3 | 0 | 0 | 0 | 100.0% | 100.0% | No B/NE, Failed, High, or ambiguity flag |
| `US4510-regression` | 10 | 6 | 1 | 0 | 3 | 70.0% | 85.7% | AT RISK: B=0, NE=3; Failed=1; Open High: DEF-S5-001, DEF-S5-008; Ambiguous Defect Reference: DEF-S5-003 |
| `CHK-checkout-e2e` | 5 | 4 | 0 | 0 | 1 | 80.0% | 100.0% | AT RISK: B=0, NE=1 |
| `API-api-security` | 5 | 5 | 0 | 0 | 0 | 100.0% | 100.0% | Open High: DEF-S5-011 |
| `SMK-smoke-sanity` | 5 | 4 | 0 | 0 | 1 | 80.0% | 100.0% | AT RISK: B=0, NE=1 |
| `XBR-cross-browser` | 5 | 3 | 1 | 1 | 0 | 100.0% | 75.0% | AT RISK: B=1, NE=0; Failed=1 |

### day04

| Test Suite | Planned | Passed | Failed | Blocked | Not Executed | Execution Progress | Pass Rate | Risk Flag |
|---|---:|---:|---:|---:|---:|---:|---:|---|
| `US2300-czech-language` | 8 | 8 | 0 | 0 | 0 | 100.0% | 100.0% | Open High: DEF-S5-005 (ambiguous); Ambiguous Defect Reference: DEF-S5-005 |
| `US2350-czech-products` | 8 | 6 | 2 | 0 | 0 | 100.0% | 75.0% | Failed=2 |
| `US3100-payu-payment` | 9 | 6 | 2 | 1 | 0 | 100.0% | 75.0% | AT RISK: B=1, NE=0; Failed=2; Open High: DEF-S5-001 |
| `US4200-delivery-costs` | 9 | 4 | 0 | 1 | 4 | 55.6% | 100.0% | AT RISK: B=1, NE=4; Open High: DEF-S5-008; Ambiguous Defect Reference: DEF-S5-003 |
| `US1007-new-logo` | 5 | 4 | 1 | 0 | 0 | 100.0% | 80.0% | Failed=1 |
| `US1008-remove-rentals` | 5 | 5 | 0 | 0 | 0 | 100.0% | 100.0% | No B/NE, Failed, High, or ambiguity flag |
| `US4350-version-number` | 5 | 3 | 2 | 0 | 0 | 100.0% | 60.0% | Failed=2; Ambiguous Defect Reference: DEF-S5-004 |
| `US1022-compliance-ready` | 5 | 5 | 0 | 0 | 0 | 100.0% | 100.0% | No B/NE, Failed, High, or ambiguity flag |
| `US1001-playwright-guide` | 3 | 0 | 2 | 1 | 0 | 100.0% | 0.0% | AT RISK: B=1, NE=0; Failed=2; Ambiguous Defect Reference: DEF-S5-004 |
| `US1003-angular-guide` | 3 | 3 | 0 | 0 | 0 | 100.0% | 100.0% | No B/NE, Failed, High, or ambiguity flag |
| `US4510-regression` | 10 | 8 | 1 | 0 | 1 | 90.0% | 88.9% | AT RISK: B=0, NE=1; Failed=1; Open High: DEF-S5-001, DEF-S5-008; Ambiguous Defect Reference: DEF-S5-003 |
| `CHK-checkout-e2e` | 5 | 5 | 0 | 0 | 0 | 100.0% | 100.0% | No B/NE, Failed, High, or ambiguity flag |
| `API-api-security` | 5 | 5 | 0 | 0 | 0 | 100.0% | 100.0% | Open High: DEF-S5-011 |
| `SMK-smoke-sanity` | 5 | 5 | 0 | 0 | 0 | 100.0% | 100.0% | No B/NE, Failed, High, or ambiguity flag |
| `XBR-cross-browser` | 5 | 3 | 2 | 0 | 0 | 100.0% | 60.0% | Failed=2 |

### day05

| Test Suite | Planned | Passed | Failed | Blocked | Not Executed | Execution Progress | Pass Rate | Risk Flag |
|---|---:|---:|---:|---:|---:|---:|---:|---|
| `US2300-czech-language` | 8 | 8 | 0 | 0 | 0 | 100.0% | 100.0% | Open High: DEF-S5-005 (ambiguous); Ambiguous Defect Reference: DEF-S5-005 |
| `US2350-czech-products` | 8 | 7 | 1 | 0 | 0 | 100.0% | 87.5% | Failed=1 |
| `US3100-payu-payment` | 9 | 8 | 1 | 0 | 0 | 100.0% | 88.9% | Failed=1; Open High: DEF-S5-001 |
| `US4200-delivery-costs` | 9 | 5 | 0 | 1 | 3 | 66.7% | 100.0% | AT RISK: B=1, NE=3; Open High: DEF-S5-008; Ambiguous Defect Reference: DEF-S5-003 |
| `US1007-new-logo` | 5 | 5 | 0 | 0 | 0 | 100.0% | 100.0% | No B/NE, Failed, High, or ambiguity flag |
| `US1008-remove-rentals` | 5 | 5 | 0 | 0 | 0 | 100.0% | 100.0% | No B/NE, Failed, High, or ambiguity flag |
| `US4350-version-number` | 5 | 4 | 1 | 0 | 0 | 100.0% | 80.0% | Failed=1; Ambiguous Defect Reference: DEF-S5-004 |
| `US1022-compliance-ready` | 5 | 5 | 0 | 0 | 0 | 100.0% | 100.0% | No B/NE, Failed, High, or ambiguity flag |
| `US1001-playwright-guide` | 3 | 1 | 1 | 1 | 0 | 100.0% | 50.0% | AT RISK: B=1, NE=0; Failed=1; Ambiguous Defect Reference: DEF-S5-005 |
| `US1003-angular-guide` | 3 | 3 | 0 | 0 | 0 | 100.0% | 100.0% | No B/NE, Failed, High, or ambiguity flag |
| `US4510-regression` | 10 | 9 | 0 | 0 | 1 | 90.0% | 100.0% | AT RISK: B=0, NE=1; Open High: DEF-S5-001, DEF-S5-008; Ambiguous Defect Reference: DEF-S5-003 |
| `CHK-checkout-e2e` | 5 | 5 | 0 | 0 | 0 | 100.0% | 100.0% | No B/NE, Failed, High, or ambiguity flag |
| `API-api-security` | 5 | 5 | 0 | 0 | 0 | 100.0% | 100.0% | Open High: DEF-S5-011 |
| `SMK-smoke-sanity` | 5 | 5 | 0 | 0 | 0 | 100.0% | 100.0% | No B/NE, Failed, High, or ambiguity flag |
| `XBR-cross-browser` | 5 | 4 | 1 | 0 | 0 | 100.0% | 80.0% | Failed=1 |

## 4. Defect Trend Overview

| Day | Unique Open Defect IDs | New IDs vs Previous Day | Recurring IDs vs Previous Day | Unique Open High IDs |
|---|---:|---|---|---:|
| `day03` | 15 | Not clearly derivable from the source (baseline) | Not clearly derivable from the source (baseline) | 4 |
| `day04` | 15 | 0 | 15 ID strings, including 3 ambiguous IDs in the full window | 4 |
| `day05` | 15 | 0 | 15 ID strings, including 3 ambiguous IDs in the full window | 4 |

No new ID string appears after the `day03` baseline. All 15 ID strings recorded on `day03` also occur on `day04` and `day05` and remain Open in the respective tables. However, only 12 IDs can be used as unambiguous defect-trend evidence. `DEF-S5-003`, `DEF-S5-004`, and `DEF-S5-005` are **Ambiguous Defect References** because their metadata is inconsistent.

### Ambiguous Defect References

| Defect ID | Source Variant 1 | Source Variant 2 | Assessment |
|---|---|---|---|
| `DEF-S5-003` | Medium; “Zásilkovna shown for US shipping address”; US4200; Open (`US4200-delivery-costs`, `US4510-regression`) | Medium; “Failure in Playwright Test Guide”; US1001; Open (`US1001-playwright-guide`, `day03`) | Ambiguous Defect Reference — different Summary and Related Story |
| `DEF-S5-004` | Low; “Build date format inconsistent in footer”; US4350; Open (`US4350-version-number`) | Medium; “Failure in Playwright Test Guide”; US1001; Open (`US1001-playwright-guide`, `day04`) | Ambiguous Defect Reference — different Summary, Severity, and Related Story |
| `DEF-S5-005` | High; “Language switcher missing on checkout page”; US2300; Open (`US2300-czech-language`) | Medium; “Failure in Playwright Test Guide”; US1001; Open (`US1001-playwright-guide`, `day05`) | Ambiguous Defect Reference — different Summary, Severity, and Related Story |

### Unresolved High-Severity Defects

| Defect ID | High-Severity Summary | Related Story | Status `day03` | Status `day04` | Status `day05` | Reference Assessment |
|---|---|---|---|---|---|---|
| `DEF-S5-001` | PayU redirect returns 502 on holtesting staging | US3100 | Open | Open | Open | Consistent metadata; referenced in US3100 and US4510 |
| `DEF-S5-005` | Language switcher missing on checkout page | US2300 | Open | Open | Open | **Ambiguous Defect Reference**: the same ID also appears on `day05` as Medium with a different Summary and Story |
| `DEF-S5-008` | Heavy delivery tier applied at 9.9 kg | US4200 | Open | Open | Open | Consistent metadata; referenced in US4200 and US4510 |
| `DEF-S5-011` | API invoices endpoint returns all users invoices | API | Open | Open | Open | Consistent metadata; referenced in API |

## 5. At-Risk Test Suites

A suite is flagged when it contains at least one Blocked or Not Executed test.

| Day | Test Suite | Blocked | Not Executed |
|---|---|---:|---:|
| `day03` | `US2300-czech-language` | 0 | 1 |
| `day03` | `US3100-payu-payment` | 1 | 0 |
| `day03` | `US4200-delivery-costs` | 1 | 5 |
| `day03` | `US1001-playwright-guide` | 2 | 0 |
| `day03` | `US4510-regression` | 0 | 3 |
| `day03` | `CHK-checkout-e2e` | 0 | 1 |
| `day03` | `SMK-smoke-sanity` | 0 | 1 |
| `day03` | `XBR-cross-browser` | 1 | 0 |
| `day04` | `US3100-payu-payment` | 1 | 0 |
| `day04` | `US4200-delivery-costs` | 1 | 4 |
| `day04` | `US1001-playwright-guide` | 1 | 0 |
| `day04` | `US4510-regression` | 0 | 1 |
| `day05` | `US4200-delivery-costs` | 1 | 3 |
| `day05` | `US1001-playwright-guide` | 1 | 0 |
| `day05` | `US4510-regression` | 0 | 1 |

| Day | Flagged Suites | Total Blocked | Total Not Executed |
|---|---:|---:|---:|
| `day03` | 8 | 5 | 11 |
| `day04` | 4 | 3 | 5 |
| `day05` | 3 | 2 | 4 |

On `day05`, the 4 Not Executed tests are distributed across `US4200-delivery-costs` (3) and `US4510-regression` (1). The 2 Blocked tests are in `US4200-delivery-costs` (1) and `US1001-playwright-guide` (1).

## 6. Exactly Two Test-Control Actions

### Action 1: Prioritise High-severity defects and perform targeted retesting

Prioritise `DEF-S5-001`, `DEF-S5-005`, `DEF-S5-008`, and `DEF-S5-011`. After a fix is reported, rerun the affected suites and the relevant regression tests. For `DEF-S5-005`, the association must first be checked against Summary, Severity, and Related Story because it is an Ambiguous Defect Reference.

**Rationale:** All four High defect ID strings are recorded as Open on `day03`, `day04`, and `day05`. According to the source, they affect payment redirection, checkout language switching, delivery pricing, and invoice API access. Improved Execution Progress does not remove these documented High-severity risks.

### Action 2: Concentrate execution capacity on the three remaining B/NE suites

Concentrate available test capacity on `US4200-delivery-costs`, `US1001-playwright-guide`, and `US4510-regression` until the 2 Blocked and 4 Not Executed tests remaining on `day05` receive conclusive results.

**Rationale:** These three suites contain all remaining execution gaps on `day05`. `US4200-delivery-costs` alone contains 1 Blocked and 3 Not Executed tests and also references the Open High-severity defect `DEF-S5-008`. Closing this concentrated gap addresses the largest uncertainty supported by the execution metrics.

## 7. Quality Control

| Check | Result |
|---|---|
| Files processed | 15 for `day03`, 15 for `day04`, and 15 for `day05`; 45 in total |
| Suite-level vs daily totals | Verified; all totals reconcile |
| Formulas | Applied as specified; no suite has Passed + Failed = 0 |
| Defect metadata | ID, Summary, Severity, Related Story, and Status checked against the source |
| Ambiguous references | `DEF-S5-003`, `DEF-S5-004`, and `DEF-S5-005` explicitly marked as Ambiguous Defect References |
| Number of test-control actions | Exactly 2 |
