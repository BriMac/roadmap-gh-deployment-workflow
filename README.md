# GitHub Pages Deployment

A minimal static site deployed automatically to GitHub Pages via a GitHub Actions workflow. Pushing a change to `index.html` on the `main` branch triggers a redeploy.

Project #4 from the [roadmap.sh DevOps Projects](https://roadmap.sh/devops/projects) track.

## What it does

- Contains a simple `index.html` landing page
- A GitHub Actions workflow (`.github/workflows/deploy.yml`) deploys the site to GitHub Pages on every push to `main` that modifies `index.html`
- Pushes that don't change `index.html` (e.g., README tweaks) do not trigger a deploy, saving CI minutes

## Live site

Site is accessible at:
`https://brimac.github.io/roadmap-gh-deployment-workflow/`

## How it works

The workflow has four steps:

1. **Checkout** — clones the repo onto the runner (`actions/checkout@v4`)
2. **Setup Pages** — configures the Pages environment (`actions/configure-pages@v5`)
3. **Upload artifact** — packages the repo contents as a Pages artifact (`actions/upload-pages-artifact@v3`)
4. **Deploy** — publishes the artifact to GitHub Pages (`actions/deploy-pages@v4`)

The trigger (`on:`) is filtered to `push` events on `main` that touch `index.html`.

## Project reference

[roadmap.sh — GitHub Actions Deployment Workflow](https://roadmap.sh/projects/github-actions-deployment-workflow)
