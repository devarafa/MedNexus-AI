# MedNexus AI — Non-Functional Requirements

## 1. Introduction

This document defines the non-functional requirements for MedNexus AI.

These requirements describe the expected quality attributes of the system, including usability, responsiveness, reliability, performance, security, source transparency, maintainability, extensibility, language support, and responsible medical communication.

---

## 2. Non-Functional Requirements

### NFR-01: Usability

The system should provide an intuitive interface that allows target users to complete the main workflows without requiring developer assistance.

Core workflows include:

- Searching for a medical term.
- Viewing terminology information.
- Requesting an explanation.
- Searching for research publications.
- Viewing publication details.
- Accessing available health information.
- Locating the original source.

#### Verification

Conduct usability testing with representative users and record navigation difficulties and feedback.

---

### NFR-02: Responsiveness

The application should provide an appropriate user experience across:

- Desktop.
- Tablet.
- Mobile.

The interface should avoid unintended horizontal scrolling and maintain readable content across supported screen sizes.

#### Verification

Test the main pages at representative viewport sizes.

---

### NFR-03: Reliability

The system should handle expected failures gracefully.

These include:

- External API failures.
- Network interruptions.
- Timeouts.
- Empty results.
- Invalid user input.
- Unavailable abstracts.
- AI service failures.

The application should provide useful feedback rather than exposing raw technical errors to users.

#### Verification

Perform failure-condition testing for the major external services and user workflows.

---

### NFR-04: Performance

The system should avoid unnecessary external requests and provide clear loading feedback during operations that depend on external services.

Performance evaluation should distinguish between:

- Frontend processing time.
- Backend processing time.
- External API response time.
- AI generation time.
- X-ray inference time, if implemented.

Actual performance targets should be established and measured during implementation rather than assumed in advance.

#### Verification

Measure representative workflows under defined test conditions.

---

### NFR-05: Security and Privacy

The backend shall protect secret API credentials.

The system should:

- Keep API keys outside frontend source code.
- Validate incoming requests.
- Restrict supported operations.
- Validate uploaded files if image analysis is implemented.
- Limit uploaded file size.
- Avoid unnecessary retention of medical images.
- Avoid collecting unnecessary personal information.

If public or authorized medical images are used for testing, the team should respect the applicable access and usage conditions.

#### Verification

Inspect the application configuration and test input validation and upload restrictions.

---

### NFR-06: Accuracy and Source Transparency

The system should clearly distinguish:

- Retrieved source information.
- AI-generated explanations.
- Model-generated X-ray outputs, if implemented.

The system should provide source links whenever available.

AI-generated content should not be represented as a direct quotation from a medical source unless it is actually quoted.

The project should evaluate generated explanations for unsupported claims and document observed limitations.

#### Verification

Compare representative AI outputs with the retrieved source material.

---

### NFR-07: Maintainability

The codebase should be organized into reusable components and clearly separated modules.

The architecture should separate:

- Frontend components.
- Backend routes.
- External API integrations.
- AI integration.
- Validation.
- Error handling.

This structure should allow individual services to be modified without requiring a complete redesign of the system.

#### Verification

Review project structure and code organization.

---

### NFR-08: Extensibility

The system should allow additional medical information sources and AI services to be integrated in the future.

External service integrations should be modular where practical.

The optional database layer should only be introduced if approved requirements require persistent data.

#### Verification

Review whether a new external service could be added without major architectural changes.

---

### NFR-09: Language Support

The system should support English and Arabic for the main educational explanation workflow.

The interface should support appropriate Arabic right-to-left presentation where applicable.

Medical terminology should not be translated through literal translation alone when an explanatory medical meaning is required.

#### Verification

Test representative medical terms and explanations in both languages.

---

### NFR-10: Responsible Medical Communication

The system shall communicate that its content is educational and informational.

The system shall not:

- Present AI-generated content as guaranteed medical truth.
- Present X-ray model outputs as confirmed diagnoses.
- Provide personalized treatment decisions.
- Claim clinical validation without appropriate evidence.

The educational disclaimer should be visible to users at appropriate points in the application.

#### Verification

Review the interface and generated outputs for potentially misleading clinical claims.

---

## 3. External Service Considerations

The system depends on external services including, subject to final implementation:

- NCBI MeSH.
- PubMed E-utilities.
- MedlinePlus Web Services.
- A large language model API.
- An X-ray inference service or model, if selected.

The team should document:

- Availability.
- Rate limits.
- Usage restrictions.
- Pricing where applicable.
- Response limitations.
- Licensing conditions.

The application should not assume that external services are permanently available.

---

## 4. Testing and Verification

The non-functional requirements will be evaluated through:

- Usability testing.
- Responsive design testing.
- API failure testing.
- Performance measurements.
- Security review.
- Source verification.
- AI explanation evaluation.
- Code structure review.
- Language and RTL testing.
- Responsible communication review.

All measured results should be documented separately from proposed targets.

---

## 5. Requirement Status

These requirements describe the expected quality of the final application. Specific technical targets may be refined during system design and implementation based on the available resources and external service constraints.