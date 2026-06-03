---
name: update-github-info
description: Read Mona's notes and official GitHub sources, update site/content/github-info.md, and propose the changes in a pull request for Mona to review.

on:
  schedule: daily
  workflow_dispatch: {}

tools:
  edit: {}
  web-fetch: {}
network:
  allowed:
    - github.blog
    - github.com
    - awesome-copilot.github.com
safe-outputs:
  create-pull-request:
    title-prefix: "[mona site update] "
    draft: true
    fallback-as-issue: false
    allowed-base-branches:
      - main
---

# Update Mona's GitHub Info website

Read `notes/mona-notes.md` before making any edits.

Use these official sources when drafting changes:
- GitHub Blog
- GitHub Changelog
- Awesome Copilot Workflows

Update `site/content/github-info.md` with concise, practical GitHub guidance for Mona's readers.

Add or refresh a section called `Latest GitHub Updates` and include source context from official sources.

Do not write directly to main.
Use safe-outputs and create-pull-request to open a pull request for review.