# MedNexus AI — Stakeholder Analysis

## 1. Introduction

This document identifies the main stakeholders associated with MedNexus AI and describes their expected interests, needs, influence, and potential contribution to the project.

The analysis focuses on educational, technical, and evaluation stakeholders. It does not assume formal partnerships, clinical validation, or institutional approval unless such relationships are explicitly established.

---

## 2. Stakeholder Categories

| ID | Stakeholder | Role | Interest | Influence |
|---|---|---|---|---|
| ST-01 | Medical Students / Learners | Primary target users | High | Medium |
| ST-02 | Medical / Biomedical Researchers | Research-oriented users | High | Medium |
| ST-03 | General Educational Users | Secondary users | Medium | Low |
| ST-04 | Project Team | Developers and researchers | High | High |
| ST-05 | Project Supervisor | Academic oversight | High | High |
| ST-06 | External Medical Information Providers | Information sources | Medium | High |
| ST-07 | AI Service / Model Providers | AI functionality | Medium | High |
| ST-08 | Healthcare Professionals | Potential subject-matter reviewers | Medium | Medium |
| ST-09 | Users with Language / Accessibility Needs | Accessibility considerations | Medium | Medium |

---

## 3. Detailed Stakeholder Analysis

### ST-01: Medical Students and Learners

#### Needs

- Understand medical terminology.
- Access scientific definitions.
- Explore relevant research.
- Receive understandable English and Arabic explanations.
- Identify original information sources.
- Use the platform easily.

#### Project Importance

They represent the primary target audience for the educational functions of the platform.

#### Validation

Their feedback may be collected through usability testing and structured feedback sessions.

---

### ST-02: Medical and Biomedical Researchers

#### Needs

- Search scientific publications.
- Access publication metadata.
- Locate abstracts.
- Access original publication records.
- Understand research content more efficiently.

#### Project Importance

Researchers represent an important user group for the PubMed research explorer.

#### Validation

Research search workflows can be tested using predefined scientific queries and representative users.

---

### ST-03: General Educational Users

#### Needs

- Understand general health information.
- Access clear explanations.
- Identify trustworthy sources.
- Understand the limitations of AI-generated content.

#### Project Importance

They represent secondary users who may benefit from the general health information component.

#### Validation

Usability testing may include users with limited medical knowledge.

---

### ST-04: Project Team

#### Needs

- Clear requirements.
- Defined project scope.
- Manageable implementation tasks.
- Reliable external APIs.
- Feasible AI integration.
- Clear testing criteria.

#### Project Importance

The development team is responsible for implementing, testing, documenting, and presenting the project.

#### Validation

Requirements, architecture, implementation progress, and testing results should be reviewed throughout development.

---

### ST-05: Project Supervisor

#### Needs

- Clear academic objectives.
- Appropriate project scope.
- Documented methodology.
- Evidence-based technical decisions.
- Responsible medical communication.
- Demonstrable final results.

#### Project Importance

The supervisor provides academic guidance and approves major scope or implementation decisions where necessary.

#### Validation

Major changes to project scope, particularly the conditional X-ray component, should be documented and discussed with the supervisor.

---

### ST-06: External Medical Information Providers

Examples include:

- NCBI / MeSH.
- PubMed.
- MedlinePlus.

#### Needs / Constraints

The project must respect:

- API usage conditions.
- Rate limits.
- Available data.
- Attribution requirements.
- Service availability.
- Applicable access conditions.

#### Project Importance

The platform depends on these services for authoritative or structured medical information.

#### Validation

The team should test the services and document their limitations.

---

### ST-07: AI Service and Model Providers

Examples may include:

- Gemini API.
- Future compatible language model services.
- Selected X-ray model or inference provider.

#### Needs / Constraints

The project must consider:

- API availability.
- Usage limits.
- Pricing.
- Data handling.
- Model capabilities.
- Licensing.
- Technical integration requirements.

#### Project Importance

AI services support explanation generation and potentially experimental image analysis.

#### Validation

AI services should be tested before being treated as confirmed project dependencies.

---

### ST-08: Healthcare Professionals

Healthcare professionals may contribute subject-matter feedback where appropriate.

#### Potential Contribution

- Review terminology presentation.
- Review educational clarity.
- Identify potentially misleading medical explanations.
- Provide feedback on responsible communication.

#### Limitation

The project does not assume clinical validation or formal healthcare institutional approval.

Any professional feedback obtained should be documented according to the actual participation and should not be represented as formal clinical validation unless such validation genuinely occurs.

---

### ST-09: Language and Accessibility Needs

Users may have different levels of English and Arabic proficiency or different accessibility needs.

#### Needs

- Clear language.
- Appropriate Arabic RTL presentation.
- Understandable explanations.
- Readable interface.
- Clear distinction between source information and generated explanations.

#### Validation

Test representative workflows in both supported languages and across different screen sizes.

---

## 4. Stakeholder Priorities

The current stakeholder priorities are:

### High Priority

- Medical students and learners.
- Project team.
- Project supervisor.
- Medical information providers.

### Medium Priority

- Medical and biomedical researchers.
- Healthcare professionals providing feedback.
- AI service providers.
- Accessibility and language considerations.

### Lower Priority for Initial MVP

- General educational users outside the primary target audience.

This prioritization may be refined during system design and usability testing.

---

## 5. Stakeholder Communication Plan

| Stakeholder | Communication / Validation Method |
|---|---|
| Medical students | Usability testing, feedback forms, interviews where feasible |
| Researchers | Research workflow testing and feedback |
| Project team | Team meetings, task tracking, technical reviews |
| Supervisor | Progress reviews and milestone approvals |
| External API providers | Official documentation and service testing |
| AI providers | Official documentation, API testing, usage review |
| Healthcare professionals | Optional subject-matter feedback |
| Accessibility users | Interface and language testing |

---

## 6. Stakeholder Risks

Potential stakeholder-related risks include:

- Requirements may change during development.
- User expectations may exceed the educational scope.
- External service limitations may affect functionality.
- AI providers may change pricing or usage restrictions.
- Healthcare professionals may not be available for review.
- Users may misunderstand AI-generated explanations as medical advice.

### Mitigation

The project will:

- Maintain documented requirements.
- Define scope clearly.
- Display medical disclaimers.
- Distinguish source information from AI-generated content.
- Document external service limitations.
- Validate important changes before implementation.

---

## 7. Stakeholder Validation

Stakeholder feedback should be used to evaluate:

- Usability.
- Clarity of terminology presentation.
- Bilingual explanation quality.
- Research exploration workflow.
- Source transparency.
- Educational usefulness.
- Responsible communication.

Feedback should inform improvements without expanding the project beyond the approved scope without appropriate approval.

---

## 8. Summary

The main stakeholders of MedNexus AI are its target educational users, project team, academic supervisor, external medical information providers, and AI service providers.

Healthcare professionals may contribute valuable subject-matter feedback when available, but the project does not claim clinical validation unless formal validation is actually conducted.

The stakeholder analysis supports the project's educational focus and helps ensure that technical decisions remain aligned with user needs, project constraints, and responsible medical communication.