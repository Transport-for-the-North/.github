# GitHub Standards

This document defines practical standards for using [Git](https://git-scm.com/) and GitHub in a
collaborative software project.

> [!NOTE]
> See [Contributing Guide](../CONTRIBUTING.md) for repository-level contribution guidance.

- [Issues](#issues)
- [Pull Requests](#pull-requests)
- [Commits](#commits)
- [Branches](#branches)
- [Creating a Repository](#creating-a-repository)

## What is stored on GitHub

Should be on GitHub:

- Source code.
- Methodology, user guide and/or code documentation, this should be limited to objective
  descriptions and be written in plaintext formats e.g. markdown or restructured text.
- Code dependencies.
- Code specific configuration e.g. Python's pyproject.toml.

> [!NOTE]
> Documentation can include dummy example inputs and outputs to show how processes work,
> if used these should be completely randomly generated and should not contain any
> real data.

Should **not** be on GitHub:

- Data - no data should be stored on any GitHub repository.
- Parameters derived from real data.
- Project reports - reports containing any details on results or similar.
- IDE (VS Code/PyCharm) or local environment settings.
- Account details/passwords.

## Issues

- Create an issue for bugs, technical debt, and feature requests.
- Use clear titles and enough context to reproduce or implement the change.
- Keep one issue focused on one problem/outcome where practical.
- Link pull requests to their related issues.

<!-- TODO: Add issue lifecycle guidance (labels, ownership, prioritisation, and closure conventions). -->

## Pull Requests

- Open a pull request for all changes merged into `main`.
- Prefer small, focused pull requests over large mixed changes.
- Use draft pull requests early for visibility and discussion.
- Include a clear summary, validation evidence, and any rollout/risk notes.
- Request review and address feedback before merge.

<!-- TODO: Add minimum review expectations (for example, when domain review and code-quality review should be split). -->

## Commits

- Make commits atomic: each commit should represent one logical change.
- Write commit messages in imperative mood (for example, "Add input validation").
- Avoid committing generated artifacts unless the repository explicitly tracks them.
- Keep commit history readable (squash/fixup when appropriate before merge).

> [!TIP]
> See [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) for some
> more specific examples of commit formats to follow.

## Branches

- Keep `main` stable and releasable.
- Protect `main` with pull-request-only merges and required checks.
- Do all development on topic branches; never commit directly to `main`.
- Use short-lived branches with descriptive names (for example, `feat/...`, `fix/...`).
- Rebase or merge from `main` regularly to reduce integration risk.

<!-- TODO: Add guidance for large/interdependent changes (for example, staged integration branches and merge strategy). -->

## Creating a Repository

- Check whether an existing repository can host the work before creating a new one.
- Start from an approved template where available.
- Configure core defaults at creation time:
  - branch protection on `main`
  - required CI checks
  - code owners/review settings
  - issue and pull request templates
  - license and README

<!-- TODO: Add baseline GitHub Actions guidance for new repositories (required checks, triggers, and ownership). -->
<!-- TODO: Add external collaboration guidance for private vs public repositories (direct access vs fork-based workflow). -->
