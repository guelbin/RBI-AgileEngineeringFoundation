# Map Test Levels to CI/CD Pipelines for Toolshop V5

## Title

Map Test Levels to CI/CD Pipelines for Toolshop V5

## Background

The Toolshop team runs a CI/CD pipeline for [https://practicesoftwaretesting.com/](https://practicesoftwaretesting.com/). Today, a full end-to-end checkout suite runs on every commit. Builds are slow, failures are hard to diagnose, and developers lose confidence in pipeline results.

ISTQB TAE section 5.1.1 states that automated tests at different test levels should be integrated into pipelines so that fast, deterministic checks run early and broader checks run later as quality gates. Your task is to redesign the pipeline test distribution for Toolshop.

## Reference

- ISTQB TAE – 5.1.1 Apply Test Automation at Different Test Levels within Pipelines
- Toolshop V5: [https://practicesoftwaretesting.com/](https://practicesoftwaretesting.com/)
- Toolshop API: [https://api.practicesoftwaretesting.com/](https://api.practicesoftwaretesting.com/)
- Swagger documentation: [https://api.practicesoftwaretesting.com/api/documentation](https://api.practicesoftwaretesting.com/api/documentation)
- Architecture documentation: [https://github.com/testsmith-io/practice-software-testing/blob/main/docs/architecture.md](https://github.com/testsmith-io/practice-software-testing/blob/main/docs/architecture.md)
- Test account: `customer@practicesoftwaretesting.com` / `welcome01`

## Tasks

1. Review the syllabus mapping of test levels to pipeline phases: configuration tests, component tests, component integration tests, system tests, and system integration tests.
2. Define four pipeline stages for Toolshop automation: **Build**, **Integration**, **Deployment**, and **Post-deployment**.
3. Complete the table below. For each test level, assign it to one pipeline stage and name **one concrete Toolshop example** (use API endpoints, UI flows, or test-automation-project checks from the references above).


| Test level (syllabus) | Pipeline stage | Concrete Toolshop example | Acts as quality gate? (yes/no) |
| --------------------- | -------------- | ------------------------- | ------------------------------ |
| Configuration test (TAF/TAS) | | | |
| Component test | | | |
| Component integration test | | | |
| System test | | | |
| System integration test | | | |


4. For **system tests** on Toolshop, choose one integration approach from the syllabus and justify your choice in **two sentences**:
   - **Approach A:** Execute tests during the deployment phase (deployment fails or rolls back on test failure).
   - **Approach B:** Trigger a separate pipeline after successful deployment (tests do not gate deployment).
5. Add **one additional pipeline use** from the syllabus (for example: nightly regression or non-functional monitoring). Describe which Toolshop test suite or check would run and how often.
6. Set a **maximum duration target** (in minutes) for the Build and Integration stages combined. Explain in **one sentence** why slow tests must not run in these early stages.

## Expected Outcome

The completed table (task 3), the two-sentence justification for Approach A or B (task 4), the additional pipeline use description (task 5), and the duration target with one-sentence rationale (task 6).

## Original Syllabus K-Level

K3

## Original Syllabus Text

One of the main benefits of test automation is that the implemented tests can run unattended, making them ideal candidates to run within pipelines. This can be accomplished through CI/CD pipelines, or the pipeline used to run the tests regularly.

Test levels are usually integrated as follows:

- **Configuration tests** for TAF/TAS, during build can be considered as a subspecies of component tests. These tests are run during the build of a test automation project (TAF/TAS) and check that all paths to the files used in the test scripts are correct, that the files really exist and are located in the specified paths.
- **Component tests** are part of the build step of the pipeline, as they are executed on the individual components (e.g., library classes, and web components). They act as quality gates for the pipeline, thus a crucial part of a continuous integration pipeline.
- **Component integration tests** can be part of the continuous integration pipeline if they are tests of low-level components or the SUT. In such cases, these tests and the component tests are executed together.
- **System tests** can often be integrated into a continuous deployment pipeline, where they act as the last quality gate of the delivered SUT.
- **System integration tests** between different system components are often part of a continuous delivery pipeline as quality gates. These system integration tests ensure that the separately developed system components are working together.

Many modern continuous integration systems differentiate between build and deployment phases of the continuous delivery pipelines. In these cases, component tests and component integration tests are part of the first build phase. When this first phase is successful (i.e., build and test together), the components/SUT are deployed.

In case of system integration testing, system testing and acceptance testing, there are two main approaches to integrate them into such pipelines:

1. Test cases are executed as part of the deployment phase after the component deployment. This can be beneficial, as based on the test results, the deployment can fail and also be rolled back. However, in this case, if tests need to be rerun, a redeployment needs to be done.
2. Test cases are executed as a separate pipeline, triggered by the successful deployment. This can be beneficial if it is expected that different test suites and various test automation code will run on each deployment. In this case, tests do not act as a quality gate. Thus, it requires other, usually manual, actions to roll back an unsuccessful deployment. In this case, a few simple automated test scripts, as deployment checks, can be used to ensure the SUT is deployed, but these automated test scripts do not verify functional suitability in a broad manner.

Pipelines can also be used for other test automation purposes, such as:

- Running different test suites periodically: A regression test suite can be run every night (i.e., the nightly regression), especially for longer running test suites, so the team will have a clear picture of the quality of the SUT in the morning.
- Running non-functional tests: Either part of a continuous deployment pipeline, or separately, to periodically monitor certain non-functional quality characteristics of the system such as performance efficiency.
