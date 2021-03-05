
# About

* [Serious Python: Black-Belt Advice on Deployment, Scalability, Testing, and More](https://nostarch.com/seriouspython)
* by Julien Danjou
* published by No Starch Press, 2019

# Thoughts

Really good intermediate-expert level Python book.

# Take-Aways

* If you want to go fast, go alone; if you want to go far, go together
* Python is simple to grasp, hard to master
* Each minor version of Python gets bug-fix support for 18 months and security support for 5 years
* Tests should be put in a submodule (dir), easy to package separately

# Concepts

* `__init__.py` - its presence makes a dir into a module; typically not much in it; prefer `small_module.py` over `small_module/__init__.py` where appropriate
* `bin` dir - if needed, in project, includes any binary tools to be installed by `setup.py`
* `docs` dir - should be included in the project, in reStructuredText format, consumed by Sphinx
* Errare Humanum Est - to err is human
* PEP 440 - introduces Python package version format; similar to Semantic Versioning but some differences; avoid using commit hashes or dates as versions
* PEP 7 - coding standard for C modules written for Python
* PEP 8 - discusses preferred code formatting; `pep8` tool exists

# Tech

* flake8 - combines Pyflakes and pep8
* OpenStack - over 9 million lines of Python
* Pyflakes - lint type tool
* Pylint - line type tool, also checks for PEP 8 conformance
* Python 2.7 - last version of the 2.x branch, will be supported until 2020

# Names Dropped

* Joshua Harlow - author of Taskflow, automation, Zake

# Publications

* The Hacker's Guide to Python - the first version of this book

# Code
