# AgroConnect

AgroConnect is a farmer-focused crop support application for disease identification, agronomy guidance, and local agricultural services. Its design prioritizes field use, regional languages, and clear next steps for Indian farmers.

> **Project status:** The computer-vision and retrieval-augmented generation (RAG) pipelines have been developed and are ready for product integration. Connecting them to the app experience, replacing the current fixed example API response, and completing deployment and operational checks remain pending. The current API response does not analyze an uploaded image.

## Where the project stands

The original Android/web app was built with Flutter and includes crop, market, weather, and profile workflows. The current web-first direction uses an Angular frontend and a Java Spring Boot API. The crop-image and RAG pipelines are developed; the current API still returns a fixed example until those pipelines are connected to the app experience.

| Area | Current state |
| --- | --- |
| Frontend | Angular starter with a diagnosis form and dashboard components |
| Backend | Spring Boot API with `POST /api/diagnose`; currently returns mock data |
| Image diagnosis | ResNet50-based crop-image pipeline is ready for product integration; not connected to the current API |
| Treatment guidance | Sentence-BERT retrieval and Gemma-based answer pipeline are ready for product integration; not connected to the current API |
| PWA and offline use | Product goals; installability and offline behavior still need implementation and testing |
| Dataset | Original project notes report 450+ crop diseases and pests; dataset contents and evaluation have not been independently verified here |
| Languages | English, Hindi, and Marathi are included in the design preview; application-level localization still needs implementation and validation |

The tracked starter uses Angular 17, TypeScript 5.3, Java 21, and Spring Boot 3.3.1. Treat these as the repository's current baseline, not a recommendation to use the newest versions. Review framework support and compatibility before upgrading dependencies.

## Run the starter

Prerequisites: Node.js and npm, Java 21, and Maven. Run each service in a separate terminal from the repository root.

```bash
cd frontend
npm install
npm start
```

```bash
cd backend
mvn spring-boot:run
```

The frontend development server is available at `http://localhost:4200` by default. The backend runs on `http://localhost:8080`. The diagnosis endpoint is `POST /api/diagnose` and currently returns a static example, regardless of the image. There is no Maven wrapper in the repository, so these instructions use an installed Maven command.

## Resume development

Start by making the existing application reproducible and connecting its completed AI pipelines:

1. Run the frontend and backend using the instructions above; record any setup or build failures.
2. Connect the existing image-diagnosis pipeline through a documented request/response contract with image validation and tests for invalid, unsupported, and valid requests.
3. Connect the existing RAG pipeline to reviewed agronomy documents and return traceable sources with each answer.
4. Create a dataset inventory and a repeatable evaluation split before training or selecting a model. Track crop, disease, image source, license, and other available provenance metadata.
5. Complete PWA installability, offline behavior, accessibility, and localized UX as testable features.
6. Add monitoring, privacy controls, operational runbooks, and deployment checks before production release.

## AI modernization direction

The existing ResNet50 image and Gemma-based RAG pipelines are developed and ready for app integration. Model upgrades are optional follow-up work, selected only when reproducible results on AgroConnect data justify them.

- **Vision:** Benchmark maintained image-classification or vision-embedding models against a simple baseline. Measure per-crop and per-disease precision and recall, calibration, performance on field photos, latency, and device or hosting cost. Include image-quality checks and allow the system to abstain when confidence is low. A generative vision model should not be the sole authority for a disease diagnosis.
- **Retrieval and generation:** Keep agronomy documents versioned and traceable to their sources. Compare hybrid keyword/vector retrieval and reranking on a reviewed question set. Return citations with recommendations, validate structured model output, and say when the sources do not support an answer.
- **Model flexibility:** Put model access behind a small provider/service boundary. Record model and prompt versions so providers can be evaluated or changed without rewriting the user experience.
- **Trust and field readiness:** Have qualified reviewers check treatment advice and translations. Test unsupported languages, conflicting sources, uncertain predictions, low connectivity, and privacy/retention behavior for uploaded crop images.

The remaining work is product integration and deployment; the existing AI pipelines do not need a ground-up rebuild.

## Proposed wireframes

[View the implementation-ready screen designs](docs/wireframes.html). Home puts photo-based crop diagnosis first, then local weather and advisory, followed by a horizontally scrollable crop-guide list. Five fixed tabs follow the original app: Home, Crops, Prices, Weather, and Profile. Additional screens cover a crop library and growing guide, AI chat, farmer community, mandi prices, and state/crop-specific schemes. English, Hindi, and Marathi previews are available. Current diagnosis, weather, market, community, and scheme data services still need app integration before deployment.

## Existing AI pipeline resources

The following notebooks document the existing model and retrieval pipelines. They are separate from the runnable web application and still need to be connected to its API and deployment workflow.

- [Crop disease image-embedding notebook (Google Colab)](https://colab.research.google.com/drive/1Ofhbm7w5_ieNhxDtnmfKlPlw8ZnU7sO-?usp=sharing)
- [RAG treatment-guidance notebook (Google Colab)](https://colab.research.google.com/drive/1V5oEq-q5Ypiri3eCXti7sOdwXQVyHoQB)

The original project notes cite [TNAU crop protection](https://agritech.tnau.ac.in/crop_protection/crop_prot.html), [Plantix plant diseases](https://plantix.net/en/library/plant-diseases/), [ICAR](https://icar.org.in/), [DARE](https://dare.gov.in/en), and [PPQS](https://ppqs.gov.in/) as potential data or information sources. Check the terms, attribution requirements, and suitability of each source before using its material in a dataset or production feature.

## Project docs

- [Proposed wireframes](docs/wireframes.html)
- [Project board](PROJECT_BOARD.md)
- [Issue backlog](GITHUB_ISSUES.md)
- [Contributing guide](CONTRIBUTING.md)

Contributions are welcome in reproducible evaluation, data documentation, AI integration, PWA behavior, accessibility, and multilingual UX. See the [contributing guide](CONTRIBUTING.md) before opening a change.
