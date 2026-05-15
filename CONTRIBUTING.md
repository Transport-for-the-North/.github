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

For any new Python package repositories consider using the
[cookiecutter-caf](https://github.com/Transport-for-the-North/cookiecutter-caf) template, which
will create a repository structure matching the TfN standards.

> [!TIP]
> See the CAF template's [pyproject.toml](https://github.com/Transport-for-the-North/cookiecutter-caf/blob/main/%7B%7B%20cookiecutter.project_slug%20%7D%7D/pyproject.toml)
> to see how these tools have been set up in order to meet TfN's coding standards.

## Releases

The CAF codebases follow [Semantic Versioning](https://semver.org/); the convention
for most software products. In summary, this means the version numbers should be read in the
following way.

Given a version number MAJOR.MINOR.PATCH (e.g. 1.2.3), increment the:

- MAJOR version when you make incompatible API changes,
- MINOR version when you add functionality in a backwards compatible manner, and
- PATCH version when you make backwards compatible bug fixes.

> [!NOTE]
> The main branch of a CAF repository contains a work in progress, and  may **not**
> contain a stable version of the codebase. We aim to keep the main branch stable, but for the
> most stable versions, please see repository tags or releases page.
