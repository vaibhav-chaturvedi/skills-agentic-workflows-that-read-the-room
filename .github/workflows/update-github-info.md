---
name: update-github-info
description: Draft updates for Mona's GitHub Info website from official GitHub sources and open a review PR.
on:
  workflow_dispatch:
  schedule:
    - cron: '17 9 * * *'
safe-outputs:
  create-pull-request:
    title-prefix: "[mona] "
    draft: true
    fallback-as-issue: false
tools:
  edit:
  web-fetch:
network:
  allowed:
    - github.com
    - github.blog
    - awesome-copilot.github.com
---

# Update Mona's GitHub Info website

Read `notes/mona-notes.md` before making any edits.

Use the repository guidance and reference files available through GitHub repository API tools. Prefer those tools over terminal, CLI, or sandboxed commands when checking repo context or instructions.

Use web-fetch to read external public guidance and official sources relevant to the update:
- GitHub Blog: https://github.blog/latest/
- GitHub Changelog: https://github.blog/changelog/
- Awesome Copilot workflows: https://awesome-copilot.github.com/workflows/
- Additional public guidance when it helps explain a change or context

Review the relevant repository content and update `site/content/github-info.md` with concise, practical summaries of the latest GitHub developments and relevant workflow inspiration from Awesome Copilot. Keep the writing clear and useful for readers who want a quick understanding of recent GitHub updates.

Open a pull request for Mona to review. Use `safe-outputs` with `create-pull-request` so the agent can propose the change without writing directly to `main`. The pull request should be focused on the GitHub Info update, include a clear Mona reference, and be ready for human review before merging.

Do not compile this workflow. Treat this as a markdown workflow definition to be reviewed and run in GitHub Actions when needed.
