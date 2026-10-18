# Risk Assessment and Mitigation Plan

---

## 1. Method

| Score | Probability | Impact |
|---|---|---|
| 1 – Low | Unlikely | Minor, easy to recover |
| 2 – Medium | Possible | Delay or rework of part of the project |
| 3 – High | Likely | A core feature fails or a deadline is missed |

**Risk level = probability × impact.** 1–2 = 🟢 Low, 3–4 = 🟡 Medium, 6–9 = 🔴 High.

---

## 2. Risk Register

| ID  | Risk                                                   | Potential impact                                          | P   | I   | Level |
| --- | ------------------------------------------------------ | --------------------------------------------------------- | --- | --- | ----- |
| R1  | AI-generated medical inaccuracies                      | Users may receive unsupported explanations                |     |     |       |
| R2  | Limited medical terminology coverage                   | Some searches may return no results                       |     |     |       |
| R3  | External API failure or rate limits                    | Search and explanation features may become unavailable    |     |     |       |
| R4  | Gemini API pricing or usage restrictions               | Increased cost or limited access                          |     |     |       |
| R5  | No suitable X-ray model found                          | The experimental feature cannot be implemented as planned |     |     |       |
| R6  | X-ray model performance limitations                    | Predictions may be unreliable                             |     |     |       |
| R7  | Integration complexity                                 | Delays in completing the application                      |     |     |       |
| R8  | Limited project time                                   | Some features may remain incomplete                       |     |     |       |
| R9  | Unauthorized or sensitive image uploads                | Privacy and security risks                                |     |     |       |
| R10 | Misleading interpretation of outputs                   | Users may confuse educational results with diagnosis      |     |     |       |
| R11 | Skill gaps (React, Node.js/Express, working with APIs) | Slower implementation                                     |     |     |       |
| R12 | API keys exposed in the public repository              | Misuse of keys and services                               |     |     |       |
| R13 | Deployment or hosting problems                         | Application not available at delivery                     |     |     |       |
| R14 | Limited availability of some team members              | Delays or uneven workload                                 |     |     |       |
| R15 | Unclear review requirements from DEPI                  | Documentation or delivery may not match expectations      |     |     |       |
| R16 | Merge conflicts or lost work on GitHub                 | Rework                                                    |     |     |       |

---

## 3. Mitigation and Contingency

| ID | Mitigation strategy | Contingency | Owner |
|---|---|---|---|
| R1 | Use retrieved source material, source attribution, structured prompts, and evaluation | | |
| R2 | Use alternative search strategies and provide clear no-result messages | | |
| R3 | Add error handling, timeouts, request limits, and suitable fallback behavior | | |
| R4 | Review current usage conditions and investigate alternatives before deployment | | |
| R5 | Start feasibility research early and document alternatives | Outcome C: document findings and keep the other features as the main deliverables | |
| R6 | Review published evaluation evidence, test within the supported task, and communicate limitations | Outcome B: restricted educational demonstration with explicit limitations, subject to supervisor approval | |
| R7 | Build and test the core features independently before optional integrations | | |
| R8 | Prioritize core requirements and control scope | | |
| R9 | Use suitable public or authorized data, validate uploads, and minimize data retention | | |
| R10 | Display clear disclaimers and avoid claims of clinical validation | | |
| R11 | Learn alongside implementation; ask the instructor | | |
| R12 | Keep secret keys in backend configuration, never in React code; do not commit secrets | Revoke and regenerate any exposed key | |
| R13 | Test deployment early | | |
| R14 | Agree available time per member | | |
| R15 | Confirm requirements with the reviewing party and record updates | | |
| R16 | Separate branches and code review | | |

---

## 4. Monitoring

- Review risks regularly and add or close them as the project evolves.
- If a risk becomes a real problem, choose and record the contingency action.

| Status | Meaning |
|---|---|
| Open | Risk exists and is being monitored |
| Occurred | Risk happened; contingency in progress |
| Closed | Risk no longer applies |


