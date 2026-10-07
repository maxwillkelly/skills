---
name: follow-angular-commit-conventions
description: Write and review Git commit messages using Angular commit conventions. Use when preparing commits or checking commit messages in a repository that follows Angular conventions, regardless of whether it uses Angular.
---

# Follow Angular Commit Conventions

## Workflow

1. Read repository instructions, contribution guidance, commitlint configuration, and recent commit messages. Explicit repository rules take precedence over these defaults; history is supporting evidence, not a reason to repeat invalid messages.
2. Inspect the actual diff. For a commit, use `git diff --cached` and check the staged file list. For a proposed message, use the supplied diff or change description. Do not claim unverified behaviour, tests, or issue resolution.
3. Choose the type and optional scope that describe the change. Use a repository-approved package or area for the scope; omit it when the change spans areas or no meaningful scope exists. Angular's own package allowlist applies when contributing to Angular, not to every repository using this format.
4. Draft the message using the format below, then check it against repository rules. If a commit-message linter is configured, use the existing validation command without adding dependencies or changing configuration.

Writing a message does not authorise staging files, creating a commit, amending history, or pushing. Perform those actions only within the user's requested scope, preserving unrelated work.

## Message Format

```text
<type>(<scope>): <summary>

<body>

<footer>
```

The header requires a type and summary; the scope is optional. Use an imperative, present-tense summary, starting with a lowercase letter and ending without a full stop. Follow the repository's configured length limits.

| Type | Use for |
| --- | --- |
| `build` | Build tooling or external dependencies |
| `ci` | CI configuration or scripts |
| `docs` | Documentation alone |
| `feat` | New functionality |
| `fix` | Bug corrections |
| `perf` | Performance improvements |
| `refactor` | Code restructuring without a feature or bug fix |
| `test` | Missing or corrected tests |

Treat additional types such as `chore` or `style` as repository extensions, not Angular defaults.

Separate header, body, and footer with blank lines. Angular requires a body of at least 20 characters except for `docs` commits. Explain the motivation and relevant change in behaviour in the body, using imperative, present-tense wording.

The optional footer holds issue references, breaking changes, or deprecations. Use `BREAKING CHANGE:` with a summary, then a blank line and migration details. Use `DEPRECATED:` with a summary and update guidance. Use closing references only for issues the change resolves; follow repository rules for tracker identifiers. Do not substitute a `!` header marker for Angular's breaking-change footer unless the repository permits that extension.

## Examples

```text
feat(skills): publish angular commit guidance

Provide reusable instructions so agents can prepare consistent messages
from the staged changes.

Refs MAX-156
```

```text
fix(config): require an explicit output directory

Prevent generated files from overwriting the caller's working directory.

BREAKING CHANGE: remove the default output directory

Pass --output with the destination directory when running the generator.
```

For a revert, prefix the original header with `revert: `. Include `This reverts commit <SHA>` and the reason in the body. Obtain the actual SHA from Git; do not invent one.

## Reference

Use [Angular's official commit message guidelines](https://github.com/angular/angular/blob/main/contributing-docs/commit-message-guidelines.md) when an Angular-specific detail needs checking.
