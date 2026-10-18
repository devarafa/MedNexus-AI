# MedNexus AI — Requirements

## 1. Overview

MedNexus AI is an AI-powered medical knowledge, research, and experimental image analysis platform.

The system is designed to help users search for medical terminology, explore scientific publications, understand medical information in English and Arabic, and access educational health information through selected authoritative sources.

The platform will also investigate the feasibility of integrating an AI-assisted X-ray analysis component. This component is conditional and will only be implemented if a suitable model or inference service can be identified, evaluated, and integrated within the project constraints.

The system is intended for educational and informational purposes only. It is not a clinical diagnostic system and must not be used as a replacement for professional medical consultation or treatment.

---

## 2. Core Project Scope

The initial project scope consists of the following major components:

1. Medical Terminology Search and Dictionary.
2. AI-Assisted Bilingual Medical Explanation.
3. Medical Research Explorer using PubMed.
4. General Health Information Retrieval.
5. Source Attribution and Medical Safety Controls.
6. Experimental X-ray Image Analysis, subject to feasibility.

---

## 3. Requirements Documents

| Document | Description |
|---|---|
| [Stakeholder Analysis](./stakeholder-analysis.md) | Identifies project stakeholders, their needs, influence, and validation approach. |
| [User Stories and Use Cases](./user-stories-and-use-cases.md) | Defines user needs and expected interactions with the system. |
| [Functional Requirements](./functional-requirements.md) | Defines the functions that the system should perform. |
| [Non-Functional Requirements](./non-functional-requirements.md) | Defines quality, security, usability, reliability, and maintainability requirements. |

---

## 4. Requirement Priority

The following priority categories are used:

### Must Have

Requirements that are essential to the core project and should be implemented for the final system.

### Should Have

Important requirements that improve the system but are not essential to the minimum viable implementation.

### Could Have

Optional improvements that may be implemented if time and resources allow.

### Conditional

Requirements that depend on an external feasibility decision. The X-ray analysis feature is currently classified as Conditional.

---

## 5. Main Functional Areas

### 5.1 Medical Terminology

The system should allow users to search for medical terms and retrieve available terminology information from an appropriate medical terminology source, initially investigating NCBI MeSH.

Available information may include:

- Standard medical term.
- Scientific definition or scope note.
- Alternative terms and synonyms.
- Related terminology where supported.
- Original source link.
- AI-assisted simplified explanation.

### 5.2 Bilingual Medical Explanation

The system should provide AI-assisted explanations in English and Arabic.

The generated explanation should be clearly distinguished from retrieved source content.

The system should use retrieved information as context whenever possible and evaluate the generated response for unsupported statements.

### 5.3 Medical Research

The system should allow users to search PubMed and explore available publication information.

The system may display:

- Article title.
- Authors.
- Publication date.
- Journal.
- Abstract when available.
- PMID and other identifiers when available.
- DOI when available.
- Original PubMed link.
- AI-assisted abstract explanation.

### 5.4 General Health Information

The system should retrieve supported educational health information from an appropriate authoritative source, initially investigating MedlinePlus Web Services.

The system should not assume that MedlinePlus provides comprehensive terminology coverage.

### 5.5 Experimental X-ray Analysis

The project will investigate suitable pretrained medical X-ray analysis models or external inference services.

The feature will only be implemented if:

- A specific achievable imaging task is identified.
- A suitable model is found.
- The model has sufficient available evidence for its intended task.
- Licensing and usage conditions permit the proposed use.
- Integration is technically feasible.
- The feature can be evaluated within the available project timeline and resources.

If these conditions are not satisfied, the X-ray feature will remain a documented feasibility study rather than a final implemented feature.

### 5.6 Source Attribution and Safety

The platform should:

- Provide source links whenever available.
- Distinguish retrieved content from AI-generated explanations.
- Communicate limitations of AI-generated content.
- Handle unavailable information and external service failures.
- Display an educational medical disclaimer.
- Avoid presenting the system as a replacement for professional medical care.

---

## 6. Assumptions

The requirements are based on the following assumptions:

1. External medical information services will remain accessible under their applicable usage conditions.
2. External APIs may have rate limits, unavailable results, or temporary failures.
3. Not every medical term will have complete information available from every source.
4. AI-generated explanations may contain errors or unsupported information.
5. Retrieved source information should be displayed separately from generated explanations.
6. API credentials must remain on the backend.
7. Arabic and English support should be considered during interface and explanation design.
8. The X-ray feature is conditional and is not guaranteed to be implemented.
9. No database is required for the initial search and retrieval workflows unless approved requirements introduce persistent user data such as bookmarks or saved searches.
10. The system is educational and informational rather than clinical.

---

## 7. Out of Scope

The initial project does not include:

- Autonomous medical diagnosis.
- Personalized treatment recommendations.
- Medication prescriptions or dosage recommendations.
- Emergency medical decision-making.
- Guaranteed disease detection from X-ray images.
- Clinically certified diagnostic services.
- Electronic health record management.
- Hospital management or billing systems.
- Appointment scheduling.
- Training a large medical foundation model from scratch.

---

## 8. Requirements Validation

Before final implementation, the team should verify that:

- Every Must Have requirement is assigned to an implementation task.
- Every functional requirement has an appropriate test case.
- External APIs have been tested before depending on them.
- API limitations and usage conditions are documented.
- AI-generated explanations are evaluated.
- Source links are verified.
- X-ray feasibility is evaluated before committing implementation resources.
- The final implementation does not claim capabilities that were not actually tested.

---

## 9. Requirement Status

The requirements represent the approved project direction and may be refined during system design and implementation if new technical constraints are discovered.

Any major change to the scope should be discussed with the project supervisor and documented before implementation.
