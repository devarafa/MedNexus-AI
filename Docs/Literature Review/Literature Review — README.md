# MedNexus AI — Literature Review

[⬅️ Project README](Home/mednexus-v1/README.md)

## Status

**Current status: Preliminary research completed; further review and validation are ongoing.**

The literature review has not yet been completed. The resources listed below are preliminary technical references identified in the approved project proposal.

Additional peer-reviewed publications and relevant research studies will be reviewed and cited before the literature review is finalized.

No lecturer feedback, official grades, or grading weights are assumed in this document.

---

## 1. Purpose

The purpose of the literature review is to investigate existing research, technologies, and information services relevant to MedNexus AI.

The review will support technical decisions and help identify relevant challenges related to medical information retrieval, AI-generated explanations, bilingual medical education, and experimental medical image analysis.

The literature review will focus on the following areas:

1. Medical terminology databases and information retrieval.
2. Scientific literature search and publication retrieval.
3. AI-assisted medical explanation and reliability.
4. Retrieval-Augmented Generation (RAG) and source-grounded generation.
5. Bilingual medical terminology and educational accessibility.
6. Pretrained medical image analysis models and their limitations.
7. Responsible use of artificial intelligence in healthcare-related applications.

---

## 2. Contents

| Document | Purpose | Current Status |
|---|---|---|
| This document | Preliminary references and planned literature review topics | Preliminary |
| [Feedback and Improvements](feedback-and-improvements.md) | Records actual reviewer feedback and potential improvements | Awaiting feedback |
| [Grading Criteria](grading-criteria.md) | Records official grading weights and criteria when provided | Awaiting official information |

---

## 3. Preliminary Technical References

The following official resources are initial technical references for the project. They provide documentation for the services and technologies under consideration; they do not, by themselves, constitute a complete academic literature review.

| Resource | Relevance to MedNexus AI |
|---|---|
| [National Library of Medicine — MeSH](https://www.ncbi.nlm.nih.gov/mesh/) | Medical terminology and structured subject headings |
| [NCBI E-utilities API Documentation](https://www.ncbi.nlm.nih.gov/home/develop/api/) | Programmatic access to NCBI databases |
| [PubMed](https://pubmed.ncbi.nlm.nih.gov/) | Scientific publication search and biomedical literature discovery |
| [MedlinePlus Web Services](https://medlineplus.gov/about/developers/webservices/) | Retrieval of supported educational health information |
| [Gemini API Documentation](https://ai.google.dev/gemini-api/docs) | Investigation of AI-assisted explanation generation |
| [Gemini API Pricing and Usage](https://ai.google.dev/gemini-api/docs/pricing) | Evaluation of potential API costs and usage limits |
| [Hugging Face Model Hub](https://huggingface.co/models) | Discovery of potential pretrained models for investigation |
| [WHO — Ethics and Governance of Artificial Intelligence for Health](https://www.who.int/publications/i/item/9789240029200) | Ethical considerations for AI applications in health-related contexts |

The availability, limitations, licensing conditions, and usage requirements of relevant services and models will be reviewed before final implementation decisions.

---

## 4. Planned Literature Review Topics

### 4.1 Medical AI Reliability

Investigate research on the reliability of AI-generated medical explanations, including hallucinations, unsupported statements, and methods for evaluating factual consistency.

**Research questions:**

- What types of errors can AI language models make when explaining medical information?
- How can generated explanations be evaluated against reliable sources?
- What limitations should be communicated to users?

### 4.2 Retrieval-Augmented Generation

Investigate RAG and related approaches that provide language models with retrieved source material before generating explanations.

**Research questions:**

- How can retrieved information support AI-generated explanations?
- What limitations remain when source material is supplied to a model?
- How can source attribution and unsupported claims be evaluated?

### 4.3 Bilingual Medical Education

Investigate challenges associated with understanding specialized medical terminology across English and Arabic.

**Research questions:**

- Why may literal translation fail to communicate a medical concept adequately?
- What makes a medical explanation understandable to learners?
- How can bilingual explanations preserve scientific meaning?

### 4.4 Medical Image Analysis

Investigate pretrained medical X-ray analysis models and external inference services.

**Research questions:**

- Which specific X-ray analysis tasks are supported by available models?
- What evaluation evidence is available for candidate models?
- What limitations, licensing conditions, and integration requirements affect their use?

The investigation does not assume that a suitable model has already been selected or validated.

### 4.5 Existing Medical Information Platforms

Review existing medical terminology resources, scientific literature databases, and educational health information services.

**Research questions:**

- What information does each service provide?
- What are its coverage and access limitations?
- How can the selected services complement one another within a unified interface?

---

## 5. Literature Review Method

The team will identify relevant peer-reviewed publications, official technical documentation, and authoritative guidance.

For each selected academic publication, the review should record:

- Full title.
- Authors.
- Publication year.
- Journal or conference.
- DOI or stable source link, where available.
- Research objective.
- Methodology.
- Main findings.
- Limitations.
- Relevance to MedNexus AI.

Official API documentation will be used to support technical integration decisions, while academic publications will be used to support the discussion of research findings, reliability, evaluation methods, and relevant limitations.

The team should distinguish between evidence reported by a publication and its own interpretation of that evidence.

---

## 6. Related Project Documentation

- [Planning](../Planning/README.md)
- [Requirements Gathering](../Requirements-Gathering/README.md)

---

## 7. Completion Criteria

The literature review may be considered ready for final review when:

- Relevant academic publications have been selected.
- Each major research topic is supported by appropriate references.
- Claims are linked to their supporting sources.
- Research findings and limitations are summarized accurately.
- The review explains how the research informs MedNexus AI.
- References follow a consistent citation style.
- Preliminary technical documentation is distinguished from peer-reviewed research.
