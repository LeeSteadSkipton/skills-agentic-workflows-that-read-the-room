---
name: update-github-info
description: Draft practical GitHub Info website updates for Mona from her notes and official GitHub sources.
on:
  workflow_dispatch:
  schedule:
    - cron: "17 9 * * *"
safe-outputs:
  create-pull-request:
    title-prefix: "[mona] "
    draft: true
    fallback-as-issue: false
    base-branch: main
    allowed-files:
      - "site/content/github-info.md"
tools:
  edit:
  web-fetch:
network:
  allowed:
    - github.blog
    - github.com
---

# Update Mona's GitHub Info website

Read `notes/mona-notes.md` and the existing `site/content/github-info.md` before drafting any changes.

Use `web-fetch` to review both:
- GitHub Blog: https://github.blog/latest/
- GitHub Changelog: https://github.blog/changelog/

Update only `site/content/github-info.md` with concise, practical updates that help developers learn GitHub faster. Keep Mona's editorial focus and existing content structure. Mention the source when an update comes from the GitHub Blog or GitHub Changelog. Do not invent announcements or include information you cannot verify from the notes or official sources.

If there is a useful, verified update, propose the change by opening a draft pull request for Mona to review. Use a title that mentions Mona or GitHub Info, explain the sources and changes in the pull request description, and rely on `safe-outputs` with `create-pull-request`. Never write directly to `main` or change any other file. If there is no useful update, make no changes and do not open an empty pull request.
