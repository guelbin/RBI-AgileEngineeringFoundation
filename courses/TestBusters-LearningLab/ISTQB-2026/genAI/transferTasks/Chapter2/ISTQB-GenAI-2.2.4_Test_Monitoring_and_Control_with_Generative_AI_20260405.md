- Sprint 5 execution logs: `courses/TestBusters-LearningLab/ISTQB-2026/TTT426-the-testproject/testexecutionTTT426/sprint5-holtesting/`

  - `day01/` … `day10/` — one markdown report per suite (e.g. `03-US3100-payu-payment-execution.md`, `11-US4510-regression-execution.md`, `13-API-api-security-execution.md`)

- Each report contains: execution summary (Passed / Failed / Blocked / Not Executed), open defects, and per-test-case results

**## Tasks**

1. Select a **monitoring window** of three consecutive days `day03`, `day04`, and `day05` recommended). Collect execution summaries and open-defect tables from **all fifteen suite reports** in each selected day folder.

2. Design a **structured prompt** for your GenAI tool. The prompt must instruct the model to:

- Calculate suite-level and sprint-level test progress metrics (totals and pass rate per day)

- Identify defect trends (new, recurring, and unresolved high-severity defects)

- Flag suites with blocked or not-executed tests that threaten the sprint exit criteria

- Propose **two test-control actions** (e.g. reprioritize suites, reassign executors, defer low-risk suites)

- Output a stakeholder-ready natural-language summary **and** a metrics table

3. Submit the collected log excerpts to GenAI and capture the generated monitoring brief.

4. **Verify** every number, defect ID, and trend claim in the AI output against the source reports. Mark each claim as *verified* or *corrected*.

5. Refine the prompt once based on verification findings (e.g. missing blocked-test counts, invented defects, wrong pass-rate formula). Re-run and compare outputs.

6. Deliver a **final validated monitoring brief** for the last day of your window that includes:

- Progress snapshot (executed vs. planned, pass/fail/blocked breakdown)

- Top three risks with evidence from the logs

- Two recommended control actions with rationale

- One lessons-learned note for future sprints

**## Expected Outcome**

A validated sprint monitoring brief for the chosen three-day window, a reusable prompt template for daily test-status reporting, and a short verification log listing AI claims checked against source data (with corrections where needed).

**## Original Syllabus K-Level**

K3

**## Original Syllabus Text**

Test monitoring tasks require the retrieval of large quantities of (sometimes unstructured) data, which are often already available in test management tools that GenAI can help analyze and synthesize.

GenAI facilitates a number of test monitoring and test control tasks, including:

- **Test monitoring and metrics analysis:** GenAI can facilitate the automation of test monitoring, as well as the analysis of trends to predict potential risks and alert teams of any deviations from the plan. This enables teams to remain informed and take action to maintain quality standards.

- **Test control:** GenAI can assist with test control by providing insights for reprioritizing tests, adjusting test schedules, and reallocating resources as needed. This promotes that testing remains flexible and focused on high-priority areas.

- **Test completion insights and continuous learning:** GenAI can assist by generating test completion reports, highlighting successes and lessons learned. This allows teams to refine test strategies and improve future test processes.

- **Enhanced test metrics visualization and reporting:** GenAI can assist in the creation of dynamic dashboards and natural language summaries, ensuring that all stakeholders have access to the relevant metrics. This assistance provides the information needed to make quick decisions and gives a clear view of test progress.