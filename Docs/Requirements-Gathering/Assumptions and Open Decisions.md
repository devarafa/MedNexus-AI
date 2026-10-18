# MedNexus AI — Assumptions and Open Decisions

## 1. Purpose

This document records the assumptions, technical decisions, and unresolved questions that may affect the implementation of MedNexus AI.

The purpose is to prevent unclear decisions from becoming hidden implementation risks and to provide a reference for system design and development.

---

# 2. Confirmed Project Scope

The current approved project scope includes:

1. Medical terminology search and dictionary.
2. AI-assisted bilingual medical explanations.
3. PubMed medical research exploration.
4. General health information retrieval.
5. Source attribution and medical safety controls.
6. Experimental X-ray analysis, subject to feasibility.

The system is intended for educational and informational use.

It is not intended to provide:

- Clinical diagnosis.
- Personalized treatment recommendations.
- Medication prescriptions.
- Emergency medical decisions.
- Clinically certified medical image interpretation.

---

# 3. Key Assumptions

## A-01: External Medical Sources

The project assumes that selected external services can be accessed under their applicable technical and usage conditions.

Initial services under consideration are:

- NCBI MeSH.
- PubMed E-utilities.
- MedlinePlus Web Services.

The team will continue to monitor availability, limitations, rate limits, and access requirements.

---

## A-02: AI-Generated Explanations

The project assumes that a suitable Large Language Model API can be used to generate educational explanations.

However, AI-generated content may contain errors or unsupported statements.

Therefore, AI output will not automatically be treated as verified medical information.

---

## A-03: Source-Grounded Generation

Where an AI explanation is requested, the system should provide relevant retrieved source information to the model as context.

The system should separate:

- Original source information.
- AI-generated explanation.

Retrieval-based prompting or RAG may reduce unsupported statements but cannot guarantee factual correctness.

---

## A-04: Source Transparency

The platform assumes that source information can be identified for retrieved medical content.

Where possible, the interface should provide:

- Source name.
- Source identifier.
- Original URL.
- Publication information.

---

## A-05: No Mandatory User Accounts

User accounts are not required for the initial search and retrieval workflows.

A database is therefore not required unless later-approved requirements introduce features such as:

- Saved searches.
- Bookmarks.
- User preferences.
- Persistent history.

---

## A-06: Educational Use

The platform will be designed for educational and informational use.

The system will clearly communicate that:

- AI-generated explanations may contain errors.
- Information should be reviewed against the original sources.
- The platform is not a replacement for professional medical care.

---

## A-07: X-ray Feature Is Conditional

The X-ray analysis component is a feasibility-driven feature.

The team will not assume that a suitable model exists or that any available model can be safely integrated.

The feature will only become an implemented project component if a suitable candidate can be identified, evaluated, and integrated within the available constraints.

---

# 4. Open Decisions

## OD-01: Medical Search Behavior

### Question

How should the search interface handle Arabic and English medical queries?

### Options

- English medical terminology search only.
- English and Arabic query support.
- Arabic query normalization before searching.
- AI-assisted query interpretation.

### Current Direction

The initial implementation should support English medical terminology and provide bilingual explanations. Arabic query support may be introduced if technically feasible within the project timeline.

### Decision Status

Open.

---

## OD-02: AI Model Selection

### Question

Which Large Language Model API should be used?

### Candidate

Gemini API is the current proposed candidate.

### Evaluation Criteria

- API accessibility.
- Pricing and usage limits.
- Response quality.
- Arabic explanation quality.
- English explanation quality.
- Source-grounding behavior.
- Backend integration complexity.
- Response latency.
- Data handling conditions.

### Current Status

Gemini has been evaluated experimentally through AI Studio, but successful manual prompting does not constitute completed backend API integration.

### Decision Status

Open pending API integration and evaluation.

---

## OD-03: Source-Grounded AI Workflow

### Question

How should retrieved medical content be passed to the language model?

### Proposed Workflow

1. User requests an explanation.
2. Backend retrieves relevant source information.
3. Backend selects appropriate source text.
4. Source context is provided to the AI model.
5. The model generates an explanation.
6. The application displays the source and generated explanation separately.
7. The output is evaluated for unsupported additions.

### Decision Status

Proposed and to be validated during implementation.

---

## OD-04: General Health Information Source

### Current Candidate

MedlinePlus Web Services.

### Observation

Initial testing showed that MedlinePlus can provide educational health information for supported topics, but it should not be treated as a comprehensive medical terminology dictionary.

### Decision

Use MedlinePlus for supported general health information rather than relying on it for complete medical terminology coverage.

### Decision Status

Proposed.

---

## OD-05: X-ray Analysis Feasibility

### Question

Can a suitable pretrained X-ray analysis model or external inference service be responsibly integrated into the project?

### Evaluation Criteria

The team will evaluate:

1. Specific imaging task.
2. Intended use.
3. Published evaluation evidence.
4. Dataset information.
5. Model limitations.
6. Licensing.
7. API availability.
8. Pricing.
9. Hardware requirements.
10. Integration complexity.
11. Testing feasibility.
12. Educational suitability.

### Possible Outcomes

#### Outcome A — Implement

A suitable model is identified, evaluated, and successfully integrated.

#### Outcome B — Limited Demonstration

A technically accessible model is available, but validation is limited. A restricted educational demonstration may be considered with supervisor approval and explicit limitations.

#### Outcome C — Do Not Implement

No suitable model can be responsibly integrated within the project constraints.

In this case, the feasibility investigation will be documented and the core platform will remain the main project deliverable.

### Decision Status

Open.

---

# 5. Technical Architecture Direction

The current proposed architecture is:

```text
React Frontend
      |
      v
Node.js / Express Backend
      |
      +--------------------+
      |                    |
      v                    v
Medical APIs          AI Model API
      |
      +--> NCBI MeSH
      +--> PubMed
      +--> MedlinePlus
```

If the X-ray feature is implemented:

```text
React Frontend
      |
      v
Node.js / Express Backend
      |
      +--> X-ray Model / Inference Service
```

The backend will act as the main integration layer between the frontend and external services.

---

# 6. API Key Protection

Secret credentials must not be stored in the React frontend.

The intended flow is:

```text
React
  |
  | Request
  v
Express Backend
  |
  | Secret API Key
  v
External Service
```

This approach prevents exposing secret credentials directly to users through frontend code.

---

# 7. Validation Plan

Before considering an external service part of the final implementation, the team should verify:

- Successful request.
- Correct response parsing.
- Expected response structure.
- Empty result behavior.
- Invalid request behavior.
- Timeout behavior.
- Service failure behavior.
- Usage limitations.
- Source attribution.
- Security implications.

For AI services, the team should additionally evaluate:

- English explanation quality.
- Arabic explanation quality.
- Source consistency.
- Unsupported claims.
- Response stability.
- Usage limits.
- Cost implications.

For X-ray models, the team should additionally evaluate:

- Supported imaging task.
- Input requirements.
- Model documentation.
- Published evaluation evidence.
- Licensing.
- Sample-image processing.
- Output interpretation.
- Integration requirements.
- Safety limitations.

---

# 8. Decision Log

| ID | Decision | Status |
|---|---|---|
| D-01 | React frontend | Confirmed |
| D-02 | Node.js + Express backend | Confirmed |
| D-03 | NCBI MeSH as terminology source under investigation | Confirmed / Tested |
| D-04 | PubMed E-utilities for research retrieval | Confirmed / Tested |
| D-05 | MedlinePlus for supported general health information | Proposed / Tested |
| D-06 | Gemini API as current LLM candidate | Under Evaluation |
| D-07 | Source-grounded AI explanation workflow | Proposed |
| D-08 | X-ray analysis | Conditional / Under Investigation |
| D-09 | Database | Not required for initial workflows |
| D-10 | Medical Claim Verification | Removed from current project scope |

---

# 9. Scope Control

The project team should prioritize the core platform if an experimental component begins to consume excessive development time.

The core implementation priority is:

1. Medical terminology search.
2. Bilingual AI explanation.
3. PubMed research explorer.
4. General health information.
5. Source attribution and safety controls.
6. X-ray feasibility and integration if achievable.

The X-ray feature must not prevent completion of the core platform.

---

# 10. Approval

Any major change to the approved project scope should be discussed with the project supervisor and documented before implementation.

The current scope does not include Medical Claim Verification.

The current project therefore focuses on medical knowledge retrieval, research exploration, bilingual AI-assisted explanation, general health information, and conditional experimental X-ray analysis.