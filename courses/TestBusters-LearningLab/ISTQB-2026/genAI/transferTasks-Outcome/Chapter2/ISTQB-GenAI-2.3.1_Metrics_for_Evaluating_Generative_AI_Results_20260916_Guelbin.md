### Title
Define and Apply Metrics for AI-Generated Test Artifacts

---

### Syllabus Reference
ISTQB GenAI – 2.3.1 Metrics for Evaluating Generative AI Results

---
## Link to the Transfer Task File

[G117 – GenAI 2.3.1 – Metrics for Evaluating Generative AI Results](https://github.com/rgroetz2/TBLL-AgileEngineeringFoundation/blob/main/courses/TestBusters-LearningLab/ISTQB-2026/genAI/transferTasks/Chapter2/ISTQB-GenAI-2.3.1_Metrics_for_Evaluating_Generative_AI_Results_20260405.md)

---

# OUTCOME

## 1. Evaluation Framework

### 1.1 Correctness

**Definition:** Evaluates whether the information in the test artifact correctly corresponds to the requirements, acceptance criteria, and source data.

| **Score** | **Description** |
|---:|---|
| **1** | The result contains many significant errors and is not usable. |
| **2** | The result contains several important errors; extensive corrections are required. |
| **3** | The result is mostly correct but contains some relevant errors. |
| **4** | The result is almost completely correct; only minor corrections are required. |
| **5** | The result is fully correct and consistent with the requirements, acceptance criteria, and source data. |

### 1.2 Completeness

**Definition:** Evaluates whether all required content, requirements, and components are included in the test artifact.

| **Score** | **Description** |
|---:|---|
| **1** | A large amount of essential content is missing; the result is not usable. |
| **2** | Several important elements are missing; extensive additions are required. |
| **3** | The most important content is present, but some relevant elements are missing. |
| **4** | Almost all required content is present; only a few minor additions are necessary. |
| **5** | All required content is fully included. |

### 1.3 Clarity

**Definition:** Evaluates how clearly, understandably, and logically the content of the test artifact is presented.

| **Score** | **Description** |
|---:|---|
| **1** | The result is incomprehensible and unstructured; it cannot be used. |
| **2** | Many statements are unclear; the structure requires substantial revision. |
| **3** | The result is generally understandable but contains some unclear statements or structural weaknesses. |
| **4** | The result is clear and well structured; only a few minor improvements are necessary. |
| **5** | The result is completely clear, unambiguous, and logically structured. |

### 1.4 Traceability

**Definition:** Evaluates whether the content of the test artifact can be clearly linked to the corresponding sources, requirements, or acceptance criteria.

| **Score** | **Description** |
|---:|---|
| **1** | There is no connection to requirements, acceptance criteria, or other sources. |
| **2** | Only a small amount of the content can be linked to a source or requirement. |
| **3** | The most important content is traceable, but some links are missing or unclear. |
| **4** | Almost all content is clearly linked to the corresponding sources or requirements. |
| **5** | All content is fully and unambiguously traceable to the corresponding sources or requirements. |

### 1.5 Actionability

**Definition:** Evaluates whether the test artifact can be directly used and acted upon in practice.

| **Score** | **Description** |
|---:|---|
| **1** | The result cannot be applied in practice; essential information is missing. |
| **2** | The result has limited applicability; extensive adjustments are required. |
| **3** | The result is generally actionable but requires some additions or adjustments. |
| **4** | The result is readily actionable; only minor adjustments are required. |
| **5** | The result can be applied directly and unambiguously without further adjustments. |

## 2. Acceptance Threshold

An AI-generated test artifact is considered acceptable if it achieves at least **18 out of 25 points**. No individual metric may receive fewer than **3 points**.

Because technical correctness is particularly important for test artifacts, the **Correctness** metric must receive at least **4 points**.

## 3. Selected Test Artifact

The first AI-generated result from the transfer task [**G114 – GenAI 2.2.4 – AI-Assisted Test Monitoring and Control for Sprint 5 Holtesting**](https://github.com/rgroetz2/TBLL-AgileEngineeringFoundation/blob/main/courses/TestBusters-LearningLab/ISTQB-2026/genAI/transferTasks-Outcome/Chapter2/ISTQB-GenAI-2.2.4_Test_Monitoring_and_Control_with_Generative_AI_20260827_Guelbin.md) is evaluated as the test artifact.

The selected artifact is the monitoring brief [03_Initial_Monitoring_Brief_V1_day03-day05.md](https://github.com/rgroetz2/TBLL-AgileEngineeringFoundation/blob/main/courses/TestBusters-LearningLab/ISTQB-2026/genAI/transferTasks-Outcome/Chapter2/G114-supporting-files/03_Initial_Monitoring_Brief_V1_day03-day05.md), which was generated using Structured Prompt V1 based on the monitoring log excerpts for `day03` to `day05`.

The following files are used as the evaluation basis:

- [01_Monitoring_Log_Excerpts_day03-day05.md](https://github.com/rgroetz2/TBLL-AgileEngineeringFoundation/blob/main/courses/TestBusters-LearningLab/ISTQB-2026/genAI/transferTasks-Outcome/Chapter2/G114-supporting-files/01_Monitoring_Log_Excerpts_day03-day05.md)
- [02_Structured_Prompt_V1.md](https://github.com/rgroetz2/TBLL-AgileEngineeringFoundation/blob/main/courses/TestBusters-LearningLab/ISTQB-2026/genAI/transferTasks-Outcome/Chapter2/G114-supporting-files/02_Structured_Prompt_V1.md)

Later prompt versions are not included in the primary evaluation of V1. The result generated with Prompt V2 is assessed separately only to verify the effectiveness of the improvement action.

## 4. Evaluation of the AI-Generated Monitoring Brief

| **Metric** | **Score** | **Brief Justification** |
|---|---:|---|
| **Correctness** | **3/5** | Most of the source values were transferred correctly. However, the pass rate was systematically calculated as `Passed / Planned` instead of `Passed / (Passed + Failed)`. As a result, several pass-rate values are incorrect. |
| **Completeness** | **5/5** | The report includes the daily metrics, suite-level results, outstanding execution gaps, defect trends, risks, and two specific test-control actions. |
| **Clarity** | **4/5** | The report is logically organized and easy to understand due to its tables and headings. One incorrect word break and several lengthy statements slightly reduce readability. |
| **Traceability** | **4/5** | The results are largely traceable through references to the test day, test suite, and defect ID. The ambiguous use of individual defect IDs is explicitly identified; however, direct references to the corresponding source locations are missing. |
| **Actionability** | **4/5** | The proposed actions identify specific defect IDs and affected test suites and are generally actionable. Before retesting, however, the ambiguous mapping of `DEF-S5-005` must be verified. |
| **Overall Score** | **20/25** | The overall score exceeds 18 points. Nevertheless, the artifact is not accepted because Correctness received 3 points, which is below the required minimum of 4. |

## 5. Weakest Dimension

The weakest dimension is **Correctness, with 3 out of 5 points**.

The main reason is the pass-rate calculation used throughout the report. Calculating it as `Passed / Planned` produces several incorrect pass-rate values at both sprint and test-suite levels.

## 6. Improvement Action

The calculation rule for the pass rate must be explicitly defined in the prompt as:

`Passed / (Passed + Failed) × 100`

All pass-rate values at sprint and test-suite levels must then be recalculated and manually verified against the source data.

## 7. Validation After the Improvement

To verify the effectiveness of the proposed improvement action, the revised monitoring report [05_Refined_Monitoring_Brief_V2_day03-day05.md](https://github.com/rgroetz2/TBLL-AgileEngineeringFoundation/blob/main/courses/TestBusters-LearningLab/ISTQB-2026/genAI/transferTasks-Outcome/Chapter2/G114-supporting-files/05_Refined_Monitoring_Brief_V2_day03-day05.md) was reviewed using the same evaluation framework.

The revised report was generated using [04_Improved_Structured_Prompt_V2.md](https://github.com/rgroetz2/TBLL-AgileEngineeringFoundation/blob/main/courses/TestBusters-LearningLab/ISTQB-2026/genAI/transferTasks-Outcome/Chapter2/G114-supporting-files/04_Improved_Structured_Prompt_V2.md). The improved prompt explicitly defines the calculation formulas, requires the verification of defect metadata, and includes a quality-control checklist.


| **Metric** | **Score** | **Brief Justification** |
|---|---:|---|
| **Correctness** | **5/5** | The pass rate is correctly calculated as `Passed / (Passed + Failed)`. The daily totals and suite-level values are consistent with the source data. |
| **Completeness** | **5/5** | The report contains all required metrics, defect trends, at-risk test suites, exactly two test-control actions, and a final quality-control section. |
| **Clarity** | **5/5** | The report is clearly structured, the calculation rules are explicitly stated, and the results are presented in well-organized tables. |
| **Traceability** | **5/5** | The results are linked to the corresponding test days, test suites, defect IDs, summaries, severity levels, related stories, and statuses. Ambiguous defect references are explicitly identified. |
| **Actionability** | **5/5** | The two proposed test-control actions identify the affected defect IDs and test suites and clearly describe the required next steps. |
| **Overall Score** | **25/25** | The revised artifact meets all acceptance criteria and is therefore accepted. |

### Validation Result

The revised artifact achieves **25 out of 25 points**. No metric is rated below 3 points, and Correctness achieves the required minimum of 4 points.

The artifact therefore meets the defined acceptance threshold and is **accepted**.

The comparison confirms that explicitly defining the pass-rate formula, strengthening the traceability requirements, and adding a quality-control checklist improved the quality of the AI-generated test artifact.