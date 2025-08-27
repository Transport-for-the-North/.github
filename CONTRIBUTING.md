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

- Code uses numpy-style doc-strings, checked with [pydocstyle](http://www.pydocstyle.org/en/stable/index.html)
- Code must be formatted with [black](https://github.com/psf/black)
- Code must be checked, and all errors corrected, by running [pylint](https://github.com/PyCQA/pylint)
- Code must be checked, and all errors corrected, by running [mypy](https://github.com/python/mypy)
- Code must include unittests, and integration tests (where relevant), built with [pytest](https://docs.pytest.org/en/stable/)

See the CAF template's [pyproject.toml](https://github.com/Transport-for-the-North/cookiecutter-caf/blob/main/%7B%7B%20cookiecutter.project_slug%20%7D%7D/pyproject.toml)
to see how these tools have been set up in order to meet TfN's coding standards.
