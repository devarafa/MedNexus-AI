# Team Roles and Task Assignment

## 1. Principles

- Responsibilities are distributed according to members' skills and the project's implementation requirements.
- With four members, one member may perform more than one role.
- Each task should have a named person responsible, not a general responsibility of the whole team (to be decided).

---

## 2. Roles and Responsibilities

| Role | Responsibilities | Assigned member |
|---|---|---|
| Project Coordinator | Coordinate tasks, track progress, communicate with the supervisor, and maintain project documentation | |
| Frontend Developer | Build React components, search interfaces, results pages, responsive layouts, and user interactions | |
| Backend Developer | Implement Express endpoints, external API integrations, validation, and error handling | |
| AI Integration and Research | Evaluate language model behavior, design explanation prompts, investigate X-ray models, and document feasibility | |
| Testing and Documentation | Prepare test cases, evaluate functionality and usability, record defects, and contribute to the final report | |
| UI/UX Designer | Design user flows, wireframes, visual consistency, and interface usability | |

## 3. Member Summary

| Member   | Role(s) | Supporting role(s) | Skills / availability |
| -------- | ------- | ------------------ | --------------------- |
| Member 1 |         |                    |                       |
| Member 2 |         |                    |                       |
| Member 3 |         |                    |                       |
| Member 4 |         |                    |                       |

---

## 4. Shared Responsibilities (Proposed)

| Responsibility       | Details                                                                   |
| -------------------- | ------------------------------------------------------------------------- |
| Meetings             | Team meetings to review progress and update tasks (frequency not decided) |
| Code review          | Pull requests reviewed by at least one other member                       |
| Testing              | Members try the platform's features before final delivery                 |
| Documentation        | Each member documents the part they build                                 |
| Delivery preparation | Final code and documentation review; presentation preparation             |
| Major decisions      | Technology and feature decisions are made together                        |

---

## 5. Task Matrix

Tasks follow the phases in the [Project Plan](new/Planning/02-project-plan.md). Fill in the member columns once assignments are agreed.

> **L** = lead, **S** = support, **A** = all members.

| Task                                                            | Period | M1  | M2  | M3  | M4  |
| --------------------------------------------------------------- | ------ | --- | --- | --- | --- |
| Proposal finalization and requirements                          | P1     |     |     |     |     |
| Literature review                                               | P1     |     |     |     |     |
| API research and evaluation (MeSH, PubMed, MedlinePlus, Gemini) | P1     |     |     |     |     |
| X-ray model investigation and feasibility report                | P1     |     |     |     |     |
| System architecture and System Diagram                          | P2     |     |     |     |     |
| Database Design                                                 | P2     |     |     |     |     |
| UI/UX design and user flows                                     | P2     |     |     |     |     |
| Backend API planning                                            | P2     |     |     |     |     |
| React and backend setup                                         | P3     |     |     |     |     |
| Medical terminology integration                                 | P3     |     |     |     |     |
| PubMed integration                                              | P4     |     |     |     |     |
| General health information retrieval                            | P4     |     |     |     |     |
| Bilingual explanation integration                               | P4     |     |     |     |     |
| X-ray integration (if feasible)                                 | P5     |     |     |     |     |
| Interface refinement, error handling, safety controls           | P5     |     |     |     |     |
| Integration testing and bug fixing                              | P6     |     |     |     |     |
| Final testing and documentation                                 | P7     |     |     |     |     |
| Presentation preparation                                        | P7     |     |     |     |     |

---

## 6. Suggested GitHub Workflow (Proposed)

1. Keep `main` stable; do feature work on separate branches.
2. Merge into `main` only after review by another member.
3. Use short, clear commit messages.
4. Track tasks with a tool the team chooses (not decided).
5. Never commit API keys or secrets.

---

## 7. Adjusting the Assignment

- Review assignments whenever skills or availability change.
- Record changes in [Assumptions and Open Decisions](new/Planning/06-assumptions-and-open-decisions.md).
- Replace placeholders with real names here and in the root README once the team agrees.

