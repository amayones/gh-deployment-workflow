# GitHub Pages Deployment Workflow

A GitHub Actions workflow to automatically deploy static HTML sites to GitHub Pages whenever the `index.html` file is updated.

## Project URL
https://roadmap.sh/projects/github-actions-deployment-workflow

## Features

- **Automatic Deployment** - Triggers on index.html changes
- **GitHub Pages Integration** - Direct deployment to GitHub Pages
- **Artifact Management** - Secure file upload and deployment
- **Branch Protection** - Only deploys from main branch
- **Minimal Configuration** - Ready-to-use workflow setup

## Usage

### Setup:
1. Enable GitHub Pages in repository settings
2. Set Pages source to "GitHub Actions"
3. Push workflow file to `.github/workflows/deploy.yml`

### Deployment:
```bash
# Any change to index.html will trigger deployment
git add index.html
git commit -m "update: homepage content"
git push origin main
```

## Requirements

- GitHub repository with Pages enabled
- Static HTML content (index.html)
- GitHub Actions permissions configured
- Main branch as default branch

## Workflow Configuration

The workflow automatically:
1. Checks out repository code
2. Configures GitHub Pages environment
3. Uploads site artifacts
4. Deploys to GitHub Pages

## Installation

1. Create the workflow directory:
```bash
mkdir -p .github/workflows
```

2. Copy the workflow file:
```bash
cp deploy.yml .github/workflows/
```

3. Commit and push:
```bash
git add .github/workflows/deploy.yml
git commit -m "ci: add GitHub Pages deployment workflow"
git push origin main
```

## Workflow Triggers

This workflow triggers on:
- Push to `main` branch
- Changes to `index.html` file only
- Manual workflow dispatch (optional)

## Permissions

Required permissions:
```yaml
permissions:
  contents: read
  pages: write
  id-token: write
```