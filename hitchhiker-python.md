# About

[The Hitchhiker's Guide to Python: Best Practices for Development](https://docs.python-guide.org/)
by Kenneth Reitz and Tanya Schlusser
published by O'Reilly, 2016

# Thoughts

A whirlwind tour of intermediate level Python development. Lots of practical advice; unlikely to age well, but captures the spirit of the era.

# Take-Aways

* If the implementation is easy to explain, it may be a good idea
* Deciding between [Python 2 or Python 3](https://wiki.python.org/moin/Python2orPython3) can be difficult.
* [Python 3 changes](https://docs.python.org/3/whatsnew/3.0.html#text-vs-data-instead-of-unicode-vs-8-bit) a lot to do with networking, sockets, web, unicode support: "Everything you thought you knew about binary data and Unicode has changed."
* Dictionary `get` method can take a default value to return
* `string.format()` params use curly braces in the format str, can be positional or named
* Prefer to join lines by enclosing them in parenthesis rather than using a backslash
* A failing test can be used to document what you wanted to accomplish next
* Best practice for projects to include README, LICENSE, INSTALL, TODO, and CHANGELOG
* Respect system configuration, eg. check proxy servers with `urllib.requests.getproxies()`, use standard POSIX and [Linux environment variables](https://help.ubuntu.com/community/EnvironmentVariables)
* Logging practices: add the NullHandler to project's logger to suppress warnings; do not add other handlers if you project is used as a library, since it should be up to the user what the log behaviour is; Twelve-Factor App defines some best practices for logging; logging configuration can be loaded from an INI file or set as a dictionary
* Very readable Python projects: HowDoI, Diamond, Tablib, Requests, Werkzeug, Flask
* Pythonic to use try/except to infer type

# Gotchas

* Beware using `in` operator on lists; unlike sets and dicts (hash tables), it will do a time consuming sequential search
* Immutable strings have the same performance concern as C#; rather than appending in a loop, build a list and joining as a final step
* US users cannot legally use your code if no license is provided
* Do not change the symbolic link to the Python executable; you will create a mismatch between the exe and the libs
* Virtual environments contain hardcoded paths in executables, cannot move them once created
* Test `tearDown` does not run if the test failed
* Python 2 classes don't always inherit from `Object`
* `@classmethod` is decorative and does not restrict access; We Are All Responsible Users

# Concepts

* `*` operator - creates N references to the same value (reference semantics)
* `@classmethod` - class method decorator; causes the first argument to be a reference to the class rather than self
* `@property` - class method decorator; works in conjuction with `__get__()`, `__set__()`, and `__delete__()`
* `__` - used to ignore a result; `_` is used as an alias for `gettext.gettext()`, also value of the last op on the cli
* `__init__.py` - if this exists in a directory, it is considered a Python package; top level is the root package; common practice to have an empty `__init__.py` for a root package when the subpackages do not share code
* `__slots__` - class optimization; avoids allocating a dictionary for each object; useful when very small objects are allocated many times; Tablib has a good example of using this with serialization
* `in` operator - prefer `in` to dictionary `has_key` method
* `pickle.dump()` - used in object serialization, depends on `__dict__` or `__getstate__()`
* `re.VERBOSE` option - allows well-documented regex strings
* `sets` - supports set arithmetic; difference `-`, union `|`, and intersection `&` operators
* `text_type()` - convert strings to unicode, both Py 2 and Py 3 compatible
* Application Binary Interface (ABI) - a CFFI feature that allows calling into code that is in a binary shared library (DLL or so file)
* Arbitrary Keyword Argument Dictionary - aka `**kwargs`, but try to use a more sensible name
* Behaviour-Driven Development (BDD) - introduced by Dan North in 2003
* C Foreign Function Interface (CFFI) - extend Python with C funcs
* Continuous Integration - Martin Fowler describes it best
* Data Model - from the Python docs: namespace tools, dir(), globals(), locals()
* Diagnostic vs Audit Logging - business events should be logged for audit purposes, not just debugging
* doctest - introduced in Python 2.1, typically less detailed than unit tests but provide a nice combination of test and doc
* Executable Zip File - if zip contains `__main__.py` then Python interpreter will run it; can even prepend a she-bang `#!` to make a Unix executable file
* extra-index-url - cli param for pip, can specify an internally hosted package repo; use the dir structure MyPackageName/MyPackageName.tar.gz
* Freezing Code - bundle packages for distribution; difficult when not all dependency licenses allow for bundled redistribution
* Global Interpreter Lock (GIL) - method used by CPython for thread-safety; oft-cited performance bottleneck
* IETF - Internet Engineering Task Force, RFCs 7230 through 7235 define http specs
* Immutable Types - data cannot change; strings, numbers, and tuples are immutable
* Keyword Arguments - optional args with default values
* Late Binding Closures - var values are looked up at the time of the inner function call; lambda expressions work the same way as def functions
* Linux Built Distribution - "correct" way to distribute a frozen Python app on Linux; does not include the interpreter, saves \~2MB
* List Comprehension - `[value for __ in range(N)]` creates N copies (value semantics)
* Monkey Patch - change a method at runtime
* Mutable Default Arguments - modifying the value of an argument changes the default value for subsequent calls; default values use reference semantics, handy for implementing a cache
* Mutable Types - data can be modified in-place; cannot be dictionary keys; lists are mutable
* Open Source Initiative (OSF) - provides some popular licenses
* PEP 20 - The Zen of Python by Tim Peters; guiding principles; import this
* PEP 282 - describes logging
* PEP 3103 - switch statement was proposed but proved unpopular
* PEP 3129 - Python 3 allows decorators on classes
* PEP 3132 - Python 3 new method of unpacking vars (* operator)
* PEP 318 - introduced decorators, a better alternative to manually wrapping a method
* PEP 333 - spec for WSGI
* PEP 343 - introduces the with statement as an alternative to try/finally
* PEP 374 - concise comparison of Subversion, Bazaar, Git, Mercurial
* PEP 427 - introduced eggs, zip format with installation metadata
* PEP 8 - code style guidelines; being pep8-ed is having a coder throw the style guideline book at you; a foolish consistency is the hobgoblin of little minds
* Percent-Style Formatting - the old hat string formatting style
* Promise Theory - problem domain in labeled graph theory where autonomous agents publish promises to each other
* PyPA - Python Packaging Authority, maintainers of pip, PyPI
* Python Software Foundation (PSF) - provides their own software license for contributors
* Python Software Foundation License (PSFL) - compatible with GNU license
* Pythonista - veteran python developer
* Ravioli Code - many similar little pieces of logic without good structure; one symptom is that it is hard to remember what types are used for what purpose * because many similarly named, closely related types exist
* RTMF - Read the Manual, Friend!
* Shims Directory - used by pyenv
* site-packages directory - where user installed packages are kept
* Source Code Management (SCM) - frumpy term for revision control
* TLDRLegal - web site that summarizes popular open source licenses
* Tox - Python cli test environment, look for `tox.ini` config in projects
* Underscore Prefix - variables can only be private by convention, using underscore prefix is encouraged
* Vendorized Dependencies - package defines external dependencies, typically in a folder called vendor or packages
* Vogon poetry - do not read out loud
* We Are All Responsible Users - Python philosophy is to leave it up to the developer to write good code
* Web Framework - typically includes solutions for url routing, handling request and response objects, html templating, debugger web service
* Werkzug - WSGI toolkit, can easily write web services
* WSGI - interface for web server plug-ins, written in 2006
* YAGNI - Never is often better than right now

# Techs

* 2PY - Fortran to Python interface generator
* ABC - educational programming lang that
* ActivePython - ActiveState commercial distro, paid license
* Anaconda - stats Python distro
* Ansible - virtual machine management, written in Python; does not require target hosts to run a daemon / service
* Apache - mod_wsgi is often considered the easiest route; performance could be better
* Apache Hive - data warehouse build on top of Hadoop
* argparse - replaces optparse; cli argument parsing
* asyncio - Python lib for async IO
* AUFS - union file system
* Autoenv - lightweight alternative to virtualenv
* bbFreeze - freeze tool
* Boost.Python - adds C++ Boost types to Python
* Buildbot - popular CI tool, runs behind a Twisted web server
* Buildout - provides Python "recipes" which are like modules
* Canopy - scientific and analytic Python distro; Enthought commercial distro
* CFEngine - virtual machine management; light-weight, written in C; distributed network communicates using Promise Theory
* Cheeseshop, The - proper name for PyPI (Python Package Index)
* Chef - virtual machine management; infrastructure as Ruby code; flexible framework; recipies and cookbooks, create with the `knife` command
* chroot - system-level containers
* Conda - Anaconda package manger, similar functionality to pip, virtualenv, and Buildout
* contextlib library - turn functions into context managers, suppress exceptions, redirect streams
* CPython - the reference implementation, compatible with C extension modules
* cx_Freeze - freeze tool
* Cyberduck - tool to sync a dir to S3
* Diamond - publishes system metrics (memory, CPU, disk), open sourced by BrightCove in 2011, can be easily extended with custom collector classes
* dir2pi - tool to create Python packages
* Django - "batteries included" web framework; very popular
* Docker - environment isolation via containers
* Docker Hub - Docker container repo
* easy_install - old package tool, prefer pip
* egg - old Python packages; a zip file with a particular structure
* Electron - cross-platform desktop apps using HTML, CSS, JS
* Eric Python IDE - free, lightweight, good debugger
* Fabric - system admin task automation framework; uses `fabfile.py` and `fab deploy`
* Facter - Puppet tool that pulls host info
* Falcon - light framework for REST services; http://falconframework.org/
* fixture - package for mocking data stores populated with data, eg. SQLAlchemy, Storm
* Flask - micro web framework
* Gherkin - syntax to describe behaviours for BDD
* Graphite - metrics back-end, published to by Diamond, open sourced by Orbitz in 2008
* Gunicorn - Green Unicorn; recommended pure Python WSGI server
* Heroku - recommended PaaS for Python services; https://devcenter.heroku.com/categories/python-support
* implified Wrapper Interface Generator (SWIG) - can generate Python interfaces for a lot of modules
* Intel Distribution for Python - commercial distro, free; includes SciPy stack
* IronPython - .NET implementation of Python, convenient interface to .NET
* JBehave - BDD for Java, Better Software magazine article in 2006, Dan North "Introducing BDD" article
* Jenkins - popular CI tool, Java servlet with web API and admin dashboard
* Jinja2 - recommended html templating; default for Flask
* Jupyter Notebooks - is awesome
* Jython - compiles to JVM bytecode, convenient interface to Java libs
* Komodo - polyglot IDE
* Lettuce, Behave - packages for BDD
* Linux Containers - system-level containers
* Luigi - by Spotify; pipeline process automation with scheduling
* MicroPython - Python 3 optimized for microcontrollers
* Mingw-static-toolchain - can build Numpy with MinGW runtime statically linked
* mock - introduced in Python 3.3, provides the mock decorator
* multiprocessing - Python lib for parallel processing
* nginx - "Engine X"; web server and reverse proxy for HTTP, SMTP, etc.
* NINJA-IDE - free IDE, lightweight
* nose - extends unittest with automatic test discovery
* Numba - NumPy-aware Python compiler for LLVM
* PaaS - platform as a service; abstracts away the infra
* pickle - serialization lib
* pip - better than Setuptools because you can uninstall packages, better error messages
* pip2pi - tool to create Python packages
* pip2tgz - tool to create Python packages
* POSIX - Portable Operating System Interface; a set of IEEE standards
* Psutil - cross-platform tool to query system info; easy to get info from Python, similar to `top`, `ps`, `df`, `netstat`
* Puppet - virtual machine management; written in Ruby; Puppet Forge community repo; rigid framework
* py2app - freeze tool; good for OS X
* py2exe - freeze tool; good for Windows
* pyboard - uses MicroPython as an OS
* PyCharm - IDE with free, paid versions
* PyCUDA - Python GPU lib
* pyenv - use multiple versions of Python side-by-side
* pygame - popular lib and community for game dev; Zlib licensed
* pyInstaller - freeze tool; good for PyGame; use `--windowed` argument
* pylint - will warn if a variable gets assigned more than one type of value
* PyPI - Python Package Index; package repo
* Pypiserver - minimal PyPI server
* PyPy - performant Python written in a Python subset, up to 5 times faster than CPython, back-end (bytecode) supports C, CIL, JVM
* PySDL2 - lightweight gui wrapper; https://pysdl2.readthedocs.io/en/latest/tutorial/index.html
* pySpark - Python lib to interface with Apache Spark
* pytest - alternative to unittest
* python-jenkins - created by OpenStack, interacts with Jenkins; Python projects often use Jenkins with a Tox script
* python.vim - syntax plug-in for vim
* PythonNet - .NET package for integrating with a native Python install; the complement to IronPython, can use both at once
* Qt - UI lib, pronounced "cute"
* reStructured Text - understood by PyPI
* Salt - virtual machine management, written in Python; uses ZeroMQ over TCP to communicate with minion hosts
* Setuptools - provides easy_install for managing packages
* Skulpt - JavaScript implementation of Python
* Sphinx - popular Python doc tool, https://readthedocs.org/
* Sphinx - tool for building docs
* Spyder - free IDE popular with scientific distros
* Stackless - patched CPython with tasklets, optz
* Sublime Text - preferred; by Jon Skinner; written in Python; Anaconda package turns it into a better Python IDE
* subprocess - Python lib defined in PEP 324, can call system commands
* Tcl - Tool Command Language, created by John Ousterhout
* TensorFlow - GPU fast math lib by Google; multidimensional arrays called tensors
* testPyPI - tool to test Python package deployments
* Theano - by University of Montreal; was a popular GPU fast math lib before TensorFlow
* Tk - UI lib, often used with Tcl
* Tornado - web framework; asynchronous (non-blocking, event driven, like Node.js)
* tox - package for test environment configuration; Python tool, cli for virtualenv
* Travis - popular CI tool, distributed server, yaml config
* types - Python lib that adds C-like types
* Ubuntu 15.10 - first release where Python 3 is the installation default
* unittest - test classes derive from TestCase, test methods start with "test", setUp and tearDown methods
* unittest2 - back-ported version of unittest for older versions of Python (2.6 and earlier)
* virtualenv - create isolated Python environments, stores it in the working dir
* virtualenvwrapper - keeps virtual environments together in one dir, provides commands to switch between them
* Warehouse - the new PyPI - https://whoisnicoleharris.com/warehouse/
* wheels - new python binary package format, replaces eggs; PEP 427
* WingIDE - paid IDE with great debugger
* wxpython - wxWidgets for Python
* zipapp - Python 3.5+ tool for creating more flexible executable zip files

# Publications

* Self-Reliance - book by Ralph Waldo Emerson
* Test Driven Development with Python book - Obey the Testing Goat!
* The Cucumber Book - Pragmatic Bookshelf book about BDD
* Understanding the Python GIL - David Beazley
* Writing Idiomatic Python - Jeff Knupp

# Names Dropped

* Andy Gale - Getting Started With Chef
* Armin Ronacher - author of Werkzug
* Benjamin Gleitzman - author of HowDoI
* David Heinemeier Hansson - creator of Ruby on Rails
* Kenneth Retiz - author of Requests, Tablib
* Kent Beck - creator of eXtreme Programming
* Paul Kehrer - seminar on distributing compiled modules
* Philip J. Eby - creator of WSGI
* Raymond Hettinger - Python coding expert; Beyond Pep 8 at PyCon 2015
* Tim Peters - Python core developer, creator of timsort

# Code

Cli

* `pip install --upgrade pip`
* `pip freeze > requirements.txt`
* `pip install -r requirements.txt` # dangerous if a virtualenv is not currently in use
* `python3 -m SimpleHTTPServer 9000` # serves the contents of current dir on port 9000

Python

* `for index, item in enumerate()` # better than using a counter var
* `filename, ext = "path.txt".rsplit(".", 1)`
* `import sys` followed by `type(sys)` # modules are a type
* `sys.path` # tells you where the Python environment will search for modules
* `mod = __import__()`  # replaced by importlib.import_module in Python 3.1, backported to 2.7
* `dir(mod)`, `getattr(mod, name)`, `issubcliass(attr, ClassName)` # Python reflection samples

Creating Packages

```
$ echo '#!/usr/bin/env python' > my_bin
$ cat my_py.zip >> my_bin
$ chmod u+x my_bin
```
```
$ pip freeze | xargs pip install --target = packages
$ touch packages/__init__.py
# requires using "import packages.foo as foo" for all dependencies
```
