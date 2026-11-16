# Python Standards

This document defines practical standards for writing maintainable, production-ready Python.
Apply these standards to all new code and to modified code where reasonable.

The standards can be summarised into 4 main points:

- Follow [PEP-8](https://peps.python.org/pep-0008/) Python standards, using ruff (and pylint)
  to handle formatting and checking.
- Include type annotations, using mypy to automatically check types.
- Docstrings should be written for **all** public modules, functions and classes.
- Support, at minimum, the latest 3 Python versions for CAF packages unless there is a clear
  project-specific reason not to.

> [!NOTE]
> See [Contributing Guide](../CONTRIBUTING.md) for TfN's full contribution guidance.

- [Dependency Management](#dependency-management)
  - [Python Version Support](#python-version-support)
  - [requirements.txt](#requirementstxt)
  - [Licenses](#licenses)
- [Linting Tools](#linting-tools)
  - [Ruff](#ruff)
  - [MyPy](#mypy)
- [Module and Package Structure](#module-and-package-structure)
- [Documentation](#documentation)
  - [Docstrings](#docstrings)
    - [Example Function Docstring](#example-function-docstring)
    - [Example Class Docstring](#example-class-docstring)
  - [Sphinx Documentation](#sphinx-documentation)
  - [Examples Folder](#examples-folder)
- [Testing (pytest)](#testing-pytest)
- [Notebooks](#notebooks)
  - [Alternatives](#alternatives)
- [Versioning](#versioning)

## Dependency Management

### Python Version Support

- CAF packages should support at least the latest 3 Python versions.
- Other TfN packages may support fewer versions where newer Python features are required.
- Set and document supported versions in project configuration (for example `pyproject.toml`) and
  keep CI aligned with that support policy.

### requirements.txt

- Define runtime dependencies in `requirements.txt`.
- Pin direct dependencies to stable ranges or exact versions suitable for reproducible environments.
- Keep dependency files up to date when adding, removing, or upgrading packages.
- Avoid unused dependencies.

### Licenses

- Only add dependencies with a GitHub-recognized approved license, or explicit manual approval
  before use.
- Verify package licenses from source repositories and registry metadata before adding
  dependencies.
- Review transitive dependencies when introducing new top-level packages.
- If license obligations require attribution or notices, include them in project documentation.

## Linting Tools

Linting tools provide consistent automated checks for code style, correctness, and type safety,
helping teams catch issues early and keep codebases maintainable.

### Ruff

Ruff is the primary linter and formatter, it should be ran on all new code and
any old code should be migrated to ruff when changes are made. Ruff has two key
functions:

- `ruff format` - formats the Python code without changing it's meaning.
- `ruff check` - checks the Python code against ruff's rules.

Additionally, ruff also supports automated fixes of certain rules with two flags for
the check command:

- `ruff check --fix` - this will fix any rules considered "safe" and should be used.
- `ruff check --fix --unsafe-fixes` - this will fix any rules ruff considers "unsafe", this
  could change the exact implementation of the code logic so should be checked more
  thoroughly if used.

> [!NOTE]
> Ruff does not currently support all Pylint rules, so pylint should be used as
> a secondary linter to catch anything ruff misses.
> [Issue 970](https://github.com/astral-sh/ruff/issues/970) on ruff's GitHub repository
> keeps track of the implementation of Pylint rules.

### MyPy

MyPy is the primary static type checker, and requires correct and detailed
[type annotations](https://typing.python.org/en/latest/spec/annotations.html) to work properly.
Type annotations should be written on all new functions and methods and should be added to
existing code whenever changes are made.

## Module and Package Structure

- Prefer clear module responsibilities over many very small files.
- Split modules when they become hard to describe briefly in module-level documentation.
- Use sub-packages sparingly; introduce them when they separate distinct functionality or
  dependencies.
- Prefer concise, clear module names; use multi-word names only when needed for clarity.

> [!TIP]
> Use the [cookiecutter-caf](https://github.com/Transport-for-the-North/cookiecutter-caf)
> template to generate the Python package structure, among other things.

## Documentation

Python projects should include enough documentation for other developers to understand what the
code does, how to run it, and where its boundaries are.

- Packages and modules should include docstrings that explain their purpose and key behavior.
- Public functions, classes, and methods should include docstrings where users need usage and
  behavior details.
- Standalone scripts should include a top-level module docstring describing intended use, required
  inputs/configuration, and notable limitations.

### Docstrings

Docstrings should be written following the [Numpy docstring Style Guide](https://numpydoc.readthedocs.io/en/latest/format.html),
with the following exceptions:

- Type annotations should not be included in the docstring as they should already be
  in the signature, and sphinx adds them to the docstring when generating the web docs.
- Class (or instance) attributes should be documented below their definition instead
  of having a specific Attributes section in the class docstring, see
  [Example Class Docstring](#example-class-docstring).

Docstrings contain different sections, e.g. parameters, returns, raises... (see
[Numpy docstring Style Guide](https://numpydoc.readthedocs.io/en/latest/format.html) for full
details), these should only be included when they add useful information. For example
a "Raises" section should be include to describe the key errors which are likely to be raised
by the function during expected use, it doesn't need to include a full list of all possible
errors.

#### Example Function Docstring

```python
def parse_limits(
    source: str, default: dict[str, int] | None = None
) -> dict[str, int]:
    """Parse numeric limits from a source string.

    Parameters
    ----------
    source
        Input text containing key=value limit pairs.
    default
        Optional fallback mapping used when a key is missing.

    Returns
    -------
    dict[str, int]
        Parsed limits as integer values.

    Raises
    ------
    ValueError
        If a value cannot be converted to an integer.
    """
```

#### Example Class Docstring

Example of class docstring with class attributes and instance attributes documented

```python
class Test:
    """Does something.

    More details explained here.

    Parameters
    ----------
    x, y
        Number for x and y - similar parameters can be documented together.
    mode
        Method to do.
    """

    class_attribute: str = "default"
    """Attribute stored within the class."""

    def __init__(self, x: int, y: int, mode: str) -> None:
        """Init docstring is optional and should only be used for containing extra
        information about the class initilisation which isn't relevant for most
        usecases but is potentially interesting for some.
        """

        # Documentation for attributes which are also parameters is contained within
        # the class docstring, but could be (optionally) duplicated here if it is useful to users
        self.mode = mode

        self.instance_attribute = self.some_func(x, y)
        """Attribute only available on class instances."""
```

### Sphinx Documentation

We use [Sphinx](https://www.sphinx-doc.org/en/master/) to build package documentation from
docstrings and supporting [reStructuredText](https://www.sphinx-doc.org/en/master/usage/restructuredtext/index.html)
pages. This is why module, class, and function docstrings should stay clear, accurate, and up to date.

A typical docs layout (as used by the CAF Python template) is:

- `docs/`
  - `source/` - documentation source files and Sphinx configuration.
  - `requirements.txt` - documentation build dependencies.
  - `Makefile` and `make.bat` - local documentation build commands.

Standalone scripts that are part of a package should still include module-level docstrings so
their purpose and usage can be surfaced in generated docs where relevant.

### Examples Folder

CAF-style Python repositories include an `examples/` folder to hold runnable code examples
that support user documentation.

- `examples/*.py` lightweight Python scripts should be written to show examples in how to use
  the package code, *these are picked up by Sphinx Gallery and rendered into the docs examples
  pages.*
- `examples/GALLERY_HEADER.rst` provides introductory text for the generated examples section.

In the standard Sphinx setup, these examples are included in the built documentation via the
`sphinx_gallery.gen_gallery` configuration in `docs/source/conf.py`.

> [!NOTE]
> Example config files, or other dataset examples, could be included in this folder.
> However, these **should not contain real data** and should just show the structure
> of the config.

## Testing (pytest)

- Use `pytest` for unit and integration tests.
- Add or update tests for all behavior changes and bug fixes.
- Keep tests deterministic, isolated, and readable.
- Run relevant tests locally before opening a pull request.

## Notebooks

[Jupyter Notebooks](https://docs.jupyter.org/en/latest/) are useful for exploration, prototyping,
and technical communication, but should not be committed to repositories.

- Do not include `.ipynb` files in repositories.
- Keep production logic in Python modules/packages.
- Use text-based alternatives for notebook-style workflows, see [Alternatives](#alternatives).

<!-- REVIEW: Confirm whether the notebook prohibition should remain absolute or allow exceptions in some repositories. -->

### Alternatives

There are notebook alternatives and workflows that are easier to review in Git:

- [jupytext](https://jupytext.org/) for text-based notebook pairing and cleaner diffs.
- [marimo](https://marimo.io/) for reactive, Python-native notebooks stored as `.py` files.

> [!TIP]
> If you already use Jupyter then jupytext is the best choice as you can easily convert existing
> notebooks to plain Python format and continue working within Jupyter.

## Versioning

[Semantic Versioning](https://semver.org/)
