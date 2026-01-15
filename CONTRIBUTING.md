# Ways Of Working

Transport for the North (TfN) encourages a collaborative way of working and as such is happy
to accept contributions on various aspects of our repositories, including:

- Code maintenance and development
- Feature requests and bug reporting
- Documentation feedback and suggestions
- Code examples and use cases

## Feedback & Requests

If you have any feedback or requests on the code, documentation, or anything else, please create a GitHub
issue. We have created some issue templates to guide you through the information needed for different types of suggestions, and opens the discussions for collaboration.

## Version Control

The vis-core codebase is hosted on [GitHub](https://github.com/Transport-for-the-North)
and use [Git](https://git-scm.com/) for version control.

> [!NOTE]
> Packages releases are managed using [Semantic-Release](https://github.com/semantic-release/semantic-release).

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

### Coding Style

TFN's coding follows the [CAF coding standards](https://transport-for-the-north.github.io/CAF-Handbook/contribution/coding_standards/overview.html),
before contributing to this repository we would
recommend reading through the standards. However, at a high level the coding standards can be
summarised as:

- Code must be formatted with [ruff format](https://docs.astral.sh/ruff/formatter/)
- Code must be checked, and all errors corrected, by running [ruff check](https://docs.astral.sh/ruff/linter/)
- Type annotations must be used and checked, and all errors corrected, by running [mypy](https://github.com/python/mypy)
- Code must include unittests, and integration tests (where relevant), built with [pytest](https://docs.pytest.org/en/stable/)

See the CAF template's [pyproject.toml](https://github.com/Transport-for-the-North/cookiecutter-caf/blob/main/%7B%7B%20cookiecutter.project_slug%20%7D%7D/pyproject.toml)
to see how these tools have been set up in order to meet TfN's coding standards.

## Releases

TfN Vis-Core follows [Semantic Versioning](https://semver.org/); the convention
for most software products. In summary, this means the version numbers should be read in the
following way.

Given a version number MAJOR.MINOR.PATCH (e.g. 1.2.3), increment the:

- MAJOR version when you make incompatible API changes,
- MINOR version when you add functionality in a backwards compatible manner, and
- PATCH version when you make backwards compatible bug fixes.

### Version Bump Rules

| Commits in PR | Version Bump | Example |
|---------------|--------------|---------|
| Only `fix:` | **Patch** | 0.5.0 → 0.5.1 |
| Any `feat:` | **Minor** | 0.5.0 → 0.6.0 |
| Any `feat!:` or `BREAKING CHANGE:` | **Major** | 0.5.0 → 1.0.0 |
| Only `docs:`, `chore:`, `test:` | **No release** | — |

When a PR contains multiple commit types, the **highest impact** wins:

BREAKING CHANGE (feat!) > feat > fix

---

## Developer Workflow

## 1. Create a Feature Branch

git checkout main
git pull origin main
git checkout -b feature/my-new-feature

## 2. Make Changes and Commit

Use **Conventional Commits** format:

### Bug fixes (patch release)
git commit -m "fix: resolve map tooltip positioning"
git commit -m "fix: correct legend formatting"

### New features (minor release)
git commit -m "feat: add export shapefile"
git commit -m "feat: add link width slider"

### Breaking changes (major release)
git commit -m "feat!: redesign configuration API"

### No release triggered
git commit -m "docs: update README examples"

git commit -m "chore: update dependencies"

git commit -m "test: add unit tests for utils"

git commit -m "refactor: simplify layer rendering logic"


## 3. Push and Create a Pull Request

git push origin feature/my-new-feature

Create a PR on GitHub targeting `main`.

## 4. Merge to Main

When the PR is merged, **semantic-release automatically**:

1. Analyzes all commits in the PR
2. Determines the version bump
3. Updates `package.json` with the new version
4. Publishes to GitHub Packages
5. Creates a GitHub Release with auto-generated notes
6. Tags the commit (e.g., `v0.6.0`)
7. Commits the updated `package.json` back to `main`

> [!NOTE]
> The main branch of the repository will contain work in progress, and  may **not**
> contain a stable version of the codebase. We aim to keep the main branch stable, but for the
> most stable versions, please see repository tags or releases page.
