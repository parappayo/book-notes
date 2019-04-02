# About

[The Hitchhiker's Guide to Python: Best Practices for Development](https://docs.python-guide.org/)
by Kenneth Reitz and Tanya Schlusser
published by O'Reilly, 2016

# Thoughts

Delivers on its promise to be a next-steps guide beyond the basics of Python development. Contains lots of helpful, practical advice.

# Take-Aways

* Deciding between [Python 2 or Python 3](https://wiki.python.org/moin/Python2orPython3) can be difficult.
* [Python 3 changes](https://docs.python.org/3/whatsnew/3.0.html#text-vs-data-instead-of-unicode-vs-8-bit) a lot to do with networking, sockets, web, unicode support: "Everything you thought you knew about binary data and Unicode has changed."
* Never is often better than right now, aka YAGNI
* Dictionary `get` method can take a default value to return
* prefer joining lines by enclosing them in parenthesis over using a backlash
* `string.format()` params use curly braces in the format str, can be positional or named
* TDD tip: a failing test can be used to document what you wanted to accomplish next
* best practice for projects to include README, LICENSE, INSTALL, TODO, and CHANGELOG
* logging practices: add the NullHandler to your project's logger to suppress logger warnings; do not add other handlers if you project is used as a library, since it should be up to the user what the log behaviour is; Twelve-Factor App defines some best practices for logging; logging configuration can be loaded from an INI file or set as a dictionary
* some very readable Python projects: HowDoI, Diamond, Tablib, Requests, Werkzeug, Flask
* your app should respect system configuration, eg. check proxy servers with `urllib.requests.getproxies()`, use standard POSIX and [Linux environment variables](https://help.ubuntu.com/community/EnvironmentVariables)

# Gotchas

* beware using `in` operator on lists; unlike sets and dicts (hash tables), it will do a time consuming sequential search
* immutable strings have the same performance concern as C#; rather than appending in a tight loop, consider building a list and joining as a final step
* US users cannot legally use your code if no license is provided
* Do not change the symbolic link to the Python executable; you will create a mismatch between the exe and the libs
* Virtual environments contain hardcoded paths in executables, cannot move them once created
* test tearDown does not run if the test failed
* Python 2 classes don't always inherit from Object

# Concepts

* `*` operator - creates N references to the same value (reference semantics)
* `@classmethod` - class method decorator, causes the first argument to be a reference to the class rather than self
* `@property` - class method decorator works in conjuction with `__get__()`, `__set__()`, and `__delete__()`
* `__init__.py` - if this exists in a directory, it is considered a Python package; top level is the root package; common practice to have an empty `__init__.py` for a root package when the subpackages do not share code
* `in` operator - prefer `in` to dictionary `has_key` method
* arbitrary keyword argument dictionary - aka `**kwargs`, but try to use a more sensible name
* Behaviour-Driven Development (BDD) - introduced by Dan North in 2003
* Data Model - from the Python docs: namespace tools, dir(), globals(), locals()
* diagnostic vs audit logging - consider that business events should be logged for audit purposes, not just debugging
* doctest - introduced in Python 2.1, typically less detailed than unit tests but provide a nice combination of test and doc
* double underscore variable -used to ignore a result; single underscore is used as an alias for gettext.gettext(), also value of the last op on the cli
* immutable types - data cannot change; strings, numbers, and tuples are immutable
* keyword arguments - optional args with default values
* late binding closures - var values are looked up at the time of the inner function call; lambda expressions work the same way as def functions
* list comprehension - `[value for __ in range(N)]` creates N copies (value semantics)
* monkey patch - change a method at runtime
* mutable default arguments - modifying the value of an argument changes the default value for subsequent calls; default values use reference semantics, handy for implementing a cache
* mutable types - data can be modified in-place; cannot be dictionary keys; lists are mutable
* Open Source Initiative (OSF) - provides some popular licenses
* PEP 20 - The Zen of Python by Tim Peters; guiding principles; import this
* PEP 282 - describes logging
* PEP 3129 - Python 3 allows decorators on classes
* PEP 3132 - Python 3 new method of unpacking vars (* operator)
* PEP 318 - introduced decorators, a better alternative to manually wrapping a method
* PEP 343 - introduces the with statement as an alternative to try/finally
* PEP 374 - concise comparison of Subversion, Bazaar, Git, Mercurial
* PEP 8 - code style guidelines; being pep8-ed is having a coder throw the style guideline book at you; a foolish consistency is the hobgoblin of little minds
* Percent-Style Formatting - the old hat string formatting style
* Python Software Foundation (PSF) - provides their own software license for contributors
* Pythonista - veteran python developer
* Ravioli Code - many similar little pieces of logic without good structure; one symptom is that it is hard to remember what types are used for what purpose * because many similarly named, closely related types exist
* RTMF - Read the Manual, Friend!
* shims directory - used by pyenv
* site-packages directory - where user installed packages are kept
* TLDRLegal - web site that summarizes popular open source licenses
* underscore prefix - variables can only be private by convention, using underscore prefix is encouraged
* vendorized dependencies - package defines external dependencies, typically in a folder called vendor or packages
* Vogon poetry - do not read out loud

# Techs

* ActivePython - ActiveState commercial distro, paid license
* Anaconda - stats Python distro
* AUFS - union file system
* Autoenv - lightweight alternative to virtualenv
* Buildout - provides Python "recipes" which are like modules
* Canopy - scientific and analytic Python distro; Enthought commercial distro
* chroot - system-level containers
* Conda - Anaconda package manger, similar functionality to pip, virtualenv, and Buildout
* contextlib library - turn functions into context managers, suppress exceptions, redirect streams
* CPython - the reference implementation, compatible with C extension modules
* Diamond - publishes system metrics (memory, CPU, disk), open sourced by BrightCove in 2011, can be easily extended with custom collector classes
* Docker - environment isolation via containers
* Docker Hub - Docker container repo
* egg - old Python packages; a zip file with a particular structure
* Electron - cross-platform desktop apps using HTML, CSS, JS
* Eric Python IDE - free, lightweight, good debugger
* fixture - package for mocking data stores populated with data, eg. SQLAlchemy, Storm
* Gherkin - syntax to describe behaviours for BDD
* Graphite - metrics back-end, published to by Diamond, open sourced by Orbitz in 2008
* Intel Distribution for Python - commercial distro, free; includes SciPy stack
* IronPython - .NET implementation of Python, convenient interface to .NET
* JBehave - BDD for Java, Better Software magazine article in 2006, Dan North "Introducing BDD" article
* Jython - compiles to JVM bytecode, convenient interface to Java libs
* Komodo - polyglot IDE
* Lettuce, Behave - packages for BDD
* Linux Containers - system-level containers
* MicroPython - Python 3 optimized for microcontrollers
* mock - introduced in Python 3.3, provides the mock decorator
* NINJA-IDE - free IDE, lightweight
* nose - extends unittest with automatic test discovery
* pip - better than Setuptools because you can uninstall packages, better error messages
* POSIX - Portable Operating System Interface; a set of IEEE standards
* pyboard - uses MicroPython as an OS
* PyCharm - IDE with free, paid versions
* pyenv - use multiple versions of Python side-by-side
* pylint - will warn if a variable gets assigned more than one type of value
* PyPI - Python Package Index; package repo
* PyPy - performant Python written in a Python subset, up to 5 times faster than CPython, back-end (bytecode) supports C, CIL, JVM
* pytest - alternative to unittest
* python.vim - syntax plug-in for vim
* PythonNet - .NET package for integrating with a native Python install; the complement to IronPython, can use both at once
* reStructured Text - understood by PyPI
* Setuptools - provides easy_install for managing packages
* Skulpt - JavaScript implementation of Python
* Sphinx - popular Python doc tool, https://readthedocs.org/
* Sphinx - tool for building docs
* Spyder - free IDE popular with scientific distros
* Stackless - patched CPython with tasklets, optz
* Sublime Text - preferred; by Jon Skinner; written in Python; Anaconda package turns it into a better Python IDE
* tox - package for test environment configuration
* Ubuntu 15.10 - first release where Python 3 is the installation default
* unittest - test classes derive from TestCase, test methods start with "test", setUp and tearDown methods
* unittest2 - back-ported version of unittest for older versions of Python (2.6 and earlier)
* virtualenv - create isolated Python environments, stores it in the working dir
* virtualenvwrapper - keeps virtual environments together in one dir, provides commands to switch between them
* wheels - new python binary package format, replaces eggs; PEP 427
* WingIDE - paid IDE with great debugger

# Publications

* Self-Reliance - book by Ralph Waldo Emerson
* Test Driven Development with Python book - Obey the Testing Goat!
* The Cucumber Book - Pragmatic Bookshelf book about BDD

# Names Dropped

* Benjamin Gleitzman - author of HowDoI
* Kenneth Retiz - Tablib author
* Raymond Hettinger - Python coding expert; Beyond Pep 8 at PyCon 2015
* Tim Peters - Python core developer, creator of timsort

# Code

Cli

* `pip install --upgrade pip`
* `pip freeze > requirements.txt`
* `pip install -r requirements.txt` # dangerous if a virtualenv is not currently in use

Python

* `for index, item in enumerate()` # better than using a counter var
* `filename, ext = "path.txt".rsplit(".", 1)`
* `import sys` followed by `type(sys)` # modules are a type
* `sys.path` # tells you where the Python environment will search for modules
* `mod = __import__()`  # replaced by importlib.import_module in Python 3.1, backported to 2.7
* `dir(mod)`, `getattr(mod, name)`, `issubcliass(attr, ClassName)` # Python reflection samples
