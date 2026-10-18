# Project Proposal

## 1. Overview

### Project Information

| Item            | Value                                                                  |
| --------------- | ---------------------------------------------------------------------- |
| Project name    | MedNexus AI                                                            |
| Subtitle        | An AI-Powered Medical Knowledge, Research, and Image Analysis Platform |
| Project type    | AI-powered web application                                             |
| Domain          | Healthcare technology, artificial intelligence, and medical education  |
| Team size       | Four members                                                           |
| Submission date | 30 November for Source Code                                            |

### Abstract

MedNexus AI is a proposed AI-powered medical web platform designed to improve access to medical knowledge, simplify medical terminology, support medical research exploration, and investigate the feasibility of AI-assisted medical image analysis.

It integrates medical terminology retrieval, scientific literature exploration, bilingual (English and Arabic) medical explanations, and an experimental X-ray analysis module into one web-based platform. The system is proposed to use authoritative services: NCBI Medical Subject Headings (MeSH), PubMed E-utilities, and MedlinePlus Web Services. A large language model API will be investigated for generating simplified explanations based on retrieved information, and suitable pretrained medical image analysis models or external inference services will be investigated for the X-ray feature.

Development will be iterative: requirements analysis and API evaluation, then design, implementation, integration, and testing. The feasibility, reliability, availability, and usage restrictions of external models and services will be evaluated before they are included in the final implementation.

### Background

Digital medical information and AI tools offer new opportunities for medical education and research, but the information is spread across many platforms. Medical terminology is also hard to carry between English and Arabic, because literal translation may not communicate scientific meaning or context. Large language models can generate accessible explanations, but their outputs may include unsupported or inaccurate statements, so they should be connected to reliable sources and evaluated. Pretrained image models can perform specific tasks, but their suitability depends on the task, training data, evaluation evidence, licensing, and deployment requirements.

---

## 2. Problem Statement

1. **Fragmented medical knowledge:** a definition, related publications, and educational context often require several separate searches.
2. **Interpreting specialized terminology:** literal translation may lose medical meaning, while scientific definitions can be hard for non-specialist learners.
3. **Reliability of AI-generated explanations:** language models may state things not supported by the information given to them. Without source retrieval, citation, and verification, users may struggle to tell established information from generated explanation.
4. **Accessibility of AI-assisted image analysis:** selecting a suitable pretrained model and integrating it into a web application requires technical evaluation and validation.

> **Note:** The user-experience problem was explored through preliminary field research conducted by a team member, including discussions with medical students and a visit to a hospital. These activities provided initial insights into the challenges users may face when accessing and understanding medical information. The findings will be used to inform the project requirements and proposed solution.

---

## 3. Proposed Solution

A unified web interface for retrieving, understanding, and exploring medical information, combining structured terminology data, scientific literature search, general health information, and AI-generated educational explanations. An experimental X-ray analysis component will be investigated in parallel.

| Component                                      | Status                                        |
| ---------------------------------------------- | --------------------------------------------- |
| Medical terminology search and dictionary      | Planned                                       |
| AI-powered bilingual medical explanation       | Planned; quality to be tested                 |
| Medical research explorer                      | Planned                                       |
| General health information retrieval           | Planned                                       |
| Source attribution and medical safety controls | Planned                                       |
| Experimental X-ray image analysis              | Experimental; feasibility under investigation |

The interface will distinguish retrieved source content from AI-generated explanations and link to original references whenever possible.

---

## 4. Project Aim

To develop an accessible, AI-assisted medical knowledge platform that helps users retrieve, understand, and explore medical information through reliable source integration, bilingual explanations, and an experimentally evaluated medical image analysis capability.

---

## 5. Objectives

1. Develop a responsive web interface for searching medical terminology and educational information.
2. Integrate a medical terminology source that provides scientific definitions and related terms.
3. Integrate PubMed search to retrieve publication metadata and available abstracts.
4. Investigate and integrate a large language model API for simplified explanations in English and Arabic.
5. Connect AI explanations to retrieved source material wherever possible, and reduce unsupported claims through retrieval-based prompting and verification.
6. Integrate general health information from an appropriate authoritative source.
7. Investigate available pretrained medical X-ray analysis models or external inference APIs.
8. Evaluate candidate X-ray models by intended task, performance evidence, licensing, accessibility, and integration requirements.
9. Implement the X-ray feature if a suitable candidate can be integrated and evaluated within the project constraints.
10. Provide source links, educational disclaimers, and a clear distinction between informational assistance and clinical decision-making.
11. Test functionality, usability, API integration, error handling, and response reliability.
12. Document the architecture, implementation decisions, limitations, and future improvements.

---

## 6. Target Users

The platform initially focuses on **educational and informational use**, not professional clinical workflows.

- Medical students seeking to understand medical terminology and scientific concepts.
- Healthcare-related students who need accessible educational resources.
- Medical and biomedical researchers exploring scientific publications.
- Learners who benefit from explanations in both English and Arabic.
- Educational users interested in the purpose and limitations of AI-assisted medical image analysis.

---

## 7. Scope

### 7.1 In Scope (Proposed for Development or Feasibility Evaluation)

| Feature                              | Description                                                                                                                                                                                                                                                                                                     | Status       |
| ------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ |
| **A. Medical terminology search**    | Standard term, scientific definition or scope note, synonyms and alternative terms, related terminology (where supported), source link, AI-assisted simplified explanation. NCBI MeSH is the initial source under investigation.                                                                                | Planned      |
| **B. Bilingual medical explanation** | Original definition, simplified English explanation, Arabic explanation, explanation of key technical terms, related examples (when source-supported), references and limitations. The model is instructed to separate source-supported information from additional explanation.                                | Planned      |
| **C. Medical research explorer**     | PubMed search showing title, authors, publication date, journal, abstract, PMID or other identifiers, DOI, link to the original record, and an AI-assisted abstract explanation when supported by the source text. The system does not assume every article has a complete abstract or open full text.          | Planned      |
| **D. General health information**    | Educational health information, initially from MedlinePlus Web Services: topic title, summary, educational information, source link, AI-assisted explanation where appropriate.                                                                                                                                 | Planned      |
| **E. Experimental X-ray analysis**   | Feasibility investigation following the workflow in Assumptions and Open Decisions. No model is selected or validated at this stage. If no suitable model is found, findings are documented and the other features continue independently. | Experimental |
| **F. Source attribution and safety** | Source links, distinction between retrieved and generated content, no presenting of generated text as verified fact, handling of unavailable sources and failed requests, educational-use disclaimer.                                                                                                           | Planned      |

### 7.2 Out of Scope

- Autonomous medical diagnosis.
- Personalized treatment recommendations.
- Medication prescriptions or dosage recommendations.
- Emergency medical decision-making.
- Guaranteed detection of every disease from an X-ray.
- A clinically certified diagnostic system.
- A complete electronic health record system.
- Hospital management, billing, or appointment scheduling.
- A custom medical foundation model trained from scratch.

These may be reconsidered in future research but are not part of the initial commitment.

### 7.3 Medical Use Limits

- Educational and informational use only.
- AI outputs are not a substitute for professional consultation, clinical diagnosis, or treatment.
- Any X-ray output is experimental, tied to the selected model's documented task and limitations, and never a confirmed clinical diagnosis.

### 7.4 Known Limitations and Constraints

- Dependence on the coverage, availability, and response formats of external medical information services.
- Not every medical term will necessarily have a complete definition or Arabic explanation from the selected sources.
- AI explanations may contain errors or unsupported statements despite retrieval and prompting safeguards.
- The X-ray feature is limited to the selected model's supported task and available evidence.
- Constrained by the schedule, available computing resources, external API usage conditions, and team experience (the team is still learning front-end development and has no practical backend experience yet).
- The initial implementation prioritizes educational accessibility and transparent retrieval over clinical deployment.

---

## 8. Key Dates

| Date | Deliverable | Status |
|---|---|---|
| 6 November 2026 | Software Architecture, Database Design, System Diagram, UI/UX Design | Confirmed |
| 30 November 2026 | Source code on GitHub, README and documentation, application online or as suitable executables | Confirmed |
| 4 December 2026 | Presentation | Confirmed |

The period-by-period schedule is in the Project Plan.

---

## 9. Expected Outcomes

- A responsive web application for searching medical terminology and educational information.
- A medical dictionary interface backed by an appropriate terminology source.
- A medical research explorer retrieving publication information from PubMed.
- An AI-assisted bilingual explanation workflow with source attribution and documented limitations.
- Integration with a suitable general health information service.
- A documented feasibility assessment of available X-ray models or inference services.
- An experimental X-ray prototype, **if** a suitable model can be integrated and evaluated.
- A documented testing and evaluation process.
- Technical documentation covering architecture, implementation, limitations, and future development.

