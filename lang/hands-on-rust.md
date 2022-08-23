# About

* [Hands-On Rust](https://pragprog.com/titles/hwrust/hands-on-rust/)
* by Herbert Wolverson
* published by Pragmatic Bookshelf 2021

# Thoughts

* Teaches a Rust with bracket-lib and legion game dev stack, sometimes is more about the stack than Rust itself
* Funcs are too long for my taste, insufficient thought is given to testability
* Zealous use of preludes sacrifices clarity for convenience; harder to tell what symbols come from what dependency libs
* Does that game-dev thing of needless renamings, eg. `ctx: BTerm` and `ecs: World` instead of the more obvious `term: BTerm` and `world: World`, just call it the thing that it is

# Concepts

* `#[derive(Debug)]` - add debug print formatter support to a struct
* `&` - reference to a variable, borrows the reference when used as a func param
* `?` - operator, bubbles Result error enum up to caller
* `cargo clippy` - get linter advice
* `cargo fmt` - reformat source code
* `cargo new --vcs=none` - create a Rust package without using git
* `cargo run --release` - default is to run in debug, running is release enables optz
* `Clone` - derive from this to add a `clone` deep copy method
* `Copy` - derive from this to make copy semantics the default for your type
* `expect()` - unwraps a Result object
* `f32` - 32-bit float
* `i32` - 32-bit integer
* `if let` - shorthand for matching only one case, useful for dealing with Option
* `impl` - keyword to implement methods on a struct
* `let θ = π * Δ` is pretty code, but editing it is a pain
* `mut` - make a variable mutable, they are immutable by default
* `Option` - enum containing Some(x) or None
* `PartialEq` - derive from this to implement `==` for your type
* `Self` - shorthand for the type of self
* `use crate::` - can import from crate root
* `use super::` - can import from parent module
* `usize` - arch dependent size int, often used to index collections
* `vec!` - macro to initialize a vector from an array initializer
* `{:#?}` - pretty print formatter
* `{:?}` - debug print formatter, useful to inspect variables
* `{}` - formatted string placeholder, built-in string formatter is powerful
* `​#![warn(clippy::all, clippy::pedantic)]` - add to top of file to make Clippy pedantic, the Rust version of `-Wall` except that it may be overkill
* Array - fixed size list of values, must all be the same type
* Associated Function - of a type, member list does not include self
* Borrowed Reference - using `&`, allows pass-by-ref but only one scope can have the reference at a time; use `&mut` to allow the callee to change it
* Builder Pattern - used to construct objects
* Code Page 437 - IBM Extended ASCII char set
* Code Smell - a hint that your code is unclean
* CommandBuffer - Legion passes this to a system, used to queue up tasks to be executed after the system update is finished; eg. `CommandBuffer.remove(entity)` to remove an entity at the end of the frame
* Component - of ECS, added to entities, describes properties of an entity
* Constructor - func that creates an instance of a type
* crates - Rust packages, managed by Cargo
* Data-Oriented Design
* Derive Macro - add functionality to a struct, a mix-in
* Destructuring Assignment - uses curly braces, extracts member values
* Dog-Leg Corridors - have a horizontal and a vertical section
* DrawBatch - of bracket-lib, used to allow async rendering, finalize the frame with `render_draw_buffer`
* DRY Principle - Don't Repeat Yourself
* Entities - in ECS, part of the game sim, could be manifested in the game environment
* Entity  - of ECS, can be any piece of state, has components attached; Legion components can be read-only or writable for a given entity
* Entity-Component System (ECS)
* Entity-Component System (ECS) - aims to efficiently manage large game state data
* Entry Point - main, where the program starts
* Enumeration - `enum`, type where the valid values are from a predefined set; enumeration values can have members on them, eg. a state enum could have substate data in it, `Some(x)`
* Fearless Concurrency - a feature of Rust
* Feature Flags - toggle optional crate functionality, can be defined in cargo.toml under "features" for each dependency crate
* Flexible Console - bracket-lib allows rendering characters at any pixel coordinate
* Game Design Document - formal design
* Game Engine - handles platform dependent functionality so that the dev can focus on game-specific content
* Game Loop - render state, read input, update state (tick), repeat
* Game State - the game sim world
* Generics - eg. `Vec<T>`
* Immediate Mode Rendering - opposite of batched drawing, render commands are executed at the time they are called
* Instance - of a type, an object
* Integrated Development Environment (IDE)
* JetBrains - IDE vendor
* Law of Demeter - promotes loose coupling between modules
* Layers - organize the order in which sprites are drawn, with bracket-lib we can use `BTermBuilder::with_simple_console_no_bg` to create transparent layers and `BTerm::set_active_console` to switch between them
* LINQ - powerful .NET iterator syntax
* Macro - calls include `!`, powerful syntax beyond what funcs provide
* Magic Number - hard-coded constants are a code smell
* Member Function - of a type, takes self as a param
* Methods - of a type, funcs that operate on instances of the type
* Minimal Viable Product (MVP)
* Minimum Viable Product (MVP) - what you must have to complete the project
* Modules - must be declared with `mod`, nestable; compiled in parallel, speeding up build times; file-based or directory-based; scope is private by default, use `pub` to expose things
* modules defined at the crate root level are automatically public
* Morton Encoding - aka Z-order Curve; fancy way of trying to arrange cells in memory so that adjacent cells are close together
* Multi-File Module - lives in a directory, has a mod.rs file
* Namespaces - crates and modules are both namespaces
* Nethack - dungeon crawler game
* Pattern Matching - tests a condition and optionally extracts member data; use `_` to match the remaining values
* Pre-release Versions - crates with a major version of 0 are pre-release and no backward compatibility is assured
* Prelude Module - little bit like a TypeScript barrel file
* Prelude Module - used to organize imports
* Procedural Macros - aka proc macros, `#[derive(...)]` syntax, can contribute to Rust code feeling like a magic black box
* Programmer Art - rough placeholders
* Queries - in legion, take a list of components and return all entities that contain all of those components; `<ComponentA, ComponentB>::query()`
* ranges - powerful C++20 iterator syntax
* Resources - of game engines, assets, data
* Rogue - dungeon crawler game
* Row-First Encoding - cells in a row are consecutive in memory
* Rust's borrowed reference semantics guards against data race conditions
* Scheduler - of Legion, run systems; uses info about which entities read and write which component to schedule updates
* Scope - denoted by curly braces
* Semver - semantic versioning, crates use it
* Snake Case - lowercase with underscores, Rust convention
* Sprints - little milestones
* State Machine - typically a finite state automata
* String - `String` is the dynamic string type, `str` is the immutable string literal type
* String Literal - `&str` type, supports unicode
* SubWorld - like World but with only components you've requested
* Swiss Army Knife - idiom for a catch-all tool
* Systems - of ECS, query entities to implement some functionality, eg. the renderer, the physics sim
* Tag - an empty component that marks an entity as being something without adding state
* Tiles - in our grid-based game, cellular representation of the game environment
* Tom's Obvious, Minimal Language (TOML) - config format, Cargo files use this
* Traits - like interfaces
* traits - Rust version of interfaces
* Tupes - use parens, useful to return multiple values
* Vector - list of values, dynamic length
* Version Control System (VCS) - manages code project revisions
* Workspace, Rust - groups multiple Rust projects
* World - in Legion, holds all entities; can `push` entities to it
* xorshift - random number generator
* Yala - Yet Another Lost Amulet

# Techs

* Amethyst - Rust game engine
* BASIC - lang
* BBC Micro, Model B - retro computer
* bracket-lib - text-based game engine, Herbert Wolverson is the primary author
* bracket-terminal - the display part of bracelet-lib, emulated console with broad rendering support
* C - low-level lang
* C++ - lang
* Cargo - Rust build tool, package manager
* Cargo - Rust package manager
* CLion - JetBrains IDE, integrates with Rust
* Clippy - Rust linter
* Code Complete - famous book
* Emacs - text editor, integrates with Rust Analyzer and Rust Language Server
* GEdit - simple text editor
* Gimp - open source 2d graphics editor
* git - popular VCS
* Godot - game engine
* IntelliJ - JetBrains IDE, integrates with Rust
* Kate - simple text editor
* Legion - open-source ECS crate
* Linux - Unix-derived OS
* Mac OS X - Unix-derived commercial OS
* Mercurial - VCS
* Metal - graphics API for Mac
* Neovim - text editor, integrates with Rust Analyzer and Rust Language Server
* Notepad++ - simple text editor
* OpenGL - graphics API
* Pascal - lang
* Perforce - commercial VCS
* Rust - lang, minor updates every 6 weeks, major updates every few years
* rustfmt - Rust code formatter
* RustUp - tool to install the Rust toolchain
* Sublime Text - commercial text editor, has Rust plug-ins
* Subversion - VCS
* toolchain - Rust compiler and supporting tools, your dev env
* Unity - commercial game engine
* Unreal - commercial game engine
* vim - text editor, integrates with Rust Analyzer and Rust Language Server
* Visual Studio Code - Microsoft IDE, Rust Analyzer and CodeLLDB plug-ins are good options for Rust integration
* Vulkan - graphics API
* WebAssembly
* Windows - Microsoft commercial OS that does not ship with its own dev tools

# Publications

* crates.io - Cargo package repository
* Dungeon Crawl Stone Soup - game, free tiles: https://github.com/crawl/tiles
* Hello World Collection - "hello world" in 578 langs
* Minesweeper - grid-based game
* Nox Futura - game
* Reddit - online communities, has Rust and game dev help
* Repton - puzzle game
* Rust by Example - online book
* The Rust Programming Language - No Starch book

# Names Dropped

* Buch - creator of some sprite art, https://opengameart.org/content/unfinished-dungeon-tileset
* Chris Hamons - curator of the Dungeon Crawl Stone Soup sprite art set, CCo licensed
* Melissa Krautheim - creator of sprite art, [Fantasy Magic Set](https://opengameart.org/content/fantasy-magic-set)
* Melle - creator of sprite art, [Fantasy Sword Set](https://opengameart.org/content/fantasy-sword-set)
