# Define Automation Infrastructure Configuration for Toolshop V6

## Title

Define Automation Infrastructure Configuration for Toolshop V6

## Background

The team plans to automate login and checkout on Toolshop V6 at [https://holtesting.practicesoftwaretesting.com/](https://holtesting.practicesoftwaretesting.com/). Early automation attempts fail because the infrastructure was never configured for testability — selectors are unstable, API behavior is unclear, and environment settings differ between local runs and the hosted instance.

ISTQB TAE section 2.1.1 states that test automation depends on infrastructure configuration that supports **observability**, **controllability**, and **architecture transparency**. Your task is to identify these configuration needs on the live V6 system.

## Reference

- ISTQB TAE – 2.1.1 Describe the Configuration Needs of an Infrastructure that Enable Implementation of Test Automation
- Toolshop V6: [https://holtesting.practicesoftwaretesting.com/](https://holtesting.practicesoftwaretesting.com/)
- Toolshop V6 API: [https://api-holtesting.practicesoftwaretesting.com/](https://api-holtesting.practicesoftwaretesting.com/)
- Swagger documentation: [https://api-holtesting.practicesoftwaretesting.com/api/documentation](https://api-holtesting.practicesoftwaretesting.com/api/documentation)
- Architecture documentation: [https://github.com/testsmith-io/practice-software-testing/blob/main/docs/architecture.md](https://github.com/testsmith-io/practice-software-testing/blob/main/docs/architecture.md)
- Test account: `customer@practicesoftwaretesting.com` / `welcome01`

## Tasks

1. Open the login page at [https://holtesting.practicesoftwaretesting.com/auth/login](https://holtesting.practicesoftwaretesting.com/auth/login). Using browser developer tools, find the `data-test` attribute on the email field and the login submit button. Write down both attribute values.
2. Log in with the test account above. After login, note **one UI element** that confirms success (for example: page title, account menu, or redirect URL).
3. Open the Swagger documentation and locate one authentication-related endpoint (for example: `POST /users/login`). Write the endpoint path and **one response field** an automated test could assert on.
4. Complete the table below — one short answer per cell, using your findings from steps 1–3 where possible.


| Configuration solution (syllabus) | Example on Toolshop V6 | Supports observability or controllability? | One configuration need for automation |
| --------------------------------- | ---------------------- | ------------------------------------------ | ------------------------------------- |
| Accessibility identifiers | | | |
| System environment variables | | | |
| Deployment variables | | | |


5. For each testability aspect below, give **one concrete Toolshop V6 example** from your exploration.


| Testability aspect | Toolshop V6 example |
| ------------------ | ------------------- |
| Observability | |
| Controllability | |
| Architecture transparency | |


6. Write **one sentence** explaining which configuration need you would address first when setting up automation for V6, and why.

## Expected Outcome

The completed tables (steps 4 and 5), the endpoint details from step 3, plus one sentence from step 6.

## Original Syllabus Text

Testability of the SUT (i.e., availability of software interfaces that support testing, e.g., to enable control and observability of the SUT) should be designed and implemented in parallel with the design and implementation of the other features of the SUT. This work is generally performed by a software architect as testability is a non-functional requirement of the system, often with the involvement of a TAE to identify the specific areas where improvements can be made.

For better testability of the SUT there are different solutions that can be utilized which have different configuration needs, for example:

- **Accessibility identifiers** — The different development frameworks can generate these identifiers automatically or the developers can set them manually.
- **System environment variables** — Certain application parameters can be changed to enable easier testing through administration.
- **Deployment variables** — Similar to system variables but can be set before starting deployment.

Designing for testability of a SUT consists of the following aspects:

- **Observability** — The SUT needs to provide interfaces that give insight into the SUT. Test cases can then use these interfaces to determine whether the actual results equal the expected results.
- **Controllability** — The SUT needs to provide interfaces that can be used to perform actions on the SUT. This can be UI elements, function calls, communication elements (e.g., Transmission Control Protocol/Internet Protocol (TCP/IP), and Universal Serial Bus (USB) protocols), or electronic signals for physical or logical switches on the different environment variables.
- **Architecture transparency** — The documentation of an architecture needs to provide clear, understandable components and interfaces that give observability and controllability at all test levels and foster quality.
