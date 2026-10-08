# Create the 42-Vienna Test Policy from Fundamentals of Testing

## 1. Title

Create the 42-Vienna Test Policy from Fundamentals of Testing

## 2. Syllabus Reference

ISTQB FL – 1 Fundamentals of Testing


| Section | Topic                                            |
| ------- | ------------------------------------------------ |
| 1.1     | What is Testing?                                 |
| 1.1.1   | Test Objectives                                  |
| 1.1.2   | Testing and Debugging                            |
| 1.2     | Why is Testing Necessary?                        |
| 1.2.1   | Testing's Contributions to Success               |
| 1.2.2   | Testing and Quality Assurance (QA)               |
| 1.2.3   | Errors, Defects, Failures, and Root Causes       |
| 1.3     | Testing Principles                               |
| 1.4     | Test Activities, Testware and Test Roles         |
| 1.4.1   | Test Activities and Tasks                        |
| 1.4.2   | Test Process in Context                          |
| 1.4.3   | Testware                                         |
| 1.4.4   | Traceability between the Test Basis and Testware |
| 1.4.5   | Roles in Testing                                 |
| 1.5     | Essential Skills and Good Practices in Testing   |
| 1.5.1   | Generic Skills Required for Testing              |
| 1.5.2   | Whole Team Approach                              |
| 1.5.3   | Independence of Testing                          |


## 3. Learning Objective

Apply ISTQB FL Chapter 1 (Fundamentals of Testing) by drafting a **42-Vienna Test Policy** for dedicated **42-Projects** in the 42 curriculum. The policy must translate each syllabus subchapter into concrete guidance for how 42 students develop, test, and validate project work — including validation by other 42 students.

## 4. Context / Scenario

At **42-Vienna**, students work on dedicated **42-Projects** as part of their curriculum. Each project has a published **subject** (requirements, constraints, mandatory deliverables) and a **Submission and peer-evaluation** section. The result of every 42-Project is **validated by other 42 students** before it counts as successfully completed.

Examples of 42-Projects in the curriculum include:


| Project                 | Type              | What students build                                 | Typical test focus                                                       |
| ----------------------- | ----------------- | --------------------------------------------------- | ------------------------------------------------------------------------ |
| **push_swap**           | C / algorithms    | Sort integers on two stacks with minimal operations | Correct output, error handling, `checker` validation, instruction count  |
| **ft_ping**             | C / networking    | Recode the `ping` command                           | ICMP behaviour, forbidden functions, no unexpected crashes               |
| **ft_nmap**             | C / networking    | Partial port scanner (`SYN`, `UDP`, etc.)           | Scan types, thread limits, error handling, no segfaults                  |
| **ft_traceroute**       | C / networking    | Recode `traceroute`                                 | IPv4/FQDN handling, hop tracing, `––help` option                         |
| **webserv**             | C++ / HTTP server | Own HTTP server, tested with a browser              | Request handling, config file, no crash under load or OOM                |
| **ft_irc**              | C++ / networking  | IRC server, tested with an IRC client               | Port/password auth, channels, no unexpected quit                         |
| **Inception-of-Things** | DevOps / K8s      | K3s, Vagrant, K3d, Argo CD environments             | Cluster setup, ingress, automated deployment per part (`p1`, `p2`, `p3`) |
| **Cloud-1**             | DevOps / cloud    | Automated remote deployment (e.g. Ansible)          | Container-per-process, persistence after reboot, parallel deploy         |
| **ft_transcendence**    | Web / full-stack  | Real-time multiplayer Pong website (Docker)         | SPA behaviour, no unhandled errors, security, single-command launch      |


Your cohort needs a **42-Vienna Test Policy** — a high-level agreement on testing purpose, principles, activities, roles, and quality governance for these 42-Projects. This policy is **not** about ToolShop, commercial products, or external industry simulations. It governs how 42 students assure quality within the 42 curriculum.

The policy will be the parent document for project-level self-testing, peer-validation sessions, and curriculum completion decisions. It must use ISTQB terminology and reflect how testing works when authors and validators are fellow students working from the same subject PDFs.

## 5. Task Instructions

1. Review ISTQB FL Chapter 1 in the course syllabus (`foundationLevel/syllabus/syllabus.md`).
2. Pick at least **two** 42-Projects you know (from the table above or your own curriculum) to use as examples throughout the policy.
3. Create a markdown document titled **42-Vienna Test Policy**.
4. Populate the policy using the **mandatory section outline** below. Every subchapter of Chapter 1 must be explicitly addressed in the named section.
5. Ground examples in **42-Project subjects** — mandatory rules, forbidden functions, deliverables, evaluation binaries (e.g. `checker_OS` for push_swap), and peer-evaluation criteria from the subject PDF.
6. Describe how **peer validation by other 42 students** is integrated into testing, independence, roles, and completion decisions.
7. Keep the policy concise but complete: aim for decision-ready guidance, not syllabus copy-paste.
8. Add document control metadata (version, date, author, reviewer).

### Mandatory section outline (maps to Chapter 1)


| Policy section                                     | Syllabus coverage | Minimum content                                                                                                                                                                                                                                                                          |
| -------------------------------------------------- | ----------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **1. Introduction — What is Testing?**             | 1.1               | Define testing for 42-Projects; distinguish testing from merely running code; mention verification (meets subject requirements) and validation (passes peer evaluation); reference dynamic testing (run program, use client/browser) and static testing (code review, subject checklist) |
| **1.1 Test Objectives**                            | 1.1.1             | List test objectives for 42-Projects (e.g., prove mandatory part compliance, reduce defect risk before peer evaluation, verify no forbidden behaviour); state how objectives differ by project type (CLI tool vs. server vs. infrastructure)                                             |
| **1.2 Testing and Debugging**                      | 1.1.2             | Define separate responsibilities: author debugs (reproduce failure, fix defect); peer validator performs confirmation testing after fixes; relate to subject rules such as "program must not quit unexpectedly"                                                                          |
| **2. Why Testing is Necessary**                    | 1.2, 1.2.1        | Explain why 42-Projects need testing before peer evaluation; link to defect detection, evaluation readiness, and curriculum progression (failed evaluation = rework)                                                                                                                     |
| **2.1 Testing and Quality Assurance**              | 1.2.2             | Distinguish testing (find defects in the project deliverable) from QA (improve how the student develops and prepares for evaluation); example: testing `webserv` responses vs. QA habit of compiling with `-Wall -Wextra -Werror` from day one                                           |
| **2.2 Errors, Defects, Failures, and Root Causes** | 1.2.3             | Define error, defect, failure, root cause; example: logic error → wrong sort order in `push_swap` → `checker_OS` prints `KO`; segfault in `ft_nmap` → evaluation failure                                                                                                                 |
| **3. Testing Principles**                          | 1.3               | Document all seven ISTQB testing principles with one 42-Project implication each (e.g., exhaustive testing impossible → sample port ranges in `ft_nmap`; early testing → test Makefile and error paths before bonus part)                                                                |
| **4. Test Activities and Tasks**                   | 1.4, 1.4.1        | Map planning, monitoring, analysis, design, implementation, execution, completion to the 42-Project lifecycle (read subject → design test cases → self-test → peer evaluation → fix → re-evaluation)                                                                                     |
| **4.1 Test Process in Context**                    | 1.4.2             | Explain how context shapes testing: project subject constraints, C vs. C++ vs. DevOps, forbidden libraries/functions, human-only correction, evaluation time limits                                                                                                                      |
| **4.2 Testware**                                   | 1.4.3             | List test work products: self-test notes, test input lists, peer-evaluation checklist, defect log, evaluation prep script; mention subject-provided tools (e.g. `checker_OS`, IRC client, browser)                                                                                       |
| **4.3 Traceability**                               | 1.4.4             | Require traceability from subject mandatory part → test conditions → test results; example: each `ft_irc` requirement in section III.1 linked to a peer-validation check                                                                                                                 |
| **4.4 Roles in Testing**                           | 1.4.5             | Define **project author**, **peer validator (other 42 student)**, and optional **evaluatee/co-evaluator** roles; who plans self-testing, who runs peer evaluation, who signs off completion                                                                                              |
| **5. Skills and Good Practices**                   | 1.5, 1.5.1        | List skills needed at 42: reading subject PDFs precisely, edge-case thinking, communicating defects constructively, tool knowledge (Valgrind, Docker, IRC client, etc.)                                                                                                                  |
| **5.1 Whole Team Approach**                        | 1.5.2             | Quality shared in team projects (e.g. `Inception-of-Things` machine naming, `Cloud-1` deployment scripts); collaboration before peer evaluation                                                                                                                                          |
| **5.2 Independence of Testing**                    | 1.5.3             | **Peer validation must be performed by other 42 students who did not author the work**; map to 42 evaluation model; note when self-testing is allowed (author tests own code) vs. when independence is required (peer evaluation)                                                        |


### Peer validation (mandatory policy topic)

The policy must include a dedicated subsection on **Peer Validation by 42 Students** covering at minimum:

- Purpose: validate whether a 42-Project meets the subject mandatory part and peer-evaluation criteria
- Independence: validators must be other 42 students, not the project author
- Inputs: project subject PDF, repository, Makefile, mandatory deliverables, evaluation rubric from the subject
- Activities: functional testing, edge-case probing, review of forbidden behaviour, re-test after fixes
- Outcomes: pass / fail for curriculum progression; failed items documented for rework
- Constructive communication: report defects and failures against the subject, not against the person
- Subject-specific tooling: use provided evaluation binaries and clients where the subject defines them (e.g. `checker_OS`, browser, IRC client)

### Example prompts (use at least three in your policy)

- **push_swap:** Does invalid input print `Error` on stderr? Does output pass `checker_OS`?
- **webserv / ft_irc:** Does the program survive malformed input without crash (subject: grade 0 if non-functional)?
- **ft_ping / ft_nmap:** Are forbidden functions avoided? Are error paths handled without segfault?
- **Inception-of-Things / Cloud-1:** Do `p1`/`p2`/`p3` (or deploy scripts) work on a clean environment after reboot?
- **ft_transcendence:** Does `docker-compose up --build` launch the full stack? Are there unhandled browser errors?

### Quality checklist before submission

- [ ] Every row in the mandatory outline table is covered by a clearly labelled policy section
- [ ] ISTQB glossary terms are used consistently
- [ ] At least **three examples** reference **named 42-Projects** from the curriculum (not ToolShop or fictional products)
- [ ] Peer validation by other 42 students is described in roles, independence, and completion criteria
- [ ] Testing vs debugging and testing vs QA are clearly separated
- [ ] All seven testing principles are listed with 42-Project implications
- [ ] Document control block is present

## 6. Expected Outcome / Deliverable

One markdown **42-Vienna Test Policy** document that addresses **all Chapter 1 subchapters** via the mandatory section outline and explicitly governs testing and peer validation for **42-Projects** in the 42 curriculum. Suggested filename: `testPolicy-42Vienna.md`.

## 7. Timebox

90 minutes

## 8. Hints (Optional)

- Read the **Submission and peer-evaluation** chapter in your project subject PDF — it defines what validators check.
- A test policy states *what* and *why*; detailed test cases belong in project test notes or a test plan (Chapter 5).
- For **1.3 Testing Principles**, a table (principle → 42-Project example) works well.
- For **1.5.3 Independence**, the 42 evaluation model is the canonical example: you cannot evaluate your own project.
- **push_swap** is a strong example for **1.4.4 Traceability**: subject rules → test inputs → `checker_OS` result.
- DevOps projects (`Inception-of-Things`, `Cloud-1`) shift testing toward environment verification and automated deployment checks.

