# VISION / LAB

**Understand. Apply. Create.** An evidence-informed AI visual learning hub for designers.

**MVP status (2026-10-26):** interactive web UI committed; **not yet confirmed deployed to a public URL**. Curriculum and assessment are experimental, not UNESCO-approved or certified.

## Run the interactive MVP

Requires Node.js 22 and npm:

```bash
npm install
npm run dev
```

Open the local URL shown by Vite (usually `http://localhost:5173`). The interface includes a dashboard, seven-module overview, and M01 *Visual Brief & Creative Direction* in three interactive stages. The other six lessons are curriculum drafts, not yet interactive web modules.

**No AI API or account required.** Drafts and completion are saved to your browser only. Completion is self-reported, not certified assessment.

## Research and curriculum
- [UNESCO 12-block crosswalk](framework/unesco-12-competency-crosswalk.md)
- [Framework v0.3](framework/competency-framework.md)
- [Pilot curriculum](curriculum/pilot-curriculum-v0.1.md)
- [Rubric](framework/pilot-assessment-rubric-v0.1.md)
- [Evidence matrix](evidence/evidence-matrix.md)
- [Source registry](research/source-registry.md)
- [Research methodology](research/methodology.md)
- [Pilot-study protocol](curriculum/pilot-study-protocol-v0.1.md)

## Infrastructure
- Target hostname: **vision.phongtran.tech**
- Intended stack: static React/Vite build on **VISION-isolated Azure Storage Static Website**, Cloudflare DNS/proxy, GitHub Actions.
- [Local and preview setup](docs/vision-local-and-preview.md)
- [Deployment decision and safety gates](docs/deployment-vision.md)

GitHub CI checks the build. Deployment is **manual**, requires VISION-specific Azure credentials and storage account, and does not modify PlotFlow. No Azure/Cloudflare account configuration or live domain has been changed by these commits.

## Principles
Evidence transparency, version-aware tool guidance, meaningful practice and critique, responsible use and privacy. Users bring their own AI-generation subscriptions.

## Licensing
Code and educational-content licenses are not yet selected; do not assume MIT or Creative Commons licensing for repository content.
