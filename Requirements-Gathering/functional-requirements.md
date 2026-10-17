# MedNexus AI — Functional Requirements

## 1. Introduction

This document defines the functional requirements of MedNexus AI.

The requirements describe the main functions that the system should provide to support medical terminology search, bilingual medical explanations, scientific research exploration, general health information retrieval, source attribution, and the conditional X-ray analysis component.

The system is intended for educational and informational use and is not designed to provide clinical diagnosis or treatment decisions.

---

## 2. Functional Requirements

### FR-01: Medical Search

**Priority:** Must Have

The system shall allow users to search for supported medical terms and educational health topics.

#### Expected Behavior

- The user enters a search query.
- The frontend sends the query to the backend.
- The backend validates the request.
- The backend communicates with the appropriate external source.
- The system displays matching results.
- If no result is found, the system displays a clear no-results message.

#### Verification

Test the search using a predefined set of valid, invalid, and unsupported queries.

---

### FR-02: Terminology Retrieval

**Priority:** Must Have

The system shall retrieve available medical terminology information from the selected terminology source.

The retrieved information may include:

- Medical term.
- Scientific definition or scope note.
- Available synonyms.
- Related terminology.
- Source identifier.
- Original source link.

#### Verification

Compare displayed terminology information with the corresponding source record.

---

### FR-03: Alternative Terms and Synonyms

**Priority:** Should Have

The system shall display available alternative terms or synonyms when returned by the selected terminology source.

If no synonyms are available, the system shall not invent alternatives.

#### Verification

Test terms with known alternative terms and terms without available alternatives.

---

### FR-04: Bilingual Medical Explanation

**Priority:** Must Have

The system shall provide AI-assisted explanations of supported medical content in English and Arabic.

The explanation should:

- Preserve the meaning of the retrieved information.
- Use understandable language.
- Clearly distinguish generated content from source content.
- Avoid presenting unsupported statements as verified medical facts.
- Indicate limitations where appropriate.

#### Verification

Use a predefined set of medical terms and evaluate generated explanations for clarity, consistency with the retrieved source, and unsupported additions.

---

### FR-05: Medical Research Search

**Priority:** Must Have

The system shall allow users to search PubMed for scientific publications.

#### Expected Behavior

- The user enters a research query.
- The backend sends the request to PubMed E-utilities.
- The system retrieves matching publication records.
- Search results are displayed in a structured format.
- The user can select an individual publication for further details.

#### Verification

Test multiple medical research queries and compare returned records with PubMed.

---

### FR-06: Publication Details

**Priority:** Must Have

The system shall display available publication metadata.

Available information may include:

- Article title.
- Authors.
- Publication date.
- Journal.
- Abstract.
- PMID.
- DOI.
- PubMed link.

The system shall not assume that every publication contains a complete abstract, DOI, or unrestricted full text.

#### Verification

Compare displayed metadata against the corresponding PubMed record.

---

### FR-07: Abstract Explanation

**Priority:** Must Have

The system shall allow users to request an AI-assisted simplified explanation of an available research abstract.

The system should:

- Use the available abstract as source context.
- Clearly distinguish the original abstract from the generated explanation.
- Avoid presenting additional unsupported findings as reported by the authors.
- Indicate when an abstract is unavailable.

#### Verification

Use a predefined set of abstracts and evaluate whether generated explanations preserve the reported findings.

---

### FR-08: General Health Information

**Priority:** Must Have

The system shall retrieve supported educational health information from the selected general health information source.

The initial source under investigation is MedlinePlus Web Services.

The system shall:

- Search supported topics.
- Display available educational information.
- Provide the original source link.
- Clearly communicate when a topic is unavailable.

#### Verification

Test supported and unsupported health topics and compare results with the source.

---

### FR-09: Source Attribution

**Priority:** Must Have

The system shall provide source attribution for retrieved medical information whenever source information is available.

Source information may include:

- Source name.
- Source record.
- External URL.
- Publication identifier.
- Original article or topic link.

AI-generated explanations shall not be represented as direct source content.

#### Verification

Check source links and compare displayed source information with retrieved records.

---

### FR-10: Error Handling

**Priority:** Must Have

The system shall handle common errors without crashing.

The system should provide appropriate messages for:

- Empty search queries.
- Invalid input.
- No search results.
- External API failure.
- Timeout.
- Unavailable content.
- Invalid API response.
- AI service failure.

#### Verification

Simulate or reproduce representative failure conditions and confirm that the interface remains usable.

---

### FR-11: X-ray Image Upload

**Priority:** Conditional

If the X-ray feature is approved for implementation, the system shall allow users to upload supported image formats subject to defined restrictions.

The system should validate:

- File type.
- File size.
- Upload status.
- Supported input requirements of the selected model.

The system should avoid unnecessary retention of uploaded images.

#### Verification

Test supported files, unsupported files, oversized files, and invalid uploads.

---

### FR-12: X-ray Image Analysis

**Priority:** Conditional

If a suitable X-ray analysis model or external inference service is successfully selected and integrated, the system shall submit eligible images for the model's supported analysis task and display the available output.

The system shall:

- Identify the supported task.
- Display the model output.
- Communicate the model's limitations.
- Avoid presenting the output as a confirmed clinical diagnosis.
- Provide relevant model/source information when available.

If no suitable model can be responsibly integrated, this requirement may remain unimplemented and documented as a feasibility outcome.

#### Verification

Test supported sample images under the selected model's documented input conditions and verify output handling.

---

### FR-13: Medical Disclaimer

**Priority:** Must Have

The system shall clearly communicate that MedNexus AI is intended for educational and informational purposes.

The system shall not present itself as:

- A replacement for a physician.
- A clinical diagnostic system.
- A treatment recommendation system.
- A clinically certified X-ray interpretation service.

#### Verification

Verify that the disclaimer is visible in the appropriate interface locations.

---

### FR-14: Explanation Language Selection

**Priority:** Must Have

The system shall allow users to select the preferred explanation language where bilingual explanation is supported.

Supported languages for the initial implementation are:

- English.
- Arabic.

The Arabic interface should support appropriate right-to-left presentation where applicable.

#### Verification

Test both language options and verify that the interface and generated explanation are presented appropriately.

---

### FR-15: Source and AI Content Separation

**Priority:** Must Have

The system shall visually distinguish retrieved source content from AI-generated explanations.

For example, the interface may provide separate sections for:

- Original source information.
- AI-assisted explanation.
- Source/reference information.

#### Verification

Review representative result pages and verify that users can identify which content comes directly from a source and which content is AI-generated.

---

### FR-16: Unavailable Content Indication

**Priority:** Should Have

The system should explicitly indicate when requested information is unavailable.

Examples include:

- No terminology record found.
- No PubMed results found.
- Abstract unavailable.
- Health topic unavailable.
- AI explanation unavailable.
- X-ray analysis unavailable.

The system shall not fabricate missing information.

#### Verification

Test representative unavailable-content scenarios.

---

## 3. Out-of-Scope Functionalities

The following are outside the initial functional scope:

- Autonomous diagnosis.
- Personalized treatment recommendations.
- Medication prescriptions or dosage recommendations.
- Emergency medical decision-making.
- Guaranteed disease detection from X-ray images.
- Electronic health records.
- Hospital management.
- Billing and appointment systems.
- Training a large medical model from scratch.

---

## 4. Acceptance Approach

The functional requirements will be validated through:

1. Unit-level testing where appropriate.
2. API integration testing.
3. End-to-end workflow testing.
4. Invalid input testing.
5. External service failure testing.
6. AI explanation evaluation.
7. Source attribution verification.
8. Responsive interface testing.
9. X-ray testing only if the conditional feature is implemented.

The final project should not claim that a requirement has been completed unless it has been implemented and tested.