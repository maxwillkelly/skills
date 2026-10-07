---
name: follow-pr-template
description: Follow the repository's pull request template when creating PRs. Use when the user asks to create, open, or submit a pull request.
---

# Follow PR Template

When asked to create a pull request, always check for a PR template before writing the description.

## Workflow

1. **Look for a template** in the repository:
   - `.github/pull_request_template.md`
   - `.github/PULL_REQUEST_TEMPLATE/` (directory of templates)
   - `docs/pull_request_template.md`

2. **If a template exists**, use it as the structure for the PR body. Fill in every section the template defines. Do not skip sections — if a section is not applicable, write "N/A" or a brief explanation of why it does not apply.

3. **If no template exists**, write a concise PR description covering:
   - What changed and why
   - How to test it
   - Any breaking changes or migration notes

4. **Never invent your own format** when a template is available. The template exists so that reviewers get a consistent structure across PRs.
