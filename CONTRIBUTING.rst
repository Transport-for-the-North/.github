===============
Ways Of Working
===============

.. _`pydocstyle`: http://www.pydocstyle.org/en/stable/index.html
.. _`black`: https://github.com/psf/black
.. _`pylint`: https://github.com/PyCQA/pylint
.. _`mypy`: https://github.com/python/mypy
.. _`pyproject.toml`: pyproject.toml
.. _`CAF coding standards`: https://transport-for-the-north.github.io/CAF-Handbook/contribution/coding_standards/overview.html
.. _`pytest`: https://docs.pytest.org/en/stable/

Transport for the North (TfN) encourages a collaborative way of working and as such is happy
to accept contributions on various aspects of our repositories, including:

- Code maintenance and development
- Feature requests and bug reporting
- Documentation feedback and suggestions
- Code examples and use cases

Feedback & Requests
-------------------

For any feedback, or requests, on the code, documentation or anything else, please create a GitHub
issue to describe your suggestion and open the discussion. We have created some issue templates to
show the information we expect for different types of suggestions.

Changes & Development
---------------------

Prior to making any changes, please consider creating an issue to discuss your proposed changes
and get feedback from people on anything to consider during implementation.

Any changes to the code or documentation should be worked on in a separate fork (or branch if
you're an organisation member) of the repository. For significant pieces of new functionality
a draft pull request should be opened during development of the code. This creates a central point
to communicate about the code being written and to keep a record of any potential issues. Once
development is complete and the code ready for review, the draft pull request can be promoted to
a normal pull request.

For smaller pieces of work, such as a bug fix, a normal pull request can be made straight away.

Coding Style
^^^^^^^^^^^^

TFN's coding follows the `CAF coding standards`_, before contributing to this repository we would
recommend reading through the standards. However, at a high level the coding standards can be
summarised as:

- Code uses numpy-style doc-strings, checked with `pydocstyle`_
- Code must be formatted with `black`_
- Code must be checked, and all errors corrected, by running `pylint`_
- Code must be checked, and all errors corrected, by running `mypy`_
- Code must include unittests, and integration tests (where relevant), built with `pytest`_

See this project's `pyproject.toml`_ to see how these tools have been set up in order
to meet TFN's coding standards.
