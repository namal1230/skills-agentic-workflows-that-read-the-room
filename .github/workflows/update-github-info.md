---
name: update-github-info
summary: Draft updates to Mona's GitHub Info website content from official GitHub sources.
description: Read Mona's notes and the GitHub Blog/Changelog, update site/content/github-info.md, and propose the changes in a pull request for Mona to review.
on:
  schedule:
    - cron: '0 9 * * *'
  workflow_dispatch: {}
safe-outputs:
  create-pull-request:
    title-prefix: "[mona site update] "
    body: "Propose updates to site/content/github-info.md based on Mona's notes and official GitHub sources. Do not write directly to main."
tools:
  edit:
    allowed:
      - notes/mona-notes.md
      - site/content/github-info.md
  web-fetch:
    allowed:
      - https://github.blog/latest/
      - https://github.blog/changelog/
      - https://awesome-copilot.github.com/workflows/
  network:
    allowed:
      - github.blog
      - github.com
      - awesome-copilot.github.com
---

# Update Mona's GitHub Info website

Read `notes/mona-notes.md` before making any edits.

Use these official sources when drafting changes:
- `https://github.blog/latest/`
- `https://github.blog/changelog/`
- `https://awesome-copilot.github.com/workflows/`

Update `site/content/github-info.md` with concise, practical GitHub guidance for Mona's readers.
Add or refresh a section called `Latest GitHub Updates` and include source context from the GitHub Blog, GitHub Changelog, or Awesome Copilot Workflows where appropriate.

Do not write directly to `main`.
Use `safe-outputs` with `create-pull-request` to open a pull request for Mona to review.
Include the phrases `GitHub Blog`, `GitHub Changelog`, `safe-outputs`, `create-pull-request`, and `pull request` in your instructions.
