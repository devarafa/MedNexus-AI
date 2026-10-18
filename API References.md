# MedNexus AI — API References & Testing Log

This document collects the official API documentation, tested request URLs, and technical resources used during the development of MedNexus AI.

**Purpose:** Keep all API resources in one place for future implementation, testing, and troubleshooting.

---

## 1. NCBI MeSH — Medical Terminology Search

**Purpose:** Search medical terms and retrieve terminology information, identifiers, synonyms, and definitions when available.

### Official Resources
- MeSH Database: https://www.ncbi.nlm.nih.gov/mesh/
- MeSH Advanced Search: https://www.ncbi.nlm.nih.gov/mesh/index
- NCBI E-utilities Documentation: https://www.ncbi.nlm.nih.gov/books/NBK25501/

### Tested Request — Search for Myocardium

```text
https://eutils.ncbi.nlm.nih.gov/entrez/eutils/esearch.fcgi?db=mesh&term=Myocardium&retmode=json
```

**What it does:** Searches the MeSH database for the medical term `Myocardium` and returns matching record identifiers in JSON format.

### Tested Request — Retrieve a MeSH Record

```text
https://eutils.ncbi.nlm.nih.gov/entrez/eutils/esummary.fcgi?db=mesh&id=68009206&retmode=json
```

**What it does:** Retrieves a summary for a MeSH record. The tested record returned terminology information, including a scope note and synonyms.

**Important limitation:** MeSH should not be assumed to provide comprehensive Arabic terminology or Arabic definitions. Arabic search support requires additional handling and testing.

---

## 2. PubMed E-utilities — Medical Research Explorer

**Purpose:** Search medical research papers and retrieve publication metadata and abstracts when available.

### Official Resources
- PubMed: https://pubmed.ncbi.nlm.nih.gov/
- NCBI API Information: https://www.ncbi.nlm.nih.gov/home/develop/api/
- E-utilities Quick Start Guide: https://eutilities.github.io/site/Quick_Start/eu_quick/
- E-utilities Reference Guide: https://eutilities.github.io/site/Reference_Guide/a_reference/

### Request A — Search PubMed

```text
https://eutils.ncbi.nlm.nih.gov/entrez/eutils/esearch.fcgi?db=pubmed&term=diabetes&retmode=json
```

**Purpose:** Search for publications related to diabetes and retrieve matching PubMed identifiers.

### Request B — Retrieve Publication Metadata

```text
https://eutils.ncbi.nlm.nih.gov/entrez/eutils/esummary.fcgi?db=pubmed&id=42888932&retmode=json
```

**Purpose:** Retrieve publication metadata for a specific PubMed record.

### Request C — Retrieve a Publication Record / Abstract

```text
https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=pubmed&id=42888932&retmode=xml
```

**Purpose:** Retrieve the record in XML format. Abstract availability depends on the individual publication.

**Testing note:** We tested PubMed search, summary retrieval, and record retrieval. The requests above are reusable example URLs; verify each one again if you need to record its exact current output.

**Important limitation:** PubMed is primarily an English-language research resource. Arabic queries may need to be mapped to suitable English medical search terms.

---

## 3. MedlinePlus Web Service — General Health Information

**Purpose:** Retrieve general health topics and educational information.

### Official Resources
- MedlinePlus: https://medlineplus.gov/
- Web Service Documentation: https://medlineplus.gov/about/developers/webservices/
- MedlinePlus XML Files: https://medlineplus.gov/xml.html

### Tested Request — Diabetes

```text
https://wsearch.nlm.nih.gov/ws/query?db=healthTopics&term=diabetes
```

**What it does:** Searches English-language MedlinePlus health topics for diabetes.

### Additional Test — Myocardium

```text
https://wsearch.nlm.nih.gov/ws/query?db=healthTopics&term=myocardium
```

**Testing observation:** Initial testing showed that some medical terms, including `myocardium`, may return no results.

**Important limitations:**
- The Web Service supports English and Spanish health topics, not Arabic.
- It is intended for general health information, not as a comprehensive medical terminology dictionary.
- The documented service limit is 85 requests per minute per IP address.

**MedNexus AI usage:** Retrieve supported English health information and, where appropriate, provide it as context for a separately labeled Arabic or English AI explanation.

---

## 4. Gemini API — Bilingual AI Medical Explanation

**Purpose:** Generate simplified educational explanations in Arabic or English using retrieved medical information as context.

### Official Resources
- Google AI Studio: https://aistudio.google.com/
- Gemini API Documentation: https://ai.google.dev/gemini-api/docs
- Gemini API Reference: https://ai.google.dev/api
- Generate Content API Reference: https://ai.google.dev/api/generate-content
- Gemini API Pricing: https://ai.google.dev/gemini-api/docs/pricing

### API Endpoint

```text
https://generativelanguage.googleapis.com/v1beta/models/{model}:generateContent
```

Replace `{model}` with the selected model name.

**Testing status:** We tested prompts manually in AI Studio. The API still needs to be integrated into the project's backend and evaluated systematically.

### Important Implementation Notes
- Test both Arabic and English explanations.
- Pass retrieved medical source content to the model as context.
- Display original source information separately from AI-generated explanations.
- Link to the original source.
- Evaluate whether the AI introduces unsupported medical claims.
- Never expose the API key in the React frontend; keep it in the backend environment variables.

**Important limitation:** Arabic language support does not guarantee medical accuracy.

---

## 5. X-ray Image Analysis — Under Investigation

**Purpose:** Explore whether an appropriate pretrained medical imaging model or external inference API can be integrated.

**Current status:** No model or API has been approved for integration.

Before choosing one, evaluate:
- Intended imaging task.
- Model documentation and published evaluation.
- Dataset and limitations.
- Licensing.
- API availability and pricing.
- Input and output requirements.
- Integration complexity.
- Suitability for an educational demonstration.

Do not treat an available model as clinically reliable without appropriate supporting evidence.

---

## 6. API Testing Summary

| Service | Intended Use | Testing Status | Main Limitation |
|---|---|---|---|
| NCBI MeSH | Medical terminology | Basic search and record retrieval tested | Arabic coverage is not guaranteed |
| PubMed E-utilities | Medical research search | Search, metadata, and record retrieval tested | Arabic queries may require English-term mapping |
| MedlinePlus Web Service | General health information | Initial requests tested | English/Spanish topics; incomplete topic coverage |
| Gemini API | AI explanations | Manual prompt testing completed | Backend integration and quality evaluation remain |
| X-ray model/API | Experimental image analysis | Feasibility investigation pending | No model selected |

---

## 7. Recommended Source-Grounded Workflow

```text
User Query
    |
    v
React Frontend
    |
    v
Node.js / Express Backend
    |
    +--> Map Arabic query to an English medical term if needed
    |
    +--> Retrieve information from MeSH / PubMed / MedlinePlus
    |
    +--> Send relevant source content to Gemini
    |
    v
Return Results
    |
    +--> Original medical information
    +--> Source name and original link
    +--> AI-generated explanation
    +--> Educational-use disclaimer
```

Retrieval-based prompting may reduce unsupported statements, but it does not guarantee that every AI-generated claim is correct.

---

## 8. Future Testing Log

Record future testing results here.

| Date | API / Service | Request Tested | Result | Issue / Notes |
|---|---|---|---|---|
| | NCBI MeSH | Myocardium search | Initial test successful | |
| | NCBI MeSH | Record summary | Initial test successful | |
| | PubMed E-utilities | Search / summary / record retrieval | Initial tests successful | |
| | MedlinePlus | Diabetes search | Initial test successful | |
| | Gemini API | Arabic / English prompts | Manual testing completed | Source consistency requires evaluation |
| | X-ray model/API | Not selected | Pending | |

**Maintenance rule:** Keep the official documentation links even if a direct request stops working. Record the exact request, date, response, and error message whenever a new test is performed.