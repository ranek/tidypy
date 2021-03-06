*****************
TidyPy Change Log
*****************

.. contents:: Releases


0.6.0 (2018-xx-xx)
==================

**Enhancements**

* Enabled the ``pydiatra`` tool on windows (thanks @jwilk).
* Upgraded the ``pylint`` and ``vulture`` tools.
* Upgraded the ``pep8-naming`` plugin of the ``pycodestyle`` tool.


0.5.0 (2018-05-05)
==================

**Enhancements**

* Added ``manifest`` and ``pydiatra`` tools.
* Upgraded the ``pylint`` tool.
* Upgraded the ``pep8-naming`` plugin of the ``pycodestyle`` tool.
* Added some convenience handling of the ``License`` vs ``Licence`` and
  ``LicenceClassifier`` vs ``LicenseClassifier`` codes reported by ``pyroma``.
* Added the first draft of the project documentation.
* Added an ``extensions`` command that will output a listing of all the
  available tools, reports, and extenders that are available.

**Fixes**

* Fixed the character location reported in ``pylint`` issues being off-by-one.
* Fixed various issues with the ``pyroma`` tool leaking problems to stderr.


0.4.0 (2017-12-02)
==================

**Enhancements**

* Added a ``sphinx-extensions`` option to the ``rstlint`` tool to enable the
  automatic recognition of Sphinx-specific extensions to ReST (Sphinx must be
  installed in the same environment as TidyPy for it to work).
* Added a ``ignore-roles`` option to the ``rstlint`` tool to help deal with
  non-standard ReST text roles.
* Changed tool execution from a multithreaded model to multiprocess. Larger
  projects should see an improvement in execution speed.

**Changes**

* The ``--threads`` option to the ``check`` command has been changed to
  ``--workers``.

**Fixes**

* Fixed an issue that caused the ``pylint`` tool to crash when it encountered
  ``duplicate-code`` issues on files that are being excluded from analysis.


0.3.0 (2017-11-18)
==================

**Enhancements**

* Added ``ignore-directives`` and ``load-directives`` options to the
  ``rstlint`` tool to help deal with non-standard ReST directives.
* Added support for the ``extension-pkg-whitelist`` option to the ``pylint``
  tool.
* Added ``install-vcs`` and ``remove-vcs`` commands to install/remove
  pre-commit hooks into the VCS of a project that will execute TidyPy.
  Currently supports both Git and Mercurial.

**Changes**

* Changed the ``merge_issues`` and ``ignore_missing_extends`` options to
  ``merge-issues`` and ``ignore-missing-extends`` for naming consistency.
* Replaced the ``radon`` tool with the traditional ``mccabe`` tool.

**Fixes**

* Fixed issue that caused TidyPy to spin out of control if you used CTRL-C to
  kill it while it was executing tools.
* Fixed issue where ``pylint``'s ``duplicate-code`` issue was reported only
  against one file, and it was usually the wrong file. TidyPy will now report
  an issue against each file identified with the duplicate code.
* Numerous fixes to support running TidyPy on Windows.


0.2.0 (2017-11-04)
==================

**Enhancements**

* Added a ``2to3`` tool.
* All tools that report issues against Python source files can now use the
  ``# noqa`` comment to ignore issues for that specific line.
* Added support for the ``ignore-nosec`` option in the ``bandit`` tool.
* Added the ability for TidyPy configurations to extend from other
  configuration files via the ``extends`` property.
* Upgraded the ``vulture`` tool.
* Upgraded the ``pyflakes`` tool.

**Changes**

* Changed the ``--no-merge`` and ``--no-progress`` options to the ``check``
  command to ``--disable-merge`` and ``--disable-progress``.
* The ``check`` command will now return ``1`` to the shell if TidyPy finds
  issues.
* No longer overriding ``pycodestyle``'s default max-line-length.

**Fixes**

* If any tools output directly to stdout or stderr, TidyPy will now capture it
  and report it as a ``tidypy:tool`` issue.
* Fixed crash/hang that occurred when using ``--disable-progress``.


0.1.0 (2017-10-15)
==================

* Initial public release.

