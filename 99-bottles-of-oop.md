
# About

* [99 Bottles of OOP: A Practical Guide to Object-Oriented Design](https://www.sandimetz.com/99bottles/)
* by Sandi Metz, Katrina Owen
* self-published, 2018

# Thoughts

99 Bottles of OOP is an excellent book. It is deeply insightful about code craft while being clear and illustrative. Every programmer should study it.

# Take-Aways

* Abstraction (OOP, DRY, DI) is a complexity trade-off: more mental load for more resilience to change
* Using the wrong abstraction is harder to recover from than duplicated code
* Abstractions should be useable in future contexts, not just the ones they were extracted from
* Code should expose the problem domain and name important concepts
* Consider how soon the future will arrive and whether it comes with new info
* Clever shortcuts are a false economy; code should tell the truth
* Skipping TDD steps may lead to missed insights about the problem domain
* TDD is not free, claims only that benfits outweigh costs
* Tests should assert what is accomplished, not how
* Refactoring breaks test - either the change is not refactoring (modified behaviour) or the test is wrong (validates how instead of what)
* Each code smell has a curative refactoring
* When stuck naming, try tabulating possible values and think of a sensible column header name
* Static analysis tools only go so far; can't tell you if your names are meaningful
* Liskov Substitution Principle also applies to Duck Typed objects
* OOD is violated when a dependency is injected that does not supply its own behaviour
* OOD conditionals should select the object with the right behaviour, not select the right behaviour for a given object; use Factory methods
* If immutable objects (FP) were free, we'd always choose to use them because they're so much easier to reason about (threading, caching)
* Two costs to FP: fixed learning cost (devs), runtime alloc cost
* Case / switch implies that the conditional remains the same, Else-if does not
* "Only two hard problems in CS" quote attributed to Phil Karlton
* "make the change easy, then make the easy change" - Kent Beck

# Concepts

* 99BOOP - 99 Bottles of OOP
* Assignments, Branches, Conditions (ABC) - code metric
* Concretely Abstract - damage done by extreme DRY
* Cyclomatic Complexity - execution path count code metric
* Data Clump - code smell, typically cured with Extract Class
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
* POOD - Practical Object-Oriented Design
* Primitive Obsession - code smell, cured by Extract Class
* Shameless Green - quick greens forgive all sins
* SOLID - Single Responsibility, Open-Closed, Liskov Substitution, Interface Segretgation, Dependency Inversion
* Source Lines of Code (SLOC) - code metric
* Speculatively General - paying the abstraction cost too soon
* Squint Test - superficial evaluation of code similarity
* Switch Statement - code smell, cure with Replace Conditional with State / Polymorphism
* Transformation Priority Premise (Bob Martin)

# Techs

* Exercism (coding exercises founded by Katrina Owen)
* Flog (Ruby ABC-ish code metrics by Ryan Davis)
* Minitest (Ruby test)

# Books

* Implementation Patterns (Kent Beck)
* Practical Object Oriented Design in Ruby (Sandi Metz)
* Refactoring: Ruby Edition (Jay Fields, Martin Fowler, Shane Harvie)
* Test-Driven Development by Example (Kent Beck)

# Talks

* Flocking Behaviour TED Talk - The Science of Sync - Steven Strogatz

# See Also

* [Get a Whiff of This](https://www.youtube.com/watch?v=PJjHfa5yxlU) (Sandi Metz talk, RailsConf 2016)
* [All the Little Things](https://www.youtube.com/watch?v=8bZh5LMaSmE) (Sandi Metz talk, RailsConf 2014)
