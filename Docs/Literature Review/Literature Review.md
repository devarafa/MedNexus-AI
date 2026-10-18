# MedNexus AI — Literature Review

**Project:** MedNexus AI  
**Document:** Literature Review, Research Findings, and Suggested Improvements  
**Project Type:** AI-Powered Medical Knowledge and Research Platform  
**Status:** Preliminary Literature Review

---

## 1. Introduction

Artificial Intelligence (AI), particularly Large Language Models (LLMs), is increasingly being explored for medical information retrieval, question answering, summarization, and healthcare-related applications.

Although these technologies offer opportunities to make medical information easier to access and understand, they also introduce challenges. AI-generated medical explanations may contain inaccurate information, omit important details, or provide statements that are not adequately supported by reliable medical sources.

MedNexus AI aims to address some of these challenges by combining medical information retrieval, bilingual medical terminology support, research exploration, and AI-assisted explanations within a single web platform.

The purpose of this literature review is to examine existing research related to the reliability of medical LLMs, Retrieval-Augmented Generation (RAG), medical terminology interoperability, and the evaluation of AI-generated medical information.

The findings will inform the design, implementation, and evaluation of MedNexus AI.

## 2. Research Objectives

This literature review focuses on the following questions:

1. What limitations affect the reliability of Large Language Models in healthcare?
2. How can external medical knowledge sources improve the grounding of AI-generated explanations?
3. Why is systematic evaluation necessary for AI-powered medical applications?
4. How can multilingual medical terminology systems improve access to medical knowledge?
5. What design and evaluation improvements are relevant to MedNexus AI?

## 3. Research Method

This preliminary review uses published research articles and official technical documentation relevant to the project.

The research focuses on four areas:

- Reliability and evaluation of LLMs in healthcare.
- Retrieval-Augmented Generation and source-grounded responses.
- Medical terminology and multilingual interoperability.
- Practical implications for developing an educational medical information platform.

The selected academic papers include systematic reviews and research articles published in peer-reviewed journals. Official documentation is also used to identify potential medical information sources and integration methods.

This document is a preliminary, focused literature review rather than an exhaustive systematic review. The sources were selected for their relevance to the project's proposed functionality.

---

## 4. Related Research

### 4.1 Testing and Evaluation of Health Care Applications of Large Language Models: A Systematic Review

**Authors:** Bedi, S., Liu, Y., Orr-Ewing, L., et al.  
**Journal:** JAMA  
**Publication Year:** 2025  
**DOI:** 10.1001/jama.2024.21700

**Research link:**  
https://pubmed.ncbi.nlm.nih.gov/39405325/

**Full-text article:**  
https://jamanetwork.com/journals/jama/fullarticle/2825147

#### Research Objective

This systematic review examined how Large Language Models were evaluated in healthcare, including the types of data, healthcare tasks, evaluation metrics, and medical specialties represented in the research.

#### Key Findings

The review examined 519 studies published between January 2022 and February 2024.

The authors reported that:

- Only 5% of the included studies used real patient-care data for LLM evaluation.
- Medical question answering was the most frequently studied natural language task.
- Accuracy was the primary evaluation dimension in 95.4% of studies.
- Fairness, bias, toxicity, calibration, uncertainty, and deployment considerations received considerably less attention.

The authors concluded that current evaluation practices were fragmented and recommended more standardized evaluation methods and broader assessment dimensions.

#### Relevance to MedNexus AI

This research demonstrates why evaluating an AI medical platform should involve more than checking whether its responses appear fluent or relevant.

MedNexus AI should evaluate whether generated explanations are:

- Factually consistent with retrieved medical sources.
- Relevant to the user's question.
- Understandable to the intended audience.
- Properly attributed to their sources.
- Appropriately cautious when the available evidence is insufficient.

The project can use a controlled set of medical terminology questions and research abstracts to assess the quality of its AI-generated explanations.

**Important limitation:** The review's findings describe the studies included in that review. They do not establish that every medical AI application has the same performance limitations.

---

### 4.2 Evaluation of ChatGPT-Generated Medical Responses: A Systematic Review and Meta-Analysis

**Authors:** Wei, Q., Yao, Z., Cui, Y., Wei, B., Jin, Z., and Xu, X.  
**Journal:** Journal of Biomedical Informatics  
**Publication Year:** 2024  
**Volume:** 151  
**Article Number:** 104620  
**DOI:** 10.1016/j.jbi.2024.104620

**Research link:**  
https://pubmed.ncbi.nlm.nih.gov/38462064/

#### Research Objective

This study systematically reviewed research evaluating medical responses generated by ChatGPT and conducted a meta-analysis of a subset of studies to estimate performance on comparable medical question-answering tasks.

#### Key Findings

The authors included 60 studies in their systematic review, with 17 studies contributing to the meta-analysis.

The meta-analysis estimated an overall accuracy of 56% (95% confidence interval: 51%–60%) for the selected multiple-choice question tasks.

The study also reported substantial variation among the included studies. Performance differed across question categories, and the authors identified problems with inconsistent reporting of model versions, prompts, evaluation methods, and other experimental details.

The authors emphasized the need for more transparent and standardized evaluation methods.

#### Relevance to MedNexus AI

This study highlights the importance of not assuming that a fluent AI-generated medical explanation is necessarily correct.

For MedNexus AI, the findings support the following design decisions:

1. Retrieve relevant information from medical sources before generating an explanation.
2. Display source information separately from the AI-generated summary.
3. Evaluate the generated explanation against the retrieved material.
4. Test the system using multiple questions rather than relying on a few successful examples.
5. Document the model version, prompts, test cases, and evaluation results.

**Important limitation:** The reported 56% estimate applies to the selected multiple-choice tasks included in that meta-analysis. It must not be interpreted as the accuracy of every LLM, every medical question, or the MedNexus AI system.

---

### 4.3 Retrieval-Augmented Generation for Large Language Models in Healthcare: A Systematic Review

**Authors:** Amugongo, L. M., Mascheroni, P., Brooks, S., Doering, S., and Seidel, J.  
**Journal:** PLOS Digital Health  
**Publication Year:** 2025  
**Volume:** 4, Issue 6  
**Article Number:** e0000877  
**DOI:** 10.1371/journal.pdig.0000877

**PubMed:**  
https://pubmed.ncbi.nlm.nih.gov/40498738/

**Full text:**  
https://pmc.ncbi.nlm.nih.gov/articles/PMC12157099/

**Publisher:**  
https://journals.plos.org/digitalhealth/article?id=10.1371/journal.pdig.0000877

#### Research Objective

This systematic review examined how Retrieval-Augmented Generation is used in healthcare, focusing on retrieval methods, knowledge sources, generation techniques, and evaluation approaches.

#### Key Findings

The authors discussed several limitations of conventional LLMs in healthcare, including outdated training knowledge, hallucinations, and limited transparency.

RAG addresses some of these challenges by retrieving relevant information from external knowledge sources and providing that information to the LLM as context for generating a response.

However, the review also identified important challenges:

- Selecting relevant and reliable knowledge sources.
- Managing noisy or irrelevant retrieved information.
- Evaluating the factual reliability of generated responses.
- Addressing ethical considerations.
- Establishing standardized evaluation frameworks for healthcare RAG systems.

The review also reported that English-language datasets predominated among the studies it examined, highlighting the importance of considering language coverage when designing medical AI systems.

#### Relevance to MedNexus AI

RAG is relevant to MedNexus AI because the project aims to combine reliable medical information retrieval with AI-generated explanations.

A proposed workflow is:

1. The user searches for a medical term or research topic.
2. The backend retrieves relevant information from an appropriate medical source.
3. The system provides the retrieved information to the AI model as context.
4. The model generates an explanation based on the supplied material.
5. The interface displays the explanation alongside the source title, link, and relevant retrieved information.

This approach can make responses more traceable and help reduce unsupported statements. However, RAG does not guarantee correctness: the retrieved source may be incomplete or irrelevant, and the model may still misinterpret or misrepresent it.

Therefore, MedNexus AI must evaluate both retrieval quality and generated-answer quality.

---

### 4.4 HealthTermFinder: Enhancing Multilingual Interoperability

**Authors:** Noll, R., Storf, H., and Schaaf, J.  
**Journal:** Studies in Health Technology and Informatics  
**Publication Year:** 2025  
**Volume:** 327  
**Pages:** 2–6  
**DOI:** 10.3233/SHTI250262

**Research link:**  
https://pubmed.ncbi.nlm.nih.gov/40380374/

#### Research Objective

This research introduced HealthTermFinder, a tool designed to support multilingual discovery and interoperability of standardized healthcare terminology using resources from the Unified Medical Language System (UMLS).

#### Key Findings

The authors explored mappings between standardized healthcare terminology resources across multiple languages, including Arabic.

The research demonstrates the importance of linking medical concepts across languages and terminology systems rather than relying exclusively on direct word-for-word translation.

The authors reported that their tool mapped clinical features in three German case studies with an overall coverage of 82%.

This result belongs to the specific tool and case studies evaluated by the authors; it should not be interpreted as a general accuracy measure for Arabic medical translation.

#### Relevance to MedNexus AI

This research is particularly relevant to the project's bilingual medical terminology feature.

A medical term may have a standardized English name, an Arabic equivalent, a specific medical meaning, and different meanings depending on context. A direct translation alone may not explain the concept sufficiently.

MedNexus AI should therefore aim to distinguish between:

- The original medical term.
- Its Arabic equivalent, where available.
- A clear explanation of the medical concept.
- Its context and relevant examples.
- The original terminology source.

Where an authoritative Arabic equivalent cannot be verified, the system should preserve the original term and indicate that the translation or equivalent requires confirmation rather than inventing one.

The study also suggests that standardized terminology resources can be valuable for connecting related concepts across languages. Their suitability, licensing, access requirements, and actual Arabic coverage must be assessed before integration.

---

## 5. Synthesis of the Literature

The selected studies address different but complementary challenges.

| Research area | Main finding | Implication for MedNexus AI |
|---|---|---|
| LLM evaluation in healthcare | Evaluation methods are often fragmented and focus heavily on accuracy. | Use structured, documented tests covering factual consistency, relevance, clarity, and source attribution. |
| Evaluation of ChatGPT-generated medical responses | Performance varies across tasks, and research methods are not always reported consistently. | Document model versions, prompts, test questions, and evaluation results. |
| RAG in healthcare | External knowledge can ground generated responses, but retrieval and evaluation remain challenging. | Retrieve medical source material before generating explanations and assess both retrieval and generation quality. |
| Multilingual medical terminology | Standardized terminology mapping can help connect medical concepts across languages. | Build terminology support around verified concepts and equivalents rather than literal translation alone. |

### Overall Research Gap

The reviewed research identifies several challenges relevant to MedNexus AI:

1. AI-generated medical content requires systematic evaluation.
2. Connecting generated explanations to trustworthy external information is important for transparency.
3. Retrieval alone does not guarantee that an explanation is accurate.
4. Medical terminology requires attention to meaning and context, not just translation.
5. Multilingual support must account for the actual language coverage of terminology resources.

Based on these findings, MedNexus AI proposes to combine medical terminology lookup, medical research exploration, and source-grounded bilingual explanations in one interface.

This is a **project design objective**, not a claim that the proposed platform has already solved these research challenges.

The reviewed studies also do not establish that no existing platform offers similar functionality. A broader comparison with existing medical dictionaries, research tools, and medical AI systems would be needed to establish the project's novelty more precisely.

---

## 6. Suggested Improvements Based on the Literature

The following recommendations are derived from the reviewed research and adapted to the proposed scope of MedNexus AI.

### 6.1 Source-Grounded AI Explanations

**Problem:** LLMs may generate unsupported or inaccurate statements.

**Recommendation:** Retrieve relevant information from an appropriate medical source and provide it to the AI model as context.

**Proposed implementation:**
- Retrieve relevant medical terminology or publication information.
- Supply relevant source content to the model.
- Generate an explanation appropriate to the user's language and knowledge level.
- Display the source title and link.
- Keep source content distinguishable from AI-generated text.

**Evaluation:** Compare generated explanations with the retrieved material and record unsupported, contradictory, or missing claims.

### 6.2 Structured AI Evaluation

**Problem:** Fluent language does not guarantee factual correctness.

**Recommendation:** Develop a documented test set for the system's core features.

**Proposed evaluation dimensions:**
- Factual consistency with the retrieved source.
- Relevance to the query.
- Clarity and readability.
- Preservation of important medical details.
- Correct representation of uncertainty.
- Quality of source attribution.

**Evaluation:** Record the test question, retrieved source, generated answer, evaluation result, and identified errors.

### 6.3 Context-Aware Medical Terminology

**Problem:** Literal translation may not adequately explain medical concepts.

**Recommendation:** Separate terminology lookup, verified equivalents, and explanatory content.

**Proposed implementation:**
- Display the original term.
- Display a verified Arabic equivalent where available.
- Provide a plain-language definition.
- Include relevant context or examples when supported by the source.
- Link to the terminology reference.

**Evaluation:** Test a collection of common medical terms and assess the correctness of definitions, terminology mappings, and Arabic explanations.

### 6.4 Transparent Research Exploration

**Problem:** An AI-generated summary may omit important details or misrepresent a publication.

**Recommendation:** Preserve access to the original research information.

**Proposed implementation:**
- Display the publication title and authors where available.
- Show the abstract or relevant source text when permitted.
- Provide a link to the original publication.
- Distinguish the original abstract from the AI-generated summary.
- Avoid presenting a summary as a substitute for reading the original research.

**Evaluation:** Compare generated summaries with the original abstracts and document material omissions or unsupported additions.

### 6.5 Language-Aware Search

**Problem:** Medical terminology resources may have limited language coverage, and an Arabic query may not map directly to an English-indexed medical concept.

**Recommendation:** Evaluate Arabic-to-English query handling and terminology mapping as a separate feature.

**Proposed implementation:**
- Accept Arabic and English search terms.
- Where appropriate, map an Arabic query to a candidate English medical term.
- Allow users to inspect the original terminology.
- Indicate when an equivalent cannot be verified.
- Avoid implying that all underlying sources provide complete Arabic coverage.

**Evaluation:** Test Arabic queries, English queries, spelling variations, and terms with multiple possible meanings.

### 6.6 Responsible Educational Use

**Problem:** Users may mistake AI-generated medical explanations for personalized medical advice.

**Recommendation:** Make the platform's educational purpose clear.

**Proposed implementation:**
- Display a medical information disclaimer.
- Avoid presenting generated content as a diagnosis or treatment recommendation.
- Communicate uncertainty when the available source material is insufficient.
- Encourage consultation with a qualified healthcare professional for personal medical concerns.

**Evaluation:** Review the interface and sample outputs for potentially misleading wording and inappropriate certainty.

---

## 7. Proposed Evaluation Plan

The following plan is a project proposal, not a report of completed testing.

| Feature | Evaluation method | Evidence to collect |
|---|---|---|
| Medical terminology search | Test a predefined set of terms and queries. | Search results, relevance, and terminology-source links. |
| Arabic-English terminology | Review a test set of bilingual terms. | Verified equivalents, definition quality, and unresolved mappings. |
| Medical research explorer | Test searches for known publications and topics. | Retrieval results, publication metadata, and working source links. |
| AI-generated explanations | Compare outputs with retrieved source content. | Factual consistency, clarity, relevance, and unsupported statements. |
| Research summaries | Compare summaries against original abstracts. | Preserved key findings, omissions, and unsupported additions. |
| General usability | Conduct a small user test with representative tasks. | Task completion, observed problems, and participant feedback. |
| Error handling | Test empty queries, missing results, and unavailable services. | Error messages, graceful failure, and recovery behavior. |

### Proposed Evaluation Metrics

Where applicable, the project may report:

- **Retrieval relevance:** Whether returned results address the query.
- **Source traceability:** Whether displayed claims can be checked against the referenced material.
- **Factual consistency:** Whether generated statements agree with the supplied sources.
- **Task completion rate:** The percentage of test tasks completed successfully.
- **Response time:** Time taken to retrieve and display results.
- **Functional test pass rate:** The percentage of executed functional test cases that pass.

The team should define the test set and scoring rules before reporting numerical results. Results must reflect actual testing rather than estimates presented as completed measurements.

---

## 8. Limitations of the Current Review

This review has several limitations:

1. It is a focused preliminary review and does not include an exhaustive search of all relevant academic databases.
2. The selected studies investigate different research questions and use different methods; their numerical findings are not directly interchangeable.
3. The review does not establish the clinical safety or effectiveness of MedNexus AI.
4. The reviewed multilingual terminology study does not establish complete Arabic terminology coverage.
5. The proposed RAG workflow may improve traceability but cannot eliminate hallucinations or incorrect interpretation.
6. The suitability of each external API depends on its documentation, availability, access restrictions, licensing, and response format.
7. The review does not constitute a comprehensive market analysis of existing medical information platforms.

These limitations should be considered when interpreting the findings and deciding which features can realistically be implemented within the project timeline.

---

## 9. Conclusion

The reviewed literature indicates that medical LLM applications require careful evaluation, transparent use of evidence, and attention to the limitations of generated content.

Research on healthcare RAG systems supports investigating source-grounded generation as a way to make AI responses more traceable, while also highlighting the need to evaluate retrieval quality, factual consistency, and ethical considerations.

Research on multilingual terminology systems further supports treating medical terminology as a standardized concept with context and language-specific equivalents, rather than relying solely on direct translation.

Based on these findings, MedNexus AI will prioritize medical terminology lookup, research exploration, source attribution, and AI-assisted explanations that can be checked against retrieved material.

The project will evaluate its implemented features through documented test cases and will report limitations honestly. Any additional feature will depend on feasibility, available data, and the remaining project timeline.

---

## 10. References

### Reference 1

Bedi, S., Liu, Y., Orr-Ewing, L., et al. (2025). Testing and Evaluation of Health Care Applications of Large Language Models: A Systematic Review. *JAMA, 333*(4), 319–328.

DOI: https://doi.org/10.1001/jama.2024.21700

PubMed: https://pubmed.ncbi.nlm.nih.gov/39405325/

### Reference 2

Wei, Q., Yao, Z., Cui, Y., Wei, B., Jin, Z., & Xu, X. (2024). Evaluation of ChatGPT-generated medical responses: A systematic review and meta-analysis. *Journal of Biomedical Informatics, 151*, 104620.

DOI: https://doi.org/10.1016/j.jbi.2024.104620

PubMed: https://pubmed.ncbi.nlm.nih.gov/38462064/

### Reference 3

Amugongo, L. M., Mascheroni, P., Brooks, S., Doering, S., & Seidel, J. (2025). Retrieval augmented generation for large language models in healthcare: A systematic review. *PLOS Digital Health, 4*(6), e0000877.

DOI: https://doi.org/10.1371/journal.pdig.0000877

PubMed: https://pubmed.ncbi.nlm.nih.gov/40498738/

Full text: https://pmc.ncbi.nlm.nih.gov/articles/PMC12157099/

### Reference 4

Noll, R., Storf, H., & Schaaf, J. (2025). HealthTermFinder: Enhancing Multilingual Interoperability. *Studies in Health Technology and Informatics, 327*, 2–6.

DOI: https://doi.org/10.3233/SHTI250262

PubMed: https://pubmed.ncbi.nlm.nih.gov/40380374/

---

## 11. Related Technical Documentation

The following official resources support the technical investigation and potential integration of medical information sources. They are technical references, not substitutes for academic research papers.

### Medical Terminology

**National Library of Medicine — Medical Subject Headings (MeSH)**  
https://www.ncbi.nlm.nih.gov/mesh/

**MeSH database search through NCBI E-utilities**  
https://www.ncbi.nlm.nih.gov/books/NBK25499/

### Medical Research Publications

**PubMed**  
https://pubmed.ncbi.nlm.nih.gov/

**NCBI APIs and E-utilities documentation**  
https://www.ncbi.nlm.nih.gov/home/develop/api/

### General Health Information

**MedlinePlus Web Service documentation**  
https://medlineplus.gov/about/developers/webservices/

MedlinePlus is intended for supported consumer-health topics; it should not be treated as a complete dictionary of specialized medical terminology.

### AI Integration

**Google AI Studio**  
https://aistudio.google.com/

**Gemini API documentation**  
https://ai.google.dev/gemini-api/docs

**Gemini API reference**  
https://ai.google.dev/api

These resources may support AI-generated explanations, but their inclusion does not imply that integration, medical quality validation, or production readiness has been completed.

---

## 12. Project Status and Outstanding Work

This document summarizes the research reviewed to inform the proposed system design. It does not claim that all recommended improvements have already been implemented.

The following tasks remain subject to project progress:

- Confirm the final external data sources and their usage conditions.
- Implement the selected APIs and validate their responses.
- Create a reproducible test set for medical terminology and AI-generated explanations.
- Evaluate Arabic-English terminology handling.
- Record actual functional and usability testing results.
- Obtain and document lecturer feedback when it is provided.
- Add the official grading criteria if they are supplied by the course or lecturer.

The project team should update this document as implementation and evaluation progress.