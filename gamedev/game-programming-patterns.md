
# About

* [Game Programming Patterns](https://gameprogrammingpatterns.com/)
* by Robert Nystrom
* published Genever Benning, 2011

# Thoughts

Good criticism of game dev lack of practices. Maybe a shortcut to reading Gang of Four's book.

# Take-Aways

* "There is no right answer, just different flavours of wrong."
* "It's a big hammer so swing it carefully."
* "my hunch is that most people just like well-defined "kinds of things""
* you don't need a "BulletManager" class, just move all of its methods onto "Bullet"
* OOP was popular in the same decade that Ace of Base, may indicate a lapse in judgement
* a good solution is a distillation of code, rather than an accretion of it
* three-way tradeoff between performance, maintainability, and developer speed
* modern games spend way more bytes on data then code
* code architecture is about enabling change; paging into a simian cerebrum over optic nerve is slow; decouple code to reduce the amount of context needed to make sensible changes
* over-engineered architecture makes it hard to find code that does real work
* optimization thrives on limitations; tension with game design
* speculative abstraction is risky; the wrong abstraction is worse than code duplication
* engineering challenges common to games projects: time sequencing, compressed dev cycles, emergent behaviour, performance
* game dev books are typically either domain-specific (rendering, AI, physics, etc.) or whole-engine (discuss each component that goes into a particular type of game)
* if you have many potential flyweight objects and are unsure on init which ones will actually be used, consider having a lazy flyweight factory; initializing every flyweight object up front is also easy
* state objects can also be flyweights if states are safe to reuse
* "stay off the UI thread" - UI programmer idiom
* threading with observer-subject is tricky, grabbing a lock that your subject holds is an immediate deadlock, consider Event Queue instead
* tricky when observers are freed, they need to deregister from subjects (requires keeping a list) or use smart pointers on the subject side (perf overhead)
* if your subject has-an observer, that is performant but not flexible
* we use Component and Type Object to avoid enshrining each monster type in its own class, more flexible options to model game actors
* types are first class in JavaScript, Python, Ruby, but not so much in C++; Type Object helps
* JS take on prototypes differs from Self in that it's much less about cloning objects and more about assigning a delegate object (the "prototype" prop on a JS object)
* consider that the singleton get func can be a factory method that switches on platform config
* controlling exactly when objects are constructed isn't just about handling slow ops during a loading state, but also about controlling memory layout to help avoid fragmentation
* buffering can be useful for game state when we want all changes to be applied at once, to avoid having later parts of the update loop act on changes that happened earlier in the loop (eg. Conway's Life)
* two approaches to buffer swap: have a reference to the active buffer (but beware other systems holding references to buffer data), or copy data from buffer to active on swap (expensive)
* Gang of Four style state machine has states as objects, they are either static (initialized once at start-up) or dynamically allocated; consider having onEnter, onExit, onUpdate, onInput methods

# Concepts

* Achievements (Trophies) System - observer-subject can be good fit; listen to game events, decouple those events from achievements
* Aspect-Oriented Programming - meant to address the problem of cross-cutting concerns
* Assert - halt the program if a condition is not met, typically only enabled in debug builds, useful for tracking down bugs faster, "fail fast"
* Behaviour Trees - a more complex state system commonly used for game AI
* Chain of Responsibility pattern - when commands act in complex ways on subordinates, etc.
* Collection of Object Double Buffer - each actor keeps a second copy of its internal state and has a "swap" method that is called at the end of the frame; this makes swapping as a whole a slower op
* Command pattern - a reified function call, first-class function, closure, partially applied function; object-oriented replacement for callbacks, encapsulates a request for queuing and replay purposes; eg. adding a layer of indirection between button inputs and game commands allows key rebinding, serialization, replay, AI control; consider having the command.execute method take in an actor to act on; if you have closures (eg. JS) consider using that for commands
* Concurrent State Machines - when an actor has multiple state machines that may even communicate with each other (eg. emit events or signals)
* Coupling / Decouple - modules of code are coupled if understanding one requires understanding the others; decoupled modules of code are independent of each other's assumptions
* Cross-Cutting Concern - something that broadly affects systems, eg. logging
* Data Binding - attempts to be smarter than Observer; may reduce tedious logic, tends to be heavyweight
* Dataflow Programming - attempts to be smarter than Observer
* Dependency Injection - rather than code reaching out to grab references to its dependencies, it is provided with those references
* Double Buffer - used in graphics to hide sequential drawing operations, presents the frame all at once; old frame data can be used to implement a simple motion blur
* Extrinsic State - data that is unique to an object instance (Flyweight)
* Finite State Machine (FSM) - states, inputs, transitions; not Turing complete
* Framebuffer - a memory allocation with pixel data in it
* Functional Reactive Programming - attempts to be smarter than Observer (where React gets its name?)
* Gang of Four - Erich Gamma, Richard Helm, Ralph Rohnson, John Vlissides
* Good Camper Rule - leave the campsite cleaner than you found it
* Hierarchical State Machine - has superstates and substates, cascading inheritance that lets substates share common superstate data; typically inputs go to the sub-most state first and cascade up as long as they are unhandled
* Instanced Rendering - shared data (meshes, textures) between rendered instances of a model, provided in both OpenGL and DirectX
* Intrinsic State - "context-free" data that is shared between object instances (Flyweight)
* Lapsed Listener Problem - common with GCed runtimes, subject holds a reference keeping alive an observer; be diligent about deregistering observers
* Law of Demeter - violating this with a widely available object ("Player" or "Game") to centralize dependencies can be a crude form of dependency injection, better than resorting to a rat's nest of singletons
* Lazy Init Singleton - object is constructed on first use; alternative is static init which runs before main; allows for control over init order
* Metadata - a property of the data object itself and not the entity that the object represents, eg. prototype
* Model-View-Controller - invented by Smalltalk community, maybe; built on the Observer pattern
* Monolithic Double Buffer - the buffer is a continuous block of memory
* Object Pool - helps fight memory fragmentation, avoid alloc overhead
* Observer - in Observer-Subject, implements a listener interface; in C# use the `event` keyword, `delegate` is a ref to a method to call; in FP consider registering a callback func rather than implementing an interface
* Observer-Subject vs Event Systems - observe the subject vs observe the event; event systems are typically message queues and have dynamic alloc, whereas observers get func calls via an interface; still worthwhile to make events agnostic of their receiver
* Planning Systems - an approach to AI
* Property Bags - Steve Yegge called these the Universal Design Pattern
* Prototype - more of a lang paradigm than a pattern; create instances by cloning; useful for spawners, consider a spawn func closure instead of a prototype obj
* Prototype Inheritance langs are great for data definition
* Prototyping - often calls for throw-away code, but resist the temptation to "clean up" the code and keep it afterward
* Pure Function - no side effects, does not mutate global state
* Push-down Automata - has a stack of states, push into new states and pop out of them
* Reflection - reified type system
* Reify - thing-ify, make real, first-class, kept as data
* Service Locator - pattern, can help reduce use of Singleton
* Singleton - when there can only be one instance of a class, often to control access to a physical resource (eg. system driver); frequently does more harm than good; Gang of Four advised to use it sparingly; creates global state, makes systems harder to reason about, encourages tight coupling, makes concurrency difficult
* Static Init Singleton - if we are doing this, it's really not any different from a static class
* Subject - in Observer-Subject, holds a list of observers which register themselves, calls them via handler funcs
* Tearing - typically happens when only half of a frame is drawn before it is presented
* Template Metaprogramming - C++ compile-time code generation allows for abstract interfaces without any runtime impact (caveat: generating a lot of code that bloats the size of your binary has a runtime impact)
* Undo - consider adding a command undo method; store undo state on each command object, have a command stack that can rollback
* YAGNI - You Ain't Gonna Need It

# Techs

* BASIC - retro lang
* C++ - lingua franca of the games industry
* Direct3D - graphics framework, has swap chains
* Finch - prototypal lang like Self, by Robert Nystrom; simple to implement, perhaps leaves too much complexity for the user
* Haskell - FP lang, only pure funcs allowed
* OpenGL - graphics framework, has swapBuffers func
* QuickBasic - Microsoft impl of Basic
* Scheme - FP lang
* Self - 1980s OOP lang; no classes, only prototypes; failed lookups delegate to object parent which can be changed at runtime; inspired JavaScript
* Sketchpad - 1963, origin of some OOP patterns
* Think C - compiler for Mac
* TRS-80 - retro computer
* XNA - graphics framework by Microsoft, swaps buffer on endDraw() call

# Names Dropped

* Antoine Saint-Exupery - perfection is achieved when there is nothing left to take away
* Blaise Pascal - "I would have written a shorter letter, but I did not have the time."
* Brendan Eich - creator of JavaScript; prototype object based language made JS easy to implement, first version took only 10 days
* Dave Ungar - co-creator of Self
* Ivan Sutherland - creator of Sketchpad
* Randall Smith - co-creator of Self
* Will Wright - game designer

# Publications

* A Pattern Language - Christopher Alexander, Sarah Ishikawa, Murray Silverstein; influenced the Gang of Four
* Design Patterns: Elements of Reusable Object-Oriented Software - Erich Gamma, Richard Helm, Ralph Rohnson, John Vlissides
* Game Programming Gems - book series, provides "a la carte" advice

# Code

* `EventListener` - in JS, can register an event listener, but can also just register a func closure which is more common

```
// example of using closure as a command
function makeMoveUnitCommand(unit, x, y) {
  return function() {
    unit.moveTo(x, y);
  }
}
```

```
// example of a flyweight for terrain quads
const TerrainTile& World::getTerrainTile(unsigned int x, unsigned int y) const {
  const unsigned int i = y * width + x;
  assert(i < width * height);
  return *tiles[i];
}
```
