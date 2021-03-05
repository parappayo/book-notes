# About

* [Realm of Racket: Learn to Program, One Game at a Time!](https://www.realmofracket.com/)
* by Matthias Felleisen, Conrad Barski, David Van Horn
* published by No Starch, 2013

# Thoughts

Honkin great. Stuff like this is why I program.

# Take-Aways

* Lisp parens avoid the need for an evaluation order; the parse tree is explicit
* Early programming languages were non-portable, thin veils over the hardware; compilers and interpreters came about in the 1950s

# Concepts

* `#:transparent` - struct option that enables pretty-printing
* `#` - expression comment, ignores the next full expression; useful to stub out code
* `#|` - starts a block comment, end with `|#`
* `'` operator - turns code into data; `'(foo)` is shorthand for `(list foo)`
* `(struct point (x y) #:transparent)` automatically defines functions including `point`, `point-x`, `point-y`, and `point?`
* `(symbol=? 'foo 'FoO)` ; test case sensitivity of symbols
* `;` - starts a line comment; conventional to use `;;` if the comment is the entire line
* `cond` - conditional special form similar to a case statement, evaluates conditions from top to bottom, use `else` to add a default case; conventional to layer bracket types for visual style
* `empty` - alias for `` `() ``
* `eq?` - conditional that checks for reference equality; verus `equal?` value equality (recurses for composite types like structs)
* `member` - returns tail of list from the point at which the given member was found
* `rackunit` - unit testing module; includes `check-equal?`, `check-pred`, `check-true`
* `rkt` - conventional file extension for Racket programs
* `set!` - assign value to variable
* `unless` - conditional special form, inverse of `when`
* `when` - conditional special form without an else branch; eg. `(when (and doc-modified (prompt-save-overwrite)) (save-doc))`
* Algol Family - C, Pascal, Java
* Brackets - Racket allows freely mixing between parentheses, brackets, and braces; opening and closing pairs must match; conventional to use parens for functions, brackets for conditionals
* Conditional - `(if (= x y) 'yup 'nope)`, every value is truthy except `#f`, note that only the branch taken is evaluated (short-circuit evaluation) which is a special form behaviour since an actual function would eval all arguments
* Cons Cell - lists are comprised of these; tuple of a value and a reference, like a linked list; `car` extracts the left value, `cdr` extracts the right value (the rest of the list), can also use `first` and `rest`
* Dotted Pair - visual representation of a cons cell
* Equality Predicate - tells whether values are equal, can be specific to type, eg. `string=?`
* Field Selectors - aka selectors; struct accessors
* functions such as `member` take advantage of the general truthyness of values to return more than a mere `#t`
* Infix Notation - when the operator goes between the parameters; traditional but unwieldy, invites order of evaluation problems
* Keywords - reserved words in Racket; eg. `define` is not a function
* Lisp Family - Common Lisp, Scheme, Racket
* List-Eater - tail recursive function that checks items at the front of a list and recurses on the rest
* Loops - abbreviations for recursive functions
* Numerical Types - Racket supports integer, float, rational, and complex; include a decimal point to coerce values to float
* Object-Oriented - appeared by 1972 with Smalltalk and Simula
* Predicate - function that returns `#t` or `#f`; eg. `zero?` and `symbol=?`, pronounce the `?` as "eh"
* Program Development Environment (PDE) - funny name for an IDE
* Quotient - integer, numerator part of the result of a division
* Racketeers - the creators of Racket; the Racket community
* Raw Cons Cell - created with `cons`
* Semantics - expressive meaning
* Structure - define with `struct`, has named fields, automatically defines accessor functions
* Symbol - the type of a stand-alone word that starts with `` ` ``; are case-sensitive but Racketeers use case sparingly
* Syntax - grammar form
* Type Predicate - tells you whether value is of a given type; structs have this defined automagically
* Universal Equality Predicate - `equal?`, compares anything regardless of type

# Techs

* Algol 60 - inspired by Fortran, European
* DrRacket - Racket IDE
* ENIAC - early computer
* Fortran - early scientific lang, American
* Racket - friendly dialect of dialect of Scheme from Rice U (Houston); values empathy for the novice
* Scheme - invented by Guy Steele, Gerry Sussman at MIT; Lisp dialect with assignment and control flow jumps; prototyped in Lisp
* Scheme84 - made by Dan Friedman, Mitch Ward at Indiana U
* T - dialect of Scheme from Yale
* Zuse Z3 - early computer

# Publications

* Land of Lisp - Conrad Barski book

# Names Dropped

* Alonso Church - invented Lambda Calculus
* John McCarthy - invented Lisp at MIT in the late 1950s, used Church's papers; invented conditionals in the 1960s?
