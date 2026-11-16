# GitHub Standards

This document defines practical standards for using [Git](https://git-scm.com/) and GitHub in a
collaborative software project.

> [!NOTE]
> See [Contributing Guide](../CONTRIBUTING.md) for repository-level contribution guidance.

- [What is stored on GitHub](#what-is-stored-on-github)
- [Issues](#issues)
- [Pull Requests](#pull-requests)
- [Commits](#commits)
- [Branches](#branches)
- [Creating a Repository](#creating-a-repository)
  - [Repository Templates](#repository-templates)

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
- Parameters derived from real data, unless there is explicit documented approval confirming they
  are safe and appropriate to store.
- Project reports - reports containing any details on results or similar.
- IDE (VS Code/PyCharm) or local environment settings.
- Account details/passwords.

> [!IMPORTANT]
> Repository history should be treated as potentially public and permanent. When a repository is
> made public, previous commits are also exposed, so do not commit data or restricted content even
> temporarily in private repositories.

## Issues

- Create an issue for bugs, technical debt, and feature requests, use relevant issue templates.
- Use clear titles and enough context to reproduce or implement the change.
- Keep one issue focused on one problem/outcome where practical, *optionally create high-level
  summary issues (with sub-issues) for larger tasks.*
- Link pull requests to their related issues.
- Use relevant labels and fields so work can be triaged and tracked.
- Close issues with a short summary of what changed and links to related pull requests where
  available.

## Pull Requests

- Open a pull request for all changes merged into `main`.
- Prefer small, focused pull requests over large mixed changes.
- Use draft pull requests early for visibility and discussion.
- Include a clear summary, validation evidence, and any rollout/risk notes.
- Request review and address feedback before merge.
- For broader changes, separate domain-review concerns from code-quality concerns in the PR
  description so reviewers can focus on their area.

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
- For large or interdependent changes, split work into staged pull requests where practical to
  reduce review and integration risk.

> [!NOTE]
> Some repositories use a dev branch, in addition to main, for staging changes before
> merging into main.

## Creating a Repository

- Check whether an existing repository can host the work before creating a new one.
- Use one of TfN's [Repository Templates](#repository-templates) when creating a new
  repository:
  - For Python packages, use
    [cookiecutter-caf](https://github.com/Transport-for-the-North/cookiecutter-caf).
- Configure core defaults at creation time:
  - branch protection on `main`
  - required CI checks (code linting, automated testing, release and deployments),
    these are defined in the relevant repository template
  - code owners/review settings
  - license and README

> [!TIP]
> Check [`{{ cookiecutter.project_slug }}/.github/workflows` (cookiecutter-caf)](https://github.com/Transport-for-the-North/cookiecutter-caf/tree/main/%7B%7B%20cookiecutter.project_slug%20%7D%7D/.github/workflows)
> for examples of GitHub actions for a Python repository.

### Repository Templates

TfN uses [cookiecutter](https://cookiecutter.readthedocs.io/en/stable/) for repository templates.
Cookiecutter creates a new project from a standard template so new repositories start with a
consistent structure, tooling, and default configuration.

To use a template, follow the Cookiecutter usage guidance:
[Create a project from a Cookiecutter template](https://cookiecutter.readthedocs.io/en/stable/README.html#usage).

Current TfN template(s):

- [cookiecutter-caf](https://github.com/Transport-for-the-North/cookiecutter-caf) - default
  template for Python package repositories, supports both CAF and non-CAF packages.
