
# About

* [The Hitchhiker's Guide to Python: Best Practices for Development](https://docs.python-guide.org/)
* by Kenneth Reitz and Tanya Schlusser
* published by O'Reilly, 2016

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
* Active Record ORM - objects represent record data and also abstract operations on the underlying db
* Advanced Message Queuing Protocol (AMQP) - comm protocol, used by RabbitMQ
* Application Binary Interface (ABI) - a CFFI feature that allows calling into code that is in a binary shared library (DLL or so file)
* Arbitrary Keyword Argument Dictionary - aka `**kwargs`, but try to use a more sensible name
* Behaviour-Driven Development (BDD) - introduced by Dan North in 2003
* Benevolent Dictator for Life (BDFL) - Guido van Rossum
* Bigram - pair of consecutive words
* C Fast Function Interface - probably a mistaken reference to CFFI
* C Foreign Function Interface (CFFI) - extend Python with C funcs, often used for optz
* Continuous Integration - Martin Fowler describes it best
* coroutines - `async def` syntax, part of async io
* CSSSelect - W3C standard to specify a path through an html document
* Data Mapper ORM - has separate interfaces to present db records and to operate on the underlying data; a mapper function converts between data objects and db records
* Data Model - from the Python docs: namespace tools, dir(), globals(), locals()
* Database Abstraction Layer (DAL) - makes implementing db drivers easier
* Diagnostic vs Audit Logging - business events should be logged for audit purposes, not just debugging
* Django Girls - charity organization, provides training
* doctest - introduced in Python 2.1, typically less detailed than unit tests but provide a nice combination of test and doc
* Executable Zip File - if zip contains `__main__.py` then Python interpreter will run it; can even prepend a she-bang `#!` to make a Unix executable file
* External Data Representation (XDR) - Sun serialization format, Python lib is xdrlib; both sender and receiver must know the data format in advance
* extra-index-url - cli param for pip, can specify an internally hosted package repo; use the dir structure MyPackageName/MyPackageName.tar.gz
* Form-Encoding - used for POST data
* Freezing Code - bundle packages for distribution; difficult when not all dependency licenses allow for bundled redistribution
* Global Interpreter Lock (GIL) - method used by CPython for thread-safety; oft-cited performance bottleneck; many networking libs use async methods to work around this
* IETF - Internet Engineering Task Force, RFCs 7230 through 7235 define http specs
* Immutable Types - data cannot change; strings, numbers, and tuples are immutable
* Internet of Connected Products (IoCP)
* JSON - JavaScript Object Notation; Python 2.6 added the json lib but PyPI also provides simplejson
* Keyed-Hashing for Message Authentication (HMAC) - RFC 2104
* Keyword Arguments - optional args with default values
* Late Binding Closures - var values are looked up at the time of the inner function call; lambda expressions work the same way as def functions
* Linux Built Distribution - "correct" way to distribute a frozen Python app on Linux; does not include the interpreter, saves \~2MB
* List Comprehension - `[value for __ in range(N)]` creates N copies (value semantics)
* Mersenne Twister - pseudorandom number generator used by random lib
* Metaclass - defines how a class behaves; https://stackoverflow.com/questions/100003/what-are-metaclasses-in-python/6581949
* Monkey Patch - change a method at runtime
* Mutable Default Arguments - modifying the value of an argument changes the default value for subsequent calls; default values use reference semantics, handy for implementing a cache
* Mutable Types - data can be modified in-place; cannot be dictionary keys; lists are mutable
* NoSQL - prefer to call it "not only SQL"
* Object-Relational Mapper (ORM) - provides data types backed by a db schema
* Open Source Initiative (OSF) - provides some popular licenses
* Password Based Key Derivation Function 2 (PBKDF2) - recommended in NIST Special Publication 800-132
* Percent-Style Formatting - the old hat string formatting style
* Promise Theory - problem domain in labeled graph theory where autonomous agents publish promises to each other
* Punkt Tokenizer - divides text into sentences, created by Tibor Kiss and Jan Strunk
* PyPA - Python Packaging Authority, maintainers of pip, PyPI
* Python Cryptographic Authority (PyCA) - maintains many crypto libs, founded in 2013
* Python Software Foundation (PSF) - provides their own software license for contributors
* Python Software Foundation License (PSFL) - compatible with GNU license
* Pythonista - veteran python developer
* Ravioli Code - many similar little pieces of logic without good structure; one symptom is that it is hard to remember what types are used for what purpose * because many similarly named, closely related types exist
* RESTful API - employs Representational State Transfer and HTTP verbs (Get, Put, Post, Delete, etc.), influenced HTTP 1.1 but is not a standard
* RTMF - Read the Manual, Friend!
* Secure Hash Algorithm 256 (SHA-256) - should do multiple iterations on this when hashing passwords
* Shims Directory - used by pyenv
* site-packages directory - where user installed packages are kept
* Socket - the combo of an IP address with a port, a transport protocol, and an i/o channel (file-like object); see https://docs.python.org/3/howto/sockets.html
* Source Code Management (SCM) - frumpy term for revision control
* Structured Query Language (SQL) - an ISO standard, but heavily vendor specific in practice
* TCP/IP - divided into layers: link (hardware, OS), internet (IPv4, IPv6), transport (TCP, UDP), application (HTTP, SMTP, FTP)
* TLDRLegal - web site that summarizes popular open source licenses
* Tox - Python cli test environment, look for `tox.ini` config in projects
* Underscore Prefix - variables can only be private by convention, using underscore prefix is encouraged
* Vendorized Dependencies - package defines external dependencies, typically in a folder called vendor or packages
* Vogon poetry - do not read out loud
* We Are All Responsible Users - Python philosophy is to leave it up to the developer to write good code
* Web Framework - typically includes solutions for url routing, handling request and response objects, html templating, debugger web service
* Werkzug - WSGI toolkit, can easily write web services
* World Wide Web Consortium (W3C) - standards body
* WSGI - interface for web server plug-ins, written in 2006
* XML - there is a standard xml lib, but to convert to and from dict you need a package such as untangle or xmltodict
* XPath - W3C standard to specify a path through an html document
* YAGNI - Never is often better than right now

# Techs

* 2PY - Fortran to Python interface generator
* `json.dumps` - serialize dict as json
* `json.loads` - parse json string into a dict
* `str.casefold` - helps to lowercase languages with special behaviour chars
* ABC - educational programming lang that
* ActivePython - ActiveState commercial distro, paid license
* Anaconda - Python distro for scientific computing; many libs (Numpy, SciPy, etc.) depend on C libs and building these for Windows can be a pain, this distro helps
* Ansible - virtual machine management, written in Python; does not require target hosts to run a daemon / service
* Apache - mod_wsgi is often considered the easiest route; performance could be better
* Apache Hive - data warehouse build on top of Hadoop
* argparse - replaces optparse; cli argument parsing
* asyncio - async sockets and queues lib, provisionally part of the standard library
* AUFS - union file system
* Autoenv - lightweight alternative to virtualenv
* Automatically Tuned Linear Algebra Format (ATLAS) - Numpy's C back-end, linear algebra lib, routines from Basic Linear Algebra Subset (BLAS) and Linear Algebra Package (LAPACK)
* Avro - Apache serialization lib
* bbFreeze - freeze tool
* bcrypt - crypto lib, uses Blowfish algorithm
* Bokeh - web-capable plotting lib
* Boost.Python - adds C++ Boost types to Python
* Buildbot - popular CI tool, runs behind a Twisted web server
* Buildout - provides Python "recipes" which are like modules
* Canopy - scientific and analytic Python distro; Enthought commercial distro
* Cassandra - distributed table store, tolerates wide tables, no joins but use redundant views instead
* Celery - AMQP lib, can store task states via SQLAlchemy or Memcached, web admin via Flower
* CFEngine - virtual machine management; light-weight, written in C; distributed network communicates using Promise Theory
* Cheeseshop, The - proper name for PyPI (Python Package Index)
* Chef - virtual machine management; infrastructure as Ruby code; flexible framework; recipies and cookbooks, create with the `knife` command
* chroot - system-level containers
* Conda - Anaconda package manger, similar functionality to pip, virtualenv, and Buildout
* configparser - Windows ini file parser lib
* contextlib library - turn functions into context managers, suppress exceptions, redirect streams
* Couchbase - distributed doc store with an SQL-like API
* CPython - the reference implementation, compatible with C extension modules
* cryptography - lib for OpenSSL primitives, lower level than pyOpenSSL; divided into recipes and hazmat (low-level primitives)
* cv2 - computer vision lib, bindings for OpenCV
* cx_Freeze - freeze tool
* Cyberduck - tool to sync a dir to S3
* dbm - GNU db, stores key-value pairs in an on-disk hash table
* Diamond - publishes system metrics (memory, CPU, disk), open sourced by BrightCove in 2011, can be easily extended with custom collector classes
* difflib - standard lib for comparing text
* dir2pi - tool to create Python packages
* Django - "batteries included" web framework; very popular
* Django ORM - tightly coupled to Django, similar in feel to Ruby on Rails ActiveRecord
* Docker - environment isolation via containers
* Docker Hub - Docker container repo
* Druid - distributed column store intended for event data
* easy_install - old package tool, prefer pip
* egg - old Python packages; a zip file with a particular structure
* Electron - cross-platform desktop apps using HTML, CSS, JS
* Eric Python IDE - free, lightweight, good debugger
* Fabric - system admin task automation framework; uses `fabfile.py` and `fab deploy`
* Facter - Puppet tool that pulls host info
* Falcon - light framework for REST services; http://falconframework.org/
* fixture - package for mocking data stores populated with data, eg. SQLAlchemy, Storm
* Flask - micro web framework
* gevent - lightweight async io lib, WSGI, coupled to C libev, see gevent.monkey; uses coroutines to provide greenlets
* Gherkin - syntax to describe behaviours for BDD
* Graphite - metrics back-end, published to by Diamond, open sourced by Orbitz in 2008
* greenlet - lib that provides green threads (user space, not kernel space)
* Gunicorn - Green Unicorn; recommended pure Python WSGI server
* gzip - compression lib, see also zlib, bzip2, lzma
* HBase - distributed column store, built on Hadoop Distributed File System, good for sparse arrays
* Heroku - recommended PaaS for Python services; https://devcenter.heroku.com/categories/python-support
* implified Wrapper Interface Generator (SWIG) - can generate Python interfaces for a lot of modules
* Intel Distribution for Python - commercial distro, free; includes SciPy stack
* IPython - enhanced Python interpreter with history, debugging, inline images; default kernel for Jupyter Notebooks, default interpreter for Spyder, included in Anaconda
* IronPython - .NET implementation of Python, convenient interface to .NET
* JBehave - BDD for Java, Better Software magazine article in 2006, Dan North "Introducing BDD" article
* Jenkins - popular CI tool, Java servlet with web API and admin dashboard
* Jinja2 - recommended html templating; default for Flask
* Jupyter Notebooks - is awesome
* Jython - compiles to JVM bytecode, convenient interface to Java libs
* Komodo - polyglot IDE
* Lettuce, Behave - packages for BDD
* libnacl - libsodium interface for Salt Stack
* libsodium - forked from nacl, fewer options (not the full TLS protocol) helps users make better choices
* Lightning Memory-Mapped Database (LMDB) - key-value store with memory-mapped file access
* Linux Containers - system-level containers
* Luigi - by Spotify; pipeline process automation with scheduling
* lxml - package for parsing xml or html, provides `html.fromstring`
* Matplotlib - scientific plotting (charts) lib, API mimics MATLAB; https://matplotlib.org/gallery.html
* MemoryBIO - part of ssl lib
* MicroPython - Python 3 optimized for microcontrollers
* Mingw-static-toolchain - can build Numpy with MinGW runtime statically linked
* mock - introduced in Python 3.3, provides the mock decorator
* MongoDB - distributed doc store, like a dict on a cluster
* multiprocessing - Python lib for parallel processing
* MySQL-python - lib for connecting to MySQL
* nacl (salt) - Networking and Cryptography library
* Neo4j - graph database
* nginx - "Engine X"; web server and reverse proxy for HTTP, SMTP, etc.
* NINJA-IDE - free IDE, lightweight
* nltk - Natural Language Toolkit lib by Steven Bird and Edward Loper (UPenn 2001), popular choice for text mining
* nose - extends unittest with automatic test discovery
* Numba - NumPy-aware Python compiler for LLVM
* numbers - standard lib that provides Integral, Rational, Real, Complex types
* Numpy - math, linear algebra lib; ATLAS lib back-end
* PaaS - platform as a service; abstracts away the infra
* Pandas - series and data frame lib, name derived from Panel Datak based on Numpy
* peewee - Active Record ORM lib, aims to be lightweight
* pickle - serialization lib; not secure against malicious input, always sanitize user input
* pika - AMQP lib for connecting to RabbitMQ
* Pillow - image file format and processing lib, forked from PIL and imported as "PIL"
* pip - better than Setuptools because you can uninstall packages, better error messages
* pip2pi - tool to create Python packages
* pip2tgz - tool to create Python packages
* Plotly - plotting lib based on D3.js
* PonyORM - Active Record ORM lib with a Python generator syntax (instead of a query grammar) and GUI entity-relationship editor; requires relations to be bi-directional, queries look like Python code
* POSIX - Portable Operating System Interface; a set of IEEE standards
* Protobuf - Google serialization lib
* Psutil - cross-platform tool to query system info; easy to get info from Python, similar to `top`, `ps`, `df`, `netstat`
* psycopg2 - lib for connecting to Postgres
* Puppet - virtual machine management; written in Ruby; Puppet Forge community repo; rigid framework
* py2app - freeze tool; good for OS X
* py2exe - freeze tool; good for Windows
* pyboard - uses MicroPython as an OS
* PyCharm - IDE with free, paid versions
* pyCrypto - older lib, not maintained by PyCA
* PyCUDA - Python GPU lib
* pyenv - use multiple versions of Python side-by-side
* pygame - popular lib and community for game dev; Zlib licensed
* pyInstaller - freeze tool; good for PyGame; use `--windowed` argument
* pylint - will warn if a variable gets assigned more than one type of value
* PyNaCl - "py-salt," bindings for libsodium; use this if you don't want to deal with pyOpenSSL
* pyOpenSSL - crypto lib, updates more frequently than Python itself
* PyPI - Python Package Index; package repo
* Pypiserver - minimal PyPI server
* PyPy - performant Python written in a Python subset, up to 5 times faster than CPython, back-end (bytecode) supports C, CIL, JVM
* PySDL2 - lightweight gui wrapper; https://pysdl2.readthedocs.io/en/latest/tutorial/index.html
* pySpark - Python lib to interface with Apache Spark
* pytest - alternative to unittest
* Python Database API (DB-API2) - PEP 249, automatically picks an appropriate db driver
* Python Imaging Library (PIL) - never ported to Python3, consider Pillow
* python-jenkins - created by OpenStack, interacts with Jenkins; Python projects often use Jenkins with a Tox script
* python.vim - syntax plug-in for vim
* PythonNet - .NET package for integrating with a native Python install; the complement to IronPython, can use both at once
* PyYAML - yaml lib
* PyZMQ - ZeroMQ lib, socket style message queues, lower level than RabbitMQ
* Qt - UI lib, pronounced "cute"
* RabbitMQ - message broker service
* Records - minimalist query lib, built on Tablib and SQLAlchemy
* Redis - distributed in-memory key-value store, redis-py lib
* requests - pip package; handles Keep-Alive, Sessions, connection pooling automatically
* reStructured Text - understood by PyPI
* Rpy2 - R wrapper lib
* SageMath - math lib with fields, rings, algebras
* Salt - virtual machine management, written in Python; uses ZeroMQ over TCP to communicate with minion hosts
* ScikitImage - image processing lib, edge detection
* ScikitLearn - machine learning lib
* SciPy - math, eng lib
* Scipy Lecture Notes - http://scipy-lectures.org/
* Sealib - plotting lib for statistics and data visualization
* Setuptools - provides easy_install for managing packages
* shelve - persistent key-value store lib, uses the best available dbm service (by GNU) on the host
* Skulpt - JavaScript implementation of Python
* socketserver - lib for serving TCP connections
* Sphinx - popular Python doc tool, https://readthedocs.org/
* Spyder - free IDE popular with scientific distros
* SQLAlchemy - ORM that uses a data mapper pattern; Classical Mappings API provides low-level db control; can run on Jython and PyPy
* sqlite3 - lib for connecting to SQLite, low latency
* SQLObject - older Active Record ORM lib, supports some legacy db engines such as Sybase, SAP DB, MSSQL
* Stackless - patched CPython with tasklets, optz
* Sublime Text - preferred; by Jon Skinner; written in Python; Anaconda package turns it into a better Python IDE
* subprocess - Python lib defined in PEP 324, can call system commands
* SymPy - math lib, series expansion, limits, calculus; written entirely in Python
* SyntaxNet - Google ML project built on TensorFlow, parser called Parsey McParseface
* Tcl - Tool Command Language, created by John Ousterhout
* TensorFlow - GPU fast math lib by Google; multidimensional arrays called tensors
* testPyPI - tool to test Python package deployments
* Theano - by University of Montreal; was a popular GPU fast math lib before TensorFlow
* Tk - UI lib, often used with Tcl
* Tornado - web framework; asynchronous (non-blocking, event driven, like Node.js)
* tox - package for test environment configuration; Python tool, cli for virtualenv
* Travis - popular CI tool, distributed server, yaml config
* TweetNaCl - crypto lib that fits in 100 tweets
* Twisted - event-driven networking lib, started in 2002, implements http, smtp, pop3, imap, ssh, Memcached, IoCP, integrates with wxPython and GTK
* types - Python lib that adds C-like types
* Ubuntu 15.10 - first release where Python 3 is the installation default
* unittest - test classes derive from TestCase, test methods start with "test", setUp and tearDown methods
* unittest2 - back-ported version of unittest for older versions of Python (2.6 and earlier)
* urllib.requests - low level http requests; docs recommend using requests package instead
* virtualenv - create isolated Python environments, stores it in the working dir
* virtualenvwrapper - keeps virtual environments together in one dir, provides commands to switch between them
* Warehouse - the new PyPI - https://whoisnicoleharris.com/warehouse/
* wheels - new python binary package format, replaces eggs; PEP 427
* WingIDE - paid IDE with great debugger
* wxpython - wxWidgets for Python
* ZeroMQ (0MQ, ZMQ) - message lib with socket style API; does not require a separate message broker, connections are just client-server; socket types specify how each socket behaves, eg. `zmq.REP` is for request-response server, see also `REQ` (client), `PUB`, `SUB`, `PUSH`, `PULL`, `PAIR`
* zipapp - Python 3.5+ tool for creating more flexible executable zip files

# Publications

* A Guide to Python's Magic Methods - blog post series by Rafe Kettler
* A Relational Model of Data for Large Share Data Banks - paper written in 1970 by Edgar Codd at IBM, introduced relational databases, popularized starting in 1977 when Larry Ellison founded Oracle, displaced other data persistence models for decades
* A Tale of Concurrency Through Creativity in Python - Kavya Joshi seminar
* Expert Python Programming - best practices book
* Fullstack Python - guide to web dev
* Getting Started with Chef - book by Andy Gale
* Natural Language Processing with Python - O'Reilly book
* Patterns of Enterprise Application Architecture - Martin Fowler book
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
* PEP 476 - important ssl improvements back-ported to Python 2.7.9
* PEP 506 - secrets lib
* PEP 8 - code style guidelines; being "pep8-ed" is having the style guidelines thrown at you; "a foolish consistency is the hobgoblin of little minds"
* Pro Python - intermediate-advanced book
* Python Module of the Week - fun examples
* Self-Reliance - book by Ralph Waldo Emerson
* Talk About the State of Crypto in Python - Jarret Raim, Paul Kehrer
* Test Driven Development with Python book - Obey the Testing Goat!
* The Cucumber Book - Pragmatic Bookshelf book about BDD
* The State of Crypto in Python - Jake Edge blog post
* The State of SSL in Python - Benjamin Peterson talk
* Twisted - book by Jessica McKellar, Abe Fettig
* Understanding the Python GIL - David Beazley
* W3Schools - web dev tutorials site
* Writing Idiomatic Python - Jeff Knupp

# Names Dropped

* Armin Ronacher - author of Werkzug
* Benjamin Gleitzman - author of HowDoI
* David Heinemeier Hansson - creator of Ruby on Rails
* Kenneth Retiz - author of Requests, Tablib
* Kent Beck - creator of eXtreme Programming
* Paul Kehrer - seminar on distributing compiled modules
* Philip J. Eby - creator of WSGI
* Raymond Hettinger - Python coding expert; Beyond Pep 8 at PyCon 2015
* Tim Peters - Python core developer, creator of timsort
* Eli Bendersky - a Python core dev, wrote about memory buffers, see buffer protocol docs and PEP 3118

# Code

Cli

* `pip install --upgrade pip`
* `pip freeze > requirements.txt`
* `pip install -r requirements.txt` # dangerous if a virtualenv is not currently in use
* `python3 -m SimpleHTTPServer 9000` # serves the contents of current dir on port 9000
* `pydoc` # cli for looking at Python docs; `pydoc time` cli is equivalent to `help(time)` repl

Python

* `for index, item in enumerate()` # better than using a counter var
* `filename, ext = "path.txt".rsplit(".", 1)`
* `import sys` followed by `type(sys)` # modules are a type
* `sys.path` # tells you where the Python environment will search for modules
* `mod = __import__()`  # replaced by importlib.import_module in Python 3.1, backported to 2.7
* `dir(mod)`, `getattr(mod, name)`, `issubcliass(attr, ClassName)` # Python reflection samples
* `dmb.whichdb('my_shelf')` - tell what dbm back-end is being used by shelve

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
