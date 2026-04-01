# MichaelChallis.github.io 

This repository contains the source code for my personal academic website, built with Jekyll.

## Local development

1. Install Ruby, Bundler, and Node.js.
2. Install dependencies:
   ```bash
   bundle install
   ```
3. Run the site locally:
   ```bash
   bundle exec jekyll serve -l -H localhost
   ```
4. Open http://localhost:4000.

## Automatic CV sync from CV repo

This repo includes a GitHub Actions workflow at `.github/workflows/sync_cv.yml` that keeps the downloadable CV in sync with your CV repository.

### Configure once

In this website repository, open **Settings → Secrets and variables → Actions → Variables** and add:

- `CV_REPO` — the source repo in `owner/repo` format (for example `MichaelChallis/cv`).
- `CV_BRANCH` — branch containing the built PDF (for example `main`).
- `CV_PDF_PATH` — path to the PDF in that repo (for example `output/cv.pdf`).

### How updates happen

The workflow runs when:

- a `repository_dispatch` event of type `cv_updated` is received,
- manually via **Run workflow**,
- or every 12 hours on a schedule.

When it runs, it downloads the source PDF, updates `files/cv.pdf` (and keeps `files/Michael_Challis_CV.pdf` in sync for backwards compatibility), then commits and pushes only if a change is detected.

### Optional: trigger from your CV repo on push

In your CV repo, add a workflow that dispatches to this site repo after generating/pushing your latest PDF:

```yaml
name: Notify website CV update

on:
  push:
    branches: [main]

jobs:
  notify:
    runs-on: ubuntu-latest
    steps:
      - name: Dispatch update event to website repo
        env:
          GH_TOKEN: ${{ secrets.WEBSITE_REPO_TOKEN }}
        run: |
          curl -L \
            -X POST \
            -H "Accept: application/vnd.github+json" \
            -H "Authorization: Bearer ${GH_TOKEN}" \
            https://api.github.com/repos/<your-username>/<your-website-repo>/dispatches \
            -d '{"event_type":"cv_updated"}'
```

> `WEBSITE_REPO_TOKEN` should be a PAT with `repo` access (or fine-grained equivalent) that can dispatch events to your website repo.

## Content structure

- `_pages/` for standalone pages.
- `files/` for downloadable assets (for example, CV PDFs).
- `images/` for profile and website images.
- `_data/` for structured site data.

This repository has been cleaned up from the default Academic Pages example content so only core site content remains.
