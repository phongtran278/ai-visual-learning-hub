# VISION — Deployment Decision

**Decision date:** 2026-10-26
**Product name:** VISION / LAB
**Intended subdomain:** vision.phongtran.tech
**Tagline:** Understand. Apply. Create.

## Confirmed product decisions
- Reuse existing Azure and Cloudflare **accounts**, while isolating VISION's app, deployment and data from PlotFlow.
- Keep source in this repository (do not merge PlotFlow runtime or stylesheet code).
- Prioritize a low-cost static MVP: Vite + React + Tailwind, Azure Storage Static Website, Cloudflare DNS/HTTPS, GitHub Actions for build/deploy.
- Initial learning progress stored locally in the browser. Learners use their own AI generation accounts; no paid model API is required for MVP.
- Use UNESCO-inspired progression with explicit attribution and independent Hub rubrics; see [crosswalk](../framework/unesco-12-competency-crosswalk.md).

## Deployment prerequisites — NOT YET VERIFIED
1. Check whether `vision.phongtran.tech` is free in Cloudflare DNS; **do not overwrite existing records**.
2. Check Azure subscription eligibility, available credits and quota, including any GitHub Education / Azure for Students benefits. Do not assume entitlement.
3. Choose an **isolated storage account/container** or other isolation strategy; do not replace PlotFlow's static website files.
4. Confirm DNS/TLS routing and Cloudflare Worker route design without changing PlotFlow's production routes.
5. Configure least-privilege GitHub Actions credentials and secrets; avoid committing keys.
6. Stage and test a preview build before pointing production DNS. Document rollback.

## State
This file records the domain and infrastructure **decision only**. No DNS, Azure resource, Cloudflare route, live deployment, or benefit eligibility has been created or verified by this document.
