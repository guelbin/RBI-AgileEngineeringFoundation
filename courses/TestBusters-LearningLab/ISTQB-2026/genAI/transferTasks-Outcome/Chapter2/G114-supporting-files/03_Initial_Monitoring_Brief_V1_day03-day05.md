# ToolShop Holtesting Sprint — Monitoring Brief

**Monitoring window:** `day03`–`day05`  
**Scope:** 15 test suites per day; 90 planned tests per day

## 1. Stakeholder Summary

Test progress improved across the monitoring window. Attempted execution increased from 79 of 90 planned tests (87.8%) on `day03` to 86 of 90 (95.6%) on `day05`. Passed tests increased from 65 to 79, while the combined Blocked and Not Executed backlog fell from 16 to 6.

The trend was not uniformly positive: Failed tests rose from 9 on `day03` to 12 on `day04`, before dropping to 5 on `day05`. The planned-basis pass rate improved from 72.2% to 87.8% over the full window. However, fo
ur unique High-severity defects remained Open on all three days, and `day05` still contained 2 Blocked and 4 Not Executed tests. The source does not define numerical sprint exit thresholds; therefore, formal exit-criteria compliance cannot be confirmed from this monitoring window alone.

## 2. Daily Sprint-Level Metrics Table

| Day | Total / Planned | Passed | Failed | Blocked | Not Executed | Execution Progress | Pass Rate |
|---|---:|---:|---:|---:|---:|---:|---:|
| `day03` | 90 | 65 | 9 | 5 | 11 | 87.8% | 72.2% |
| `day04` | 90 | 70 | 12 | 3 | 5 | 94.4% | 77.8% |
| `day05` | 90 | 79 | 5 | 2 | 4 | 95.6% | 87.8% |

**Calculation basis**

- Execution Progress = (Passed + Failed + Blocked) / Total Planned.
- Pass Rate = Passed / Total Planned. This planned-basis rate shows how much of the full daily scope has reached a Passed result.

**Change across the window**

- `day03` → `day04`: execution progress increased by 6.7 percentage points and Passed increased by 5, but Failed also increased by 3.
- `day04` → `day05`: Passed increased by 9, Failed decreased by 7, Blocked decreased by 1, and Not Executed decreased by 1.
- `day03` → `day05`: Passed increased by 14; Failed, Blocked, and Not Executed decreased by 4, 3, and 7 respectively. Execution progress increased by 7.8 percentage points and pass rate by 15.6 percentage points.

## 3. Suite-Level Progress and Risks

### day03

| Test Suite | Planned | Passed | Failed | Blocked | Not Executed | Execution Progress | Pass Rate | Risk Flag |
|---|---:|---:|---:|---:|---:|---:|---:|---|
| `US2300-czech-language` | 8 | 7 | 0 | 0 | 1 | 87.5% | 87.5% | High defect open; 1 not executed |
| `US2350-czech-products` | 8 | 6 | 2 | 0 | 0 | 100.0% | 75.0% | 2 failed |
| `US3100-payu-payment` | 9 | 7 | 1 | 1 | 0 | 100.0% | 77.8% | High defect open; 1 failed; 1 blocked |
| `US4200-delivery-costs` | 9 | 3 | 0 | 1 | 5 | 44.4% | 33.3% | High defect open; 1 blocked; 5 not executed |
| `US1007-new-logo` | 5 | 4 | 1 | 0 | 0 | 100.0% | 80.0% | 1 failed |
| `US1008-remove-rentals` | 5 | 5 | 0 | 0 | 0 | 100.0% | 100.0% | No failed/blocked/not-executed or High-defect flag |
| `US4350-version-number` | 5 | 3 | 2 | 0 | 0 | 100.0% | 60.0% | 2 failed |
| `US1022-compliance-ready` | 5 | 5 | 0 | 0 | 0 | 100.0% | 100.0% | No failed/blocked/not-executed or High-defect flag |
| `US1001-playwright-guide` | 3 | 0 | 1 | 2 | 0 | 100.0% | 0.0% | 1 failed; 2 blocked |
| `US1003-angular-guide` | 3 | 3 | 0 | 0 | 0 | 100.0% | 100.0% | No failed/blocked/not-executed or High-defect flag |
| `US4510-regression` | 10 | 6 | 1 | 0 | 3 | 70.0% | 60.0% | High defect open; 1 failed; 3 not executed |
| `CHK-checkout-e2e` | 5 | 4 | 0 | 0 | 1 | 80.0% | 80.0% | 1 not executed |
| `API-api-security` | 5 | 5 | 0 | 0 | 0 | 100.0% | 100.0% | High defect open |
| `SMK-smoke-sanity` | 5 | 4 | 0 | 0 | 1 | 80.0% | 80.0% | 1 not executed |
| `XBR-cross-browser` | 5 | 3 | 1 | 1 | 0 | 100.0% | 60.0% | 1 failed; 1 blocked |

### day04

| Test Suite | Planned | Passed | Failed | Blocked | Not Executed | Execution Progress | Pass Rate | Risk Flag |
|---|---:|---:|---:|---:|---:|---:|---:|---|
| `US2300-czech-language` | 8 | 8 | 0 | 0 | 0 | 100.0% | 100.0% | High defect open |
| `US2350-czech-products` | 8 | 6 | 2 | 0 | 0 | 100.0% | 75.0% | 2 failed |
| `US3100-payu-payment` | 9 | 6 | 2 | 1 | 0 | 100.0% | 66.7% | High defect open; 2 failed; 1 blocked |
| `US4200-delivery-costs` | 9 | 4 | 0 | 1 | 4 | 55.6% | 44.4% | High defect open; 1 blocked; 4 not executed |
| `US1007-new-logo` | 5 | 4 | 1 | 0 | 0 | 100.0% | 80.0% | 1 failed |
| `US1008-remove-rentals` | 5 | 5 | 0 | 0 | 0 | 100.0% | 100.0% | No failed/blocked/not-executed or High-defect flag |
| `US4350-version-number` | 5 | 3 | 2 | 0 | 0 | 100.0% | 60.0% | 2 failed |
| `US1022-compliance-ready` | 5 | 5 | 0 | 0 | 0 | 100.0% | 100.0% | No failed/blocked/not-executed or High-defect flag |
| `US1001-playwright-guide` | 3 | 0 | 2 | 1 | 0 | 100.0% | 0.0% | 2 failed; 1 blocked |
| `US1003-angular-guide` | 3 | 3 | 0 | 0 | 0 | 100.0% | 100.0% | No failed/blocked/not-executed or High-defect flag |
| `US4510-regression` | 10 | 8 | 1 | 0 | 1 | 90.0% | 80.0% | High defect open; 1 failed; 1 not executed |
| `CHK-checkout-e2e` | 5 | 5 | 0 | 0 | 0 | 100.0% | 100.0% | No failed/blocked/not-executed or High-defect flag |
| `API-api-security` | 5 | 5 | 0 | 0 | 0 | 100.0% | 100.0% | High defect open |
| `SMK-smoke-sanity` | 5 | 5 | 0 | 0 | 0 | 100.0% | 100.0% | No failed/blocked/not-executed or High-defect flag |
| `XBR-cross-browser` | 5 | 3 | 2 | 0 | 0 | 100.0% | 60.0% | 2 failed |

### day05

| Test Suite | Planned | Passed | Failed | Blocked | Not Executed | Execution Progress | Pass Rate | Risk Flag |
|---|---:|---:|---:|---:|---:|---:|---:|---|
| `US2300-czech-language` | 8 | 8 | 0 | 0 | 0 | 100.0% | 100.0% | High defect open |
| `US2350-czech-products` | 8 | 7 | 1 | 0 | 0 | 100.0% | 87.5% | 1 failed |
| `US3100-payu-payment` | 9 | 8 | 1 | 0 | 0 | 100.0% | 88.9% | High defect open; 1 failed |
| `US4200-delivery-costs` | 9 | 5 | 0 | 1 | 3 | 66.7% | 55.6% | High defect open; 1 blocked; 3 not executed |
| `US1007-new-logo` | 5 | 5 | 0 | 0 | 0 | 100.0% | 100.0% | No failed/blocked/not-executed or High-defect flag |
| `US1008-remove-rentals` | 5 | 5 | 0 | 0 | 0 | 100.0% | 100.0% | No failed/blocked/not-executed or High-defect flag |
| `US4350-version-number` | 5 | 4 | 1 | 0 | 0 | 100.0% | 80.0% | 1 failed |
| `US1022-compliance-ready` | 5 | 5 | 0 | 0 | 0 | 100.0% | 100.0% | No failed/blocked/not-executed or High-defect flag |
| `US1001-playwright-guide` | 3 | 1 | 1 | 1 | 0 | 100.0% | 33.3% | 1 failed; 1 blocked |
| `US1003-angular-guide` | 3 | 3 | 0 | 0 | 0 | 100.0% | 100.0% | No failed/blocked/not-executed or High-defect flag |
| `US4510-regression` | 10 | 9 | 0 | 0 | 1 | 90.0% | 90.0% | High defect open; 1 not executed |
| `CHK-checkout-e2e` | 5 | 5 | 0 | 0 | 0 | 100.0% | 100.0% | No failed/blocked/not-executed or High-defect flag |
| `API-api-security` | 5 | 5 | 0 | 0 | 0 | 100.0% | 100.0% | High defect open |
| `SMK-smoke-sanity` | 5 | 5 | 0 | 0 | 0 | 100.0% | 100.0% | No failed/blocked/not-executed or High-defect flag |
| `XBR-cross-browser` | 5 | 4 | 1 | 0 | 0 | 100.0% | 80.0% | 1 failed |

**Suites with Blocked or Not Executed tests that may threaten exit readiness**

| Day | Flagged Suites | Count |
|---|---|---:|
| `day03` | `US2300-czech-language` (0 B, 1 NE); `US3100-payu-payment` (1 B, 0 NE); `US4200-delivery-costs` (1 B, 5 NE); `US1001-playwright-guide` (2 B, 0 NE); `US4510-regression` (0 B, 3 NE); `CHK-checkout-e2e` (0 B, 1 NE); `SMK-smoke-sanity` (0 B, 1 NE); `XBR-cross-browser` (1 B, 0 NE) | 8 |
| `day04` | `US3100-payu-payment` (1 B, 0 NE); `US4200-delivery-costs` (1 B, 4 NE); `US1001-playwright-guide` (1 B, 0 NE); `US4510-regression` (0 B, 1 NE) | 4 |
| `day05` | `US4200-delivery-costs` (1 B, 3 NE); `US1001-playwright-guide` (1 B, 0 NE); `US4510-regression` (0 B, 1 NE) | 3 |

By `day05`, the remaining execution gap was concentrated in three suites: `US4200-delivery-costs` (1 Blocked, 3 Not Executed), `US1001-playwright-guide` (1 Blocked), and `US4510-regression` (1 Not Executed). `US4200-delivery-costs` is the largest direct coverage gap and also reports an Open High-severity defect. Open High-severity defects also remain in `US2300-czech-language`, `US3100-payu-payment`, `US4510-regression`, and `API-api-security`, even where the suite itself has no remaining Blocked or Not Executed tests.

## 4. Defect Trends

| Day | Unique Open Defect IDs | New IDs vs Previous Day | Recurring IDs vs Previous Day | Unique Open High IDs |
|---|---:|---:|---:|---:|
| `day03` | 15 | Baseline — no earlier day in source | Baseline — no earlier day in source | 4 |
| `day04` | 15 | 0 | 15 | 4 |
| `day05` | 15 | 0 | 15 | 4 |

No new unique defect ID appears after the `day03` baseline. All 15 unique IDs recorded on `day03` recur on both `day04` and `day05`, and every listed status remains Open. The source provides no pre-`day03` data, so the 15 baseline IDs cannot be classified as newly discovered during this window.

**Unresolved High-severity defects**

| Defect ID | Summary | Related Story | Seen in Window | Status on `day05` |
|---|---|---|---|---|
| `DEF-S5-001` | PayU redirect returns 502 on holtesting staging | US3100 | `day03`, `day04`, `day05` | Open |
| `DEF-S5-005` | Language switcher missing on checkout page | US2300 | `day03`, `day04`, `day05` | Open |
| `DEF-S5-008` | Heavy delivery tier applied at 9.9 kg | US4200 | `day03`, `day04`, `day05` | Open |
| `DEF-S5-011` | API invoices endpoint returns all users invoices | API | `day03`, `day04`, `day05` | Open |

**Traceability note:** The source reuses `DEF-S5-003`, `DEF-S5-004`, and `DEF-S5-005` in the `US1001-playwright-guide` suite with the summary “Failure in Playwright Test Guide”, while the same IDs are associated elsewhere with different summaries and, for `DEF-S5-005`, a different severity. The trend counts above therefore use unique IDs exactly as recorded, but those three cross-suite references are ambiguous.

## 5. Two Recommended Test-Control Actions

### 1. Reprioritise High-severity defect resolution and targeted retesting

Prioritise `DEF-S5-001`, `DEF-S5-005`, `DEF-S5-008`, and `DEF-S5-011`, then retest their affected suites and the relevant regression coverage after fixes are available.

**Rationale:** All four High-severity IDs remain Open throughout the three-day window. They affect payment redirection, checkout language support, delivery pricing, and invoice API access. The persistence of these defects is a stronger exit-readiness concern than the improved aggregate pass rate, because completed test execution does not demonstrate that these High-severity product risks have been removed.

### 2. Reassign execution capacity to clear the remaining Blocked and Not Executed backlog

Concentrate available executors on `US4200-delivery-costs`, `US1001-playwright-guide`, and `US4510-regression` until the 2 Blocked and 4 Not Executed tests recorded on `day05` receive conclusive results.

**Rationale:** These three suites contain the entire remaining `day05` execution gap. `US4200-delivery-costs` alone accounts for four of the six outstanding tests and also carries the recurring High-severity `DEF-S5-008`. Clearing this concentrated backlog reduces the largest remaining uncertainty against sprint exit readiness.
