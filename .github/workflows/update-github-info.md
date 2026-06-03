---
name: update-github-info
summary: Draft updates to Mona's GitHub Info website content from official GitHub sources.
description: Read Mona's notes and the GitHub Blog/Changelog, update site/content/github-info.md, and propose the changes in a pull request for Mona to review.

on:
  schedule:
    - cron: '0 9 * * *'
  workflow_dispatch: {}

tools:
  edit:
    allowed:
      - notes/mona-notes.md
      - site/content/github-info.md

  network:
    allowed:
      - https://github.blog/
      - https://github.blog/changelog/
      - https://awesome-copilot.github.com/

  github:
    allowed:
      - create-check-run
      - create-pull-request

safe-outputs:
  create-check-run:
    output:
      summary: "Mona GitHub info update workflow executed"

  update-pull-request:
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