# Assumptions and Open Decisions


This file collects what is **confirmed**, what was **assumed**, and what is **still undecided**, so nothing in the documentation is mistaken for a final decision. Update it whenever a decision is made.

---

## 1. Confirmed Information

| ID | Information |
|---|---|
| C1 | Deadlines: 6 November (design deliverables), 30 November (final delivery), 4 December (presentation), all in 2026 |
| C2 | The team has four members |
| C3 | The project is part of DEPI; a reviewing party exists (details not specified) |
| C4 | The team is still learning front-end development and has no practical backend experience |
| C5 | GitHub hosts the source code |
| C6 | The platform is for educational and informational purposes only, not a substitute for professional medical care |

## 2. Assumptions and Proposals

| ID  | Assumption or proposal                                                                                                                                                                | Effect if it changes                 |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------ |
| A1  | Planning starts on 16 October 2026                                                                                                                                                    | Internal period dates shift          |
| A2  | Iterative development methodology                                                                                                                                                     | Plan structure changes               |
| A3  | Frontend: React.js, HTML5, CSS3, JavaScript                                                                                                                                           | Tasks and learning needs change      |
| A4  | Backend: Node.js and Express.js                                                                                                                                                       | Tasks and architecture change        |
| A5  | Terminology source: NCBI MeSH; publications: PubMed E-utilities; health information: MedlinePlus Web Services                                                                         | Integration tasks change             |
| A6  | Explanation service: Gemini API                                                                                                                                                       | Explanation workflow and cost change |
| A7  | A database is not required for the initial search and retrieval workflows; it may be added if requirements justify it                                                                 | Storage design and privacy work      |
| A8  | The 6 November deliverables are produced in separate System Analysis & Design work; the plan only schedules them                                                                      | Detailed tasks may need to be added  |
| A9  | Role assignments are not decided; one member may hold several roles                                                                                                                   | Task matrix changes                  |
| A10 | Free or open-source tools are preferred                                                                                                                                               | Technical options may change         |
| A11 | A free X-ray API with limited capabilities (estimates such as sex and approximate age) was identified earlier; it has not been evaluated or selected as part of the feasibility study | X-ray candidate list changes         |

## 3. Open Decisions

| ID | Decision | Notes | Status |
|---|---|---|---|
| D1 | X-ray model or inference service | No model selected or validated; see outcomes below | Undecided |
| D2 | X-ray feasibility outcome (A, B, or C) | Decided after the investigation | Undecided |
| D3 | Gemini API integration, pricing, and usage limits | To be tested from the backend | Undecided |
| D4 | Database | Only if requirements justify it | Undecided |
| D5 | Hosting and deployment | | |
| D6 | Role and task assignments | | |
| D7 | Weekly hours per member | | |
| D8 | Team name and supervisor name | | |
| D9 | Submission date | | |
| D10 | Intermediate DEPI review dates, if any | | |
| D11 | Task-tracking tool | | |
| D12 | Usability test participants and the predefined test sets (terms, explanations) | | |
| D13 | Image data source for X-ray testing (appropriately sourced and authorized) | | |

## 4. X-ray Feasibility Outcomes

The investigation looks for an existing pretrained model or inference service for a specific, achievable X-ray task (no training from scratch). Candidates are assessed on task suitability, evidence of performance, ease of integration, computational feasibility, cost and access restrictions, licensing, ability to communicate limitations, and suitability for educational demonstration.

| Outcome                              | Description                                                                                                                                                             |
| ------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **A: Successful integration**        | A suitable candidate is integrated and evaluated; the experimental X-ray feature is implemented                                                                         |
| **B: Limited demonstration**         | A model is accessible but cannot be adequately validated; a restricted educational demonstration with explicit limitations may be shown, subject to supervisor approval |
| **C: Infeasible within constraints** | Findings are documented and the other platform features remain the main deliverables                                                                                    |

Safety: the X-ray module is not presented as clinically approved. Patient images are not used without authorization and privacy safeguards, and public datasets are considered only after reviewing their access conditions and permitted use.

## 5. Decision Log

| Date | Decision | Decided by | Notes |
|---|---|---|---|
| | | | |

---

