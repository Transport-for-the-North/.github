# Python Standards

Outlined here are the standards / conventions used within TfN, and CAF, for writing Python
code. These standards should be adhered to in all new code...

> [!NOTE]
> See [Contributing Guide](../CONTRIBUTING.md) for TfN's full contribution guidance.

- [Dependency Management](#dependency-management)
  - [requirements.txt](#requirementstxt)
  - [Licenses](#licenses)
- [Linting Tools](#linting-tools)
  - [Ruff](#ruff)
  - [MyPy](#mypy)
- [Testing (pytest)](#testing-pytest)
- [Documentation](#documentation)
  - [Docstrings](#docstrings)
  - [Example Function Docstring](#example-function-docstring)
    - [Example Class Docstring](#example-class-docstring)
- [Notebooks](#notebooks)
  - [Alternatives](#alternatives)

> [!WARNING]
> TODO - this section is work-in-progress
>
> Existing docs:
>
> - [Coding Standards doc](https://transportforthenorth.sharepoint.com/:w:/r/sites/TAMEBusinessImprovements/Shared%20Documents/North/05%20Development/01%20Quality%20Handbook/01%20Code%20and%20Software%20Standards/Software%20Development%20and%20Coding%20Standards%20v2.0.docx?d=w64eb087c965f4e2abe2cf7e94986f6c6&csf=1&web=1&e=fCdK82)
> - [Python Style Guide and Workflows (PPT)](https://transportforthenorth.sharepoint.com/:p:/r/sites/TAMEBusinessImprovements/Shared%20Documents/North/05%20Development/01%20Quality%20Handbook/01%20Code%20and%20Software%20Standards/Python%20Style%20Guide%20and%20Workflows%20v1.pptx?d=w157335625e034cb59c47ee30970777a5&csf=1&web=1&e=YzFPBh)
> - [Python Coding Standards Crash Course (PPT)](https://transportforthenorth.sharepoint.com/:p:/r/sites/TAMEBusinessImprovements/Shared%20Documents/North/05%20Development/01%20Quality%20Handbook/01%20Code%20and%20Software%20Standards/Python%20Coding%20Standards%20Crash%20Course.pptx?d=wec21219f91094987b13d924153045048&csf=1&web=1&e=rkYquj)

## Dependency Management

### requirements.txt

### Licenses

## Linting Tools

### Ruff

### MyPy

## Testing (pytest)

## Documentation

### Docstrings

Docstrings should be written following the [Numpy docstring Style Guide](https://numpydoc.readthedocs.io/en/latest/format.html),
with the following exceptions:

- Type annotations should not be included in the docstring as they should already be
  in the signature, and sphinx adds them to the docstring when generating the web docs.
- Class (or instance) attributes should be documented below their definition instead
  of having a specific Attributes section in the class docstring, see
  [Example Class Docstring](#example-class-docstring).

### Example Function Docstring

> [!WARNING]
> TODO - this section is work-in-progress

```python
def test(a: int, b: str, option: dict[str, int] | None = None) -> dict[str, int]:
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

## Notebooks

[Jupyter Notebooks](https://docs.jupyter.org/en/latest/) (AKA IPython Notebooks) are documents
which contain computer code (usually Python) with plain language descriptions, data and
visualisations. Jupyter is a specific Python package / software for using notebooks but other
[alternatives](#alternatives) exist.

Notebooks are good for prototyping, sharing code-heavy methodologies and creating technical
reports with code and visualisations. They should not be used for complete models or tools as
they aren't very flexible and are difficult to integrate with larger pipelines, or processes.

> [!WARNING]
> Jupyter Notebooks should not be included in **any** git repositories because they store outputs
> within the file which can lead to data leaks, see [Alternatives](#alternatives) if you want
> to use notebooks within a git repository.

### Alternatives

There are some alternatives to Jupyter notebook format which do not store data/outputs within them
and are therefore much easier to store on git repositories. Two key alternatives are:

- [jupytext](https://jupytext.org/) - this is an extension to Jupyter notebooks which allows
  storing the notebook in various plain text formats but you can still work with them in Jupyterlab.
- [marimo](https://marimo.io/) - complete replacement for Jupyter Notebooks and Jupyter Lab.

> [!TIP]
> If you already use Jupyter then jupytext is the best choice as you can easily convert existing
> notebooks to plain Python format and continue working within Jupyter.
