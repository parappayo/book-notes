
# About

* [The Scheme Programming Language](https://www.scheme.com/tspl3/)
* by R. Kent Dybvig
* published by MIT Press, 1987

# Take-Aways

* Some Scheme implementations allow brackets to be used instead of parentheses, can mix between them for emphasis

# Syntax

* `!` - conventional suffix for procedures that have side effects
* `#()` - vector
* `#\` - char prefix
* `#f` - false; all other values are true, including `()` and `nil`
* `#t` - true
* `->` - prefer naming conversion functions like `foo->bar` instead of `convert-foo-to-bar`
* `;` - comment, until end of line
* `?` - prefer naming procedures like `valid?` instead of `is-valid`

# Concepts

* Block-Structured - nested blocks of code define lexical scope
* Continuation - a program's execution context from a given point, as an object; backtracking, multithreading, and coroutines are supported
* Garbage Collector - frees objects that are no longer referenced
* Lexical Context - a procedure carries its surrounding scope (environment)
* Lexically Scoped - variables and keywords enter and leave scope
* R6RS - Revised Report on Scheme version 6
* Shadowed Binding - when a local variable hides a variable in the surrounding scope
* Syntactic Extensions - allow new language constructs to be defined (macros?), commonly used alongside procedure definitions
* Syntax-Case Semantic Abstraction System
* Tail Call - Scheme mandates the optimization that the local state for the calling procedure is discarded

# Tech

* Algol 60 - the source of Scheme's lexical scoping and block structure
* ANSI / IEEE Standard - less up to date than the Revised Report (R5RS)
* Chez Scheme - Dybig's implementation of R6RS [on GitHub](https://github.com/cisco/chezscheme)
* Common Lisp - developed alongside Scheme (influencing each-other's development), also has lexical scoping and first-class procedures; evaluation rules for procedures is different from other objects; separate namespace for procedure variables
* Lisp - provides values as first-class objects, data as symbols and lists
* Petite Chez Scheme
* R5RS - Revised Report on the Algorithmic Language Scheme, version 5
* Revised Report on the Algorithmic Language Scheme - defines standard Scheme
* Scheme - Lisp dialect introduced in 1975, Sussman & Steele; added lexical scoping (from Algol), procedures as first-class objects, continuations
* Scheme Widget Library (SWL)

# Names Dropped

* Jean-Pierre Hebert - monohedral tilings; prototile

# Publications

* The Little Schemer - book
