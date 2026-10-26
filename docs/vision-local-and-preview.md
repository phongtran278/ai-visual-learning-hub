# Run VISION locally and prepare safe Azure preview

## Local development

Requirements: Node.js 22 and npm.

```bash
npm ci
npm run dev
```

Open the address Vite prints (usually http://localhost:5173). For a production build: `npm run build` and `npm run preview`. All app content is served statically. Answers and progress are saved locally in the browser under `vision-lab-m01-progress-v1`.

## GitHub CI
`.github/workflows/vision-ci.yml` builds main branch and pull requests; it does **not** deploy.

## Azure preview (manual and opt-in)
`.github/workflows/vision-deploy.yml` runs **only on manual workflow_dispatch** and targets the GitHub environment `vision-preview`.

Before activating:
1. Review resource availability and GitHub Education credits in your own accounts. They are **not yet verified**.
2. Provision a VISION-only Azure storage account, or an isolated resource demonstrably separate from PlotFlow. **Never point the workflow at the PlotFlow storage account.**
3. Enable Static Website on that resource and configure index/error pages.
4. Create a least-privilege deployment identity. Store Azure service principal JSON in GitHub environment secret `VISION_AZURE_CREDENTIALS`, and storage account name in environment variable `VISION_AZURE_STORAGE_ACCOUNT`. Azure identity must have a suitable Storage Blob Data Contributor role scoped to the VISION resource.
5. Set environment approval protections where available, then manually trigger the deployment workflow. Check the Azure static website endpoint.
6. Only afterward configure `vision.phongtran.tech` through Cloudflare. Verify no conflicting DNS record or Worker route exists; use a separate Worker route/TLS strategy if required. Do not change PlotFlow routes.

**Important:** Azure Storage static website endpoints and Cloudflare custom-hostname HTTPS cannot be assumed to work together simply by creating a CNAME. Validate origin host headers, certificate and route handling; add a dedicated Cloudflare Worker proxy only when necessary.

## Rollback
Until production DNS is configured, rollback means stop the preview workflow and delete or replace files in the isolated VISION account. For production, preserve a previously known-good build and DNS/Worker configuration before release. No deployment or DNS changes were performed when this file was created.

## Privacy and limits
There is no login, sync, remote scoring or AI API. Local drafts and self-reported milestones are browser-local and can be lost if site data is cleared. Do not treat lesson completion as competency certification.
