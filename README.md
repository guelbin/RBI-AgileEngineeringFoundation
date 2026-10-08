# TestBusters-LearningLab (TBLL) - Agile Engineering Foundation Program

Learning content repository for the **Agile Engineering Programs** and related courses at the TestBusters-LearningLab,  [42 Vienna](https://42vienna.com/) and RBI trainings. This repo holds course materials, transfer tasks (TRATAS), AI agent configurations, and practice scenarios — not deployable application code.

## Repository overview 


| Area                | Purpose                                                                  |
| ------------------- | ------------------------------------------------------------------------ |
| `courses/`          | Program and workshop materials (GO-IT Academy, TestBusters Learning Lab) |
| `systemsUnderTest/` | Backlog and scenarios for practice applications (primarily **ToolShop**) |
| `templates/`        | TRATAS and prompt templates for authors                                  |
| `.cursor/`          | Cursor IDE agents, rules, and skills                                     |
| `.github/agents/`   | GitHub Copilot agent definitions                                         |
| `generated/`        | Generated prompts and artifacts                                          |


There is no build system or test runner in this repository. Learners work against external systems (e.g. [Practice Software Testing](https://practicesoftwaretesting.com/)) and submit outcomes under `transferTasks-Outcome/` folders.

## Repository structure

```
courses/
  GO-IT-Academy/
    agile-engineering-foundation-program/   # LE001, LE002 (certificates, simulations)
    HolisticTestingWithGenAI-*/             # Workshop runs (PO, Scrum Masters, …)
    TestDataManagement-2026/                # Test data classification and masking
  TestBusters-LearningLab/
    ISTQB-2026/                             # Foundation, GenAI, TAE transfer tasks
    BMAD-ToolShop-2026/                     # BMAD planning and implementation artifacts
    ISTQB-2026-old/                         # Archived materials
systemsUnderTest/
  toolShop/backlog/                         # User stories, features, defects for ToolShop
  onlineBanking/                            # Additional SUT scenarios
templates/                                  # transfer-task-template.md, prompt templates
.cursor/                                    # agents, rules, skills
.github/agents/                             # Copilot agents (ISTQB coach, instructional designer, …)
generated/prompts/
```

### Course tracks in this repo

- **Agile Engineering Foundation** — `courses/GO-IT-Academy/agile-engineering-foundation-program/` (LE001 theory, LE002 hands-on Scrum simulation)
- **ISTQB 2026** — `courses/TestBusters-LearningLab/ISTQB-2026/` with tracks:
  - `foundationLevel/` — CTFL syllabus transfer tasks (~90 tasks)
  - `genAI/` — Generative AI for software testing (~40 tasks)
  - `testAutomationEngineer/` — CTAL-TAE syllabus (~35 tasks)
- **Holistic Testing with GenAI** — workshop artifacts under `HolisticTestingWithGenAI-`*
- **Test Data Management** — masking concepts and SAP HR examples under `TestDataManagement-2026/`
- **BMAD ToolShop** — PRD, architecture, epics, and story specs under `BMAD-ToolShop-2026/_bmad-output/`

### System under test (ToolShop)

Most testing transfer tasks use the **ToolShop** practice app ([Practice Software Testing](https://practicesoftwaretesting.com/)):

- Application: [https://practicesoftwaretesting.com/](https://practicesoftwaretesting.com/)
- Documentation: [https://github.com/testsmith-io/practice-software-testing/tree/main/docs](https://github.com/testsmith-io/practice-software-testing/tree/main/docs)
- Sprint 5 reference: [https://github.com/testsmith-io/practice-software-testing/tree/main/sprint5](https://github.com/testsmith-io/practice-software-testing/tree/main/sprint5)
- Sprint 6 (CZ Version): [https://github.com/rgroetz2/TBLL-AgileEngineeringFoundation/tree/main/systemsUnderTest/toolShop/holtesting/backlog] https://github.com/rgroetz2/TBLL-AgileEngineeringFoundation/tree/main/systemsUnderTest/toolShop/holtesting/backlog)

Extended backlog and teaching scenarios live in `systemsUnderTest/toolShop/backlog/` (features F1–F5, ESG, defects, general stories).

### Content conventions

**Transfer tasks (TRATAS)** follow a standard structure: Title, Syllabus Reference, Learning Objective, Context / Scenario, Task Instructions, Expected Outcome / Deliverable, Timebox (default 30 min), optional Hints. Filename pattern: `ISTQB-<section>-<short-title>_<date>_<author>.md`. Use `templates/transfer-task-template.md` as a starting point.

**Black Stories** (workshop puzzles) are defined in `.cursor/agents/blackstory-designer-agent.md` and `.cursor/rules/blackstory-rules.md`: Title, Teaser, Hidden Solution, Investigation Path, Learning Goal, Difficulty.

**AI agents** (Cursor and GitHub Copilot) support authors and learners — e.g. TRATAS instructional designer, ISTQB TAE coach, Black Story designer, data masking. See `.cursor/agents/` and `.github/agents/`.

Learner submissions are stored in `*/transferTasks-Outcome/` and should not be overwritten by maintainers.

---



## Maintainer notes

- Authoring guidance for AI assistants: see [CLAUDE.md](./CLAUDE.md)
- Cursor rules for instructional design: `.cursor/rules/instructional-designer.mdc`
- Do not commit learner-specific secrets; `.gitignore` excludes `.DS_Store` only

