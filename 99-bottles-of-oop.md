
# About

[99 Bottles of OOP](https://www.sandimetz.com/99bottles/)
by Sandi Metz, Katrina Owen
self-published, 2018

# Thoughts

99 Bottles of OOP is an excellent book. It is deeply insightful about code craft while being clear and illustrative. Every programmer should study it.

# Take-Aways

* Abstraction (OOP, DRY, DI) is a complexity trade-off: more mental load for more resilience to change
* Using the wrong abstraction is harder to recover from than duplicated code
* Code should expose the problem domain and name important concepts
* Consider how soon the future will arrive and whether it comes with new info
* Skipping TDD steps may lead to missed insights about the problem domain
* TDD is not free, claims only that benfits outweigh costs
* Tests should assert what is accomplished, not how
* Refactoring breaks test - either the change is not refactoring (modified behaviour) or the test is wrong (validates how instead of what)
* When stuck naming, try tabulating possible values and think of a sensible column header name
* Static analysis tools only go so far; can't tell you if your names are meaningful
* Liskov Substitution Principle also applies to Duck Typed objects
* OOD is violated when a dependency is injected that does not supply its own behaviour
* Under OOD conditionals should select for the object with the right behaviour, not select the right behaviour for a given object
* If immutable objects (FP) were free, we'd always choose to use them
* Two costs to FP: fixed learning cost (devs), runtime alloc cost
* Case / switch implies that the conditional remains the same, Else-if does not
* "Only two hard problems in CS" quote attributed to Phil Karlton

# Concepts

* Assignments, Branches, Conditions (ABC) - code metric
* Concretely Abstract - damage done by extreme DRY
* Cyclomatic Complexity - execution path count code metric
* Dependency Injection (DI)
* Dependency Inversion - depend on abstractions rather than concretions
* Don't Repeat Yourself (DRY)
* Flocking Rules - select things most alike, find smallest difference between, make the smallest change that removes the difference
* Functional Programming (FP)
* Green Bar Patterns (Kent Beck) - Fake It, Obvious Implementation, Triangulate
* Incomprehenisibly Concise - cryptic code golf
* Interface Segregation - depend only on what you use
* Liskov Subtitution - subclass objects can stand-in for base class
* Object-Oriented Design (OOD)
* Open Principle - first refactor, then add features, not both at once
* Open-Closed Principle - open for extension, closed for modification
* Primitive Obsession - code smell, cured by Extract Class
* Shameless Green - quick greens forgive all sins
* SOLID - Single Responsibility, Open-Closed, Liskov Substitution, Interface Segretgation, Dependency Inversion
* Source Lines of Code (SLOC) - code metric
* Speculatively General - paying the abstraction cost too soon
* Squint Test - superficial evaluation of code similarity
* Transformation Priority Premise (Bob Martin)

# Techs

* Flog (Ruby ABC-ish code metrics by Ryan Davis)
* Minitest (Ruby test)

# Books

* Implementation Patterns (Kent Beck)
* Refactoring: Ruby Edition (Jay Fields, Martin Fowler, Shane Harvie)
* Test-Driven Development by Example (Kent Beck)

# Talks

* Flocking Behaviour TED Talk - The Science of Sync - Steven Strogatz

# See Also

* [Get a Whiff of This](https://www.youtube.com/watch?v=PJjHfa5yxlU) (Sandi Metz talk)
* Each code smell has a curative refactoring
