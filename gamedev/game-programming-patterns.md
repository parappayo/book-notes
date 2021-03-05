
# About

* [Game Programming Patterns](https://gameprogrammingpatterns.com/)
* by Robert Nystrom
* published Genever Benning, 2011

# Thoughts

Good criticism of game dev lack of practices. Maybe a shortcut to reading Gang of Four's book.

# Take-Aways

* "There is no right answer, just different flavours of wrong."
* a good solution is a distillation of code, rather than an accretion of it
* three-way tradeoff between performance, maintainability, and developer speed
* code architecture is about enabling change; paging into a simian cerebrum over optic nerve is slow; decouple code to reduce the amount of context needed to make sensible changes
* over-engineered architecture makes it hard to find code that does real work
* optimization thrives on limitations; tension with game design
* speculative abstraction is risky; the wrong abstraction is worse than code duplication
* engineering challenges common to games projects: time sequencing, compressed dev cycles, emergent behaviour, performance
* game dev books are typically either domain-specific (rendering, AI, physics, etc.) or whole-engine (discuss each component that goes into a particular type of game)
* if you have many potential flyweight objects and are unsure on init which ones will actually be used, consider having a lazy flyweight factory; initializing every flyweight object up front is also easy
* state objects can also be flyweights if states are safe to reuse

# Concepts

* Chain of Responsibility pattern - when commands act in complex ways on subordinates, etc.
* Command pattern - a reified function call, first-class function, closure, partially applied function; object-oriented replacement for callbacks, encapsulates a request for queuing and replay purposes; eg. adding a layer of indirection between button inputs and game commands allows key rebinding, serialization, replay, AI control; consider having the command.execute method take in an actor to act on; if you have closures (eg. JS) consider using that for commands
* Coupling / Decouple - modules of code are coupled if understanding one requires understanding the others; decoupled modules of code are independent of each other's assumptions
* Extrinsic State - data that is unique to an object instance (Flyweight)
* Gang of Four - Erich Gamma, Richard Helm, Ralph Rohnson, John Vlissides
* Good Camper Rule - leave the campsite cleaner than you found it
* Instanced Rendering - shared data (meshes, textures) between rendered instances of a model, provided in both OpenGL and DirectX
* Intrinsic State - "context-free" data that is shared between object instances (Flyweight)
* Prototyping - often calls for throw-away code, but resist the temptation to "clean up" the code and keep it afterward
* Reflection - reified type system
* Reify - thing-ify, make real, first-class, kept as data
* Template Metaprogramming - C++ compile-time code generation allows for abstract interfaces without any runtime impact (caveat: generating a lot of code that bloats the size of your binary has a runtime impact)
* Undo - consider adding a command.undo method, storing undo state on each command object, having a command stack that can rollback
* YAGNI - You Ain't Gonna Need It

# Techs

* BASIC - retro lang
* C++ - lingua franca of the games industry
* QuickBasic - Microsoft impl of Basic
* Think C - compiler for Mac
* TRS-80 - retro computer

# Names Dropped

* Antoine Saint-Exupery - perfection is achieved when there is nothing left to take away
* Blaise Pascal - "I would have written a shorter letter, but I did not have the time."
* Will Wright - game designer

# Publications

* A Pattern Language - Christopher Alexander, Sarah Ishikawa, Murray Silverstein; influenced the Gang of Four
* Design Patterns: Elements of Reusable Object-Oriented Software - Erich Gamma, Richard Helm, Ralph Rohnson, John Vlissides
* Game Programming Gems - book series, provides "a la carte" advice

# Code

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
