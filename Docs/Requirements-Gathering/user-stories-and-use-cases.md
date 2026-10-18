# MedNexus AI — User Stories and Use Cases

## 1. Introduction

This document describes the main user stories and use cases for MedNexus AI.

The user stories represent the needs of the intended users, while the use cases describe the expected interaction between users and the system.

The project focuses on educational and informational medical knowledge rather than clinical diagnosis or treatment.

---

# 2. User Stories

## US-01: Search for a Medical Term

**As a** medical student or learner,

**I want to** search for a medical term,

**so that** I can find its scientific meaning and related information.

### Acceptance Criteria

- The user can enter a medical term.
- The system returns available matching information.
- The result displays the medical term.
- The result provides available scientific information.
- The source is identified.
- A clear message is displayed if no result is available.

---

## US-02: View Alternative Terms

**As a** medical learner,

**I want to** see available synonyms or alternative terms,

**so that** I can understand related terminology and search more effectively.

### Acceptance Criteria

- Alternative terms are displayed when provided by the source.
- The system does not invent synonyms when none are available.

---

## US-03: Understand a Medical Term in English and Arabic

**As a** bilingual medical learner,

**I want to** receive an understandable explanation in English or Arabic,

**so that** I can understand the medical concept more easily.

### Acceptance Criteria

- The user can request an explanation.
- The user can select English or Arabic.
- The generated explanation is clearly identified as AI-assisted.
- Retrieved source information is shown separately.
- Unsupported information should be avoided or identified.

---

## US-04: Search Medical Research

**As a** medical student or researcher,

**I want to** search PubMed for scientific publications,

**so that** I can explore research related to a medical topic.

### Acceptance Criteria

- The user can enter a research query.
- The system returns matching publications.
- Search results display available publication information.
- The user can open an individual publication.

---

## US-05: View Publication Details

**As a** researcher or learner,

**I want to** view publication metadata and available abstracts,

**so that** I can determine whether a paper is relevant.

### Acceptance Criteria

The system may display:

- Title.
- Authors.
- Journal.
- Publication date.
- Abstract.
- PMID.
- DOI.
- PubMed link.

Unavailable information should be clearly indicated.

---

## US-06: Understand a Research Abstract

**As a** learner,

**I want to** request a simplified explanation of a research abstract,

**so that** I can understand the main idea and findings more easily.

### Acceptance Criteria

- The abstract is available to the system.
- The user can request an explanation.
- The AI explanation is clearly separated from the original abstract.
- The explanation should preserve the findings reported by the authors.
- Additional unsupported claims should be avoided.

---

## US-07: Access General Health Information

**As a** general learner,

**I want to** search for supported health topics,

**so that** I can access educational health information from an authoritative source.

### Acceptance Criteria

- The user can search for a supported topic.
- The system displays available information.
- The original source is identified.
- The system communicates when the topic is unavailable.

---

## US-08: Identify Information Sources

**As a** user,

**I want to** know where medical information came from,

**so that** I can review the original source.

### Acceptance Criteria

- Source names are displayed.
- Original links are provided whenever available.
- AI-generated explanations are distinguished from source content.

---

## US-09: Receive Clear Failure Messages

**As a** user,

**I want to** receive a clear message when information cannot be retrieved,

**so that** I understand that the problem is related to availability rather than incorrect information.

### Acceptance Criteria

The system should provide appropriate messages for:

- No results.
- API failure.
- Network error.
- Timeout.
- Missing abstract.
- AI service failure.
- Unsupported request.

The system should not fabricate unavailable information.

---

## US-10: Understand the Educational Nature of the Platform

**As a** user,

**I want to** understand the limitations of MedNexus AI,

**so that** I do not mistake educational information for professional medical advice.

### Acceptance Criteria

The system clearly states that:

- The platform is educational and informational.
- It is not a replacement for a healthcare professional.
- AI-generated explanations may contain errors.
- X-ray outputs, if implemented, are experimental and not confirmed diagnoses.

---

## US-11: Upload an X-ray for Experimental Analysis

**Priority:** Conditional

**As a** user,

**I want to** upload a supported X-ray image,

**so that** I can explore the output of an experimentally evaluated medical image analysis model.

### Acceptance Criteria

This story is applicable only if:

- A suitable X-ray task is identified.
- A suitable model is selected.
- The model can be legally and technically integrated.
- The model can be evaluated within project constraints.

If implemented:

- Supported file types are validated.
- File size restrictions are applied.
- The image is submitted to the selected model.
- The output is displayed with appropriate limitations.
- The result is not presented as a clinical diagnosis.

---

# 3. Use Cases

## UC-01: Search Medical Term

### Primary Actor

Medical student / learner

### Preconditions

The system is available and the terminology service is accessible.

### Main Flow

1. User opens the medical search interface.
2. User enters a medical term.
3. User submits the search.
4. Frontend sends the request to the backend.
5. Backend validates the request.
6. Backend queries the selected terminology source.
7. System receives the result.
8. System displays available terminology information.
9. System displays the source.
10. User may request an AI-assisted explanation.

### Alternative Flows

- No result is returned.
- External API fails.
- Invalid input is submitted.
- The requested information is unavailable.

---

## UC-02: Request Bilingual Explanation

### Primary Actor

Medical student / learner

### Preconditions

Relevant source information is available.

### Main Flow

1. User selects a medical term or source content.
2. User selects English or Arabic.
3. User requests an explanation.
4. Backend retrieves or uses the relevant source context.
5. Backend sends appropriate context to the selected language model.
6. AI generates an explanation.
7. System displays the generated explanation separately from the source content.
8. System provides source information and limitations.

### Alternative Flows

- AI service unavailable.
- Source content unavailable.
- Generated response cannot be safely processed.

---

## UC-03: Explore Medical Publications

### Primary Actor

Medical student / researcher

### Preconditions

PubMed service is available.

### Main Flow

1. User opens the research explorer.
2. User enters a research query.
3. System sends the request to PubMed.
4. PubMed returns matching records.
5. System displays publication results.
6. User selects a publication.
7. System displays available metadata and abstract.

### Alternative Flows

- No results.
- PubMed service unavailable.
- Some metadata is missing.

---

## UC-04: Explain a Research Abstract

### Primary Actor

Medical student / learner

### Preconditions

A publication contains an available abstract.

### Main Flow

1. User opens a publication.
2. User reviews the original abstract.
3. User requests an AI-assisted explanation.
4. Backend provides the abstract as context.
5. AI generates a simplified explanation.
6. System displays the original abstract and generated explanation separately.
7. System provides the publication source.

### Alternative Flows

- Abstract unavailable.
- AI service unavailable.
- Explanation cannot be generated.

---

## UC-05: Access General Health Information

### Primary Actor

General learner

### Preconditions

The selected health information service is available.

### Main Flow

1. User searches for a health topic.
2. Backend sends the request to the selected service.
3. Service returns available information.
4. System displays the information.
5. System provides the original source link.

### Alternative Flows

- Topic unavailable.
- Service unavailable.
- Search returns no results.

---

## UC-06: Verify Source

### Primary Actor

Any user

### Preconditions

A source link or identifier is available.

### Main Flow

1. User views medical information.
2. User identifies the source.
3. User opens the original source link.
4. User reviews the original information.

### Expected Result

The user can distinguish source content from AI-generated explanatory content.

---

## UC-07: Experimental X-ray Analysis

### Primary Actor

Educational user

### Preconditions

A suitable X-ray model has been selected, evaluated, and integrated.

### Main Flow

1. User opens the experimental image analysis interface.
2. User selects a supported image.
3. System validates the image.
4. Backend sends the image to the selected model or inference service.
5. Model returns an output.
6. System displays the output.
7. System displays the supported task and relevant limitations.
8. System displays the educational-use disclaimer.

### Alternative Flows

- Unsupported image format.
- File exceeds allowed size.
- Model unavailable.
- Inference fails.
- No suitable X-ray model has been approved.

### Safety Condition

The result shall not be presented as a confirmed medical diagnosis.

---

# 4. Out-of-Scope User Interactions

The system will not support:

- Requesting personalized treatment plans.
- Requesting prescriptions or dosage decisions.
- Using the platform for emergency decisions.
- Treating X-ray predictions as confirmed diagnosis.
- Managing patient medical records.
- Hospital administrative workflows.

---

# 5. Summary

The user stories and use cases define the primary educational workflows of MedNexus AI.

The core workflows are:

1. Medical terminology search.
2. Bilingual explanation.
3. Medical research exploration.
4. Abstract explanation.
5. General health information retrieval.
6. Source verification.
7. Conditional experimental X-ray analysis.

The system will prioritize reliable retrieval, transparent source attribution, responsible AI communication, and clear limitations.