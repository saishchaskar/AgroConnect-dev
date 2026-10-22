# GitHub Issues for AgroConnect

This file contains contributor-ready issue ideas for the AgroConnect project, based on the current project scope in the README and implementation notes.

## Issue 1: Improve the crop disease dataset quality and diversity

**Description**
The project has built a dataset with more than 450 crop diseases and pests across India. The next logical step is to improve data quality, consistency, and coverage.

**Why this matters**
Model performance relies heavily on dataset diversity and quality. This task directly improves disease detection accuracy and generalization.

**Acceptance criteria**
- Review duplicates and low-quality images
- Improve class balance across major crop diseases
- Add metadata such as crop type, growth stage, and region when available
- Document dataset composition and versioning

**Labels**
machine-learning, data, enhancement

---

## Issue 2: Add formal evaluation metrics for the disease prediction model

**Description**
The project uses a pretrained ResNet50-based approach for disease matching. It should now include reproducible benchmarking and evaluation metrics.

**Why this matters**
Without formal metrics, it is difficult to judge whether the model is improving over time.

**Acceptance criteria**
- Add precision, recall, and F1 score reporting
- Generate confusion matrices for disease classes
- Compare baseline and fine-tuned models
- Add a reproducible evaluation script

**Labels**
machine-learning, research, enhancement

---

## Issue 3: Improve RAG retrieval quality for treatment and management guidance

**Description**
The project uses a retrieval-augmented generation pipeline to answer questions on disease causes, symptoms, and treatment. Retrieval quality should be tuned and evaluated.

**Why this matters**
Better retrieval leads to more accurate and grounded answers from the LLM.

**Acceptance criteria**
- Tune chunking and overlap strategy for agronomic documents
- Review embedding quality and retrieval relevance
- Improve prompt design for crop disease recommendations
- Add evaluation notes for retrieval quality and answer grounding

**Labels**
ai, rag, enhancement, help wanted

---

## Issue 4: Validate and expand multilingual support for broader accessibility

**Description**
The project mentions multilingual integration, but the README does not yet describe validation or coverage for this feature.

**Why this matters**
Broader accessibility and adoption depend on quality multilingual experiences.

**Acceptance criteria**
- Validate translated prompts and generated responses
- Add fallback handling for unsupported languages
- Document supported languages and limitations
- Test language-specific UI text and response generation

**Labels**
ai, localization, enhancement

---

## Issue 5: Package the project for reproducible deployment and contribution onboarding

**Description**
The project appears to be a combination of notebooks, model artifacts, and app logic. Packaging the workflow in a more reproducible way would make it easier for contributors to explore and improve.

**Why this matters**
Reproducibility is essential for ML and research-heavy projects.

**Acceptance criteria**
- Add environment setup instructions for Python and model dependencies
- Document dataset folder structure and notebook flow
- Add Docker or similar setup if feasible
- Create a clear contribution guide for researchers and developers

**Labels**
documentation, devops, enhancement

---

## Suggested contribution prompt

We welcome contributions in machine learning, data processing, RAG quality, frontend/mobile UX, multilingual support, and documentation. Please comment on the issue you want to work on and mention the issue title.
