# Ways Of Working

Transport for the North (TfN) encourages a collaborative way of working and as such is happy
to accept contributions on various aspects of our repositories, including:

- Code maintenance and development
- Feature requests and bug reporting
- Documentation feedback and suggestions
- Code examples and use cases

## Version Control

CAF codebases are all hosted on [GitHub](https://github.com/Transport-for-the-North)
and use [Git](https://git-scm.com/) for version control, see our [GitHub standards](standards/github.md)
for guidance.

> [!NOTE]
> Code [releases](#releases) are managed using Semantic Versioning.

## Feedback & Requests

If you have any feedback or requests on the code, documentation, or anything else, please create a GitHub
issue. We have created some issue templates to guide you through the information needed for different
types of suggestions, and opens the discussions for collaboration.

> [!NOTE]
> See [Issues Standards](standards/github.md#issues) for TfN's full guidance on creating
> issues.

### Security Reports

If you discover a potential security issue (for example an exposed secret or a vulnerability), do
not open a public issue with sensitive details. Report it privately to repository maintainers so it
can be investigated and resolved safely.

<!-- REVIEW: Confirm the preferred private reporting route (for example, GitHub Security Advisories or a dedicated contact point). -->

## Changes & Development

Prior to making any changes, please consider creating an issue to discuss your proposed changes.
This helps us to support you with the changes and provide wider context and considerations for your implementation.

Any changes to the code or documentation should be worked on in a separate fork (or branch if
you're an organisation member) of the repository. For significant pieces of new functionality
a draft pull request should be opened during development of the code. This creates a central point
to communicate about the code being written and to keep a record of any potential issues. Once
development is complete and the code ready for review, the draft pull request can be promoted to
a normal pull request.

For smaller pieces of work, such as a bug fix, a normal pull request can be made straight away.

> [!NOTE]
> See [PR Standards](standards/github.md#pull-requests) for TfN's full guidance on creating
> pull requests and issues.

### Pull Request Reviews

Before requesting review, complete the relevant local validation for your change:

- run formatting and linting checks
- run type checks (where used by the repository)
- run relevant tests
- test building documentation when docs or docstrings are changed

Pull request descriptions should include:

- a short summary of the change
- links to related issues
- validation evidence (commands run and key outcomes)
- notable risks, rollout considerations, or follow-up actions

> [!TIP]
> Draft pull requests can be created at the start of development
> on a new branch and should outline the plans for the work, see
> [Pull Requests (GitHub Standards)](standards/github.md#pull-requests) for more details

### Creating New Repositories

Before creating a new repository:

- Check whether an existing TfN repository can reasonably host the work.
- Find a suitable [TfN repository template](standards/github.md#repository-templates), e.g.
  for Python package repositories use
  [cookiecutter-caf](https://github.com/Transport-for-the-North/cookiecutter-caf).
- Configure baseline repository controls are in place:
  - branch protection
  - CI checks enabled for linting and tests
  - review settings configured

> [!NOTE]
> See [Creating a Repository Standards](standards/github.md#creating-a-repository) for TfN's
> full setup checklist.

### Coding Standards

Python is the most commonly used programming language used with TfN, it is also the preferred
language for most new tools. The main alternative is JavaScript / TypeScript which is used
within the Visualisation Framework.

#### Python

TFN's Python coding follows the [CAF Python standards](standards/python.md), before contributing to
this repository we would recommend reading through the standards. However, at a high level the coding
standards can be summarised as:

- Code must be formatted with [ruff format](https://docs.astral.sh/ruff/formatter/)
- Code must be checked, and all errors corrected, by running [ruff check](https://docs.astral.sh/ruff/linter/)
- Type annotations must be used and checked, and all errors corrected, by running [mypy](https://github.com/python/mypy)
- Code must include unittests, and integration tests (where relevant), built with [pytest](https://docs.pytest.org/en/stable/)

For any new Python package repositories use the
[cookiecutter-caf](https://github.com/Transport-for-the-North/cookiecutter-caf) template, see
[Creating New Repositories](#creating-new-repositories) for details.

> [!TIP]
> See the CAF template's [pyproject.toml](https://github.com/Transport-for-the-North/cookiecutter-caf/blob/main/%7B%7B%20cookiecutter.project_slug%20%7D%7D/pyproject.toml)
> to see how these tools have been set up in order to meet TfN's coding standards.

#### JavaScript / TypeScript

JavaScript / TypeScript standards for the Visualisation Framework and related repositories will be
documented in a dedicated standards file.

<!-- TODO: Add JS/TS standards document and link it here once available. -->

## Releases

CAF codebases follow [Semantic Versioning](https://semver.org/) (`MAJOR.MINOR.PATCH`) for
release versions.

> [!NOTE]
> The main branch of a CAF repository is a work in progress and should be kept stable where
> practical. For guaranteed stable versions, use repository tags or GitHub releases.

Semantic Versioning can be summarised as specific increments e.g. given a version number
MAJOR.MINOR.PATCH (e.g. 1.2.3), increment the:

- MAJOR version when you make incompatible API changes (e.g. 2.0.0),
- MINOR version when you add functionality in a backwards compatible manner (e.g. 1.3.0), and
- PATCH version when you make backwards compatible bug fixes (e.g. 1.2.4).
