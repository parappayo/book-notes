
# About

* [Programming TypeScript](https://www.oreilly.com/library/view/programming-typescript/9781492037644/)
* by Boris Cherny
* published O'Reilly, 2019

# Thoughts

A fairly formal look; more about what TypeScript is, less about how to use it.

# Take-Aways

* TypeScript emits JavaScript, complete build process is roughly TypeScript code -> AST -> JavaScript -> AST -> JIT compiled bytecode -> runtime
* JavaScript errs on the side of doing "something" rather than throwing exceptions
* null and undefined tend to be used interchangeably but there are subtle differences

# Concepts

* `&` - type intersection operator, take all of the members of both types
* `...` - spread operator, useful for immutable data funcs
* `bigint` - large integer type
* `never` - return type of a function that never returns, eg. a function that immediately throws; I assume that this cannot be inferred in general due to the Halting Problem
* `object` - as a type, similar to the empty object type `{}`, best avoided
* `symbol` - type useful for keys, never equal to any other symbol; new in ES2015
* `unknown` - unlike `any`, need to refine it to a more specific type to do much
* `void` - return type of a function that has no return value
* `{}` - empty object type, every value except null or undefined is assignable to this; best avoided
* `|` - type union operator, either/or of the given types
* Abstract Syntax Tree (AST) - parser takes text as input and produces this
* Arrays - `T[]` and `Array<T>` syntax mean the same; best practice for arrays to be homogenous
* Bytecode - compiler takes AST as input and outputs this, type checking happens between
* const enums - a little more strict than enums
* Definite Assignment - compiler disallows use of uninitialized variables
* Document Object Model (DOM) - doc tree
* Don't Repeat Yourself (DRY) - popularized by Andrew Hunt and Dave Thomas in The Pragmatic Programmer, often over-used
* Dynamic Type Binding - when code needs to be evaluated in order to determine types; JS does this
* enums - either a map from strings to strings or a map from strings to numbers; by convention the keys are capitalized; can be split across multiple declarations, compiler merges them; lots of pitfalls, good practice to avoid enums
* esnext - typically the most recent JS language spec
* Explicitly Typed - compiler requires lots of type annotations; C and Java do this
* Gradually Typed - type checker infers as many types as it can, but compilation continues even when some types are undetermined; TypeScript, Python, Ruby do this
* Incremental Compilation - when some code changes, only code that depends on it needs to be rebuilt
* Index Signature - `[key: T] :U` on an object, all members with key of type T must have a value of type U; T must be assignable to either integer or string; `[key: number] :string` is common, for example
* JavaScript - often considered to be an interpreted lang, but is JIT compiled
* noImplicitAny - tsconfig.json setting, disallows assuming type of `any`; included with strict
* Nominal Typing - type is determined by name
* preserveConstEnums - tsconfig.json setting, enables runtime enum generation so that inlined enum values aren't broken by package changes, etc.
* Readonly Array - can only use nonmutating methods on it
* Rest Elements - `...` syntax with tuples, allows a varying number of members
* Runtime - takes bytecode as input, evaluates it
* Self-Hosting Compiler - when the compiler is written in the lang that it compiles
* strictNullChecks - tsconfig.json option; older versions of TypeScript had null as a subtype of every type (every type was nullable) and disabling this option brings back that behaviour
* Structural Typing / Duck Typing - type is inferred from object properties; TS infers object shape from object literals, follow with `as const` to make members `readonly`
* Type - a set of values and the operations on them
* Type Alias - using `type` keyword
* Type Annotations - code that tells the type checker what types are expected
* Type Inferencing - type checker applies rules to decide what types fit the code; Haskell, OCaml infer types aggressively, Scala and TypeScript are more gradually typed; TypeScript automatically assigns types to variables when they are assigned a compile-time constant
* Type Literal - type that is only allowed to be a given value, eg. `:true`
* Type Safety - when types enforce code validity, eg. cannot append to an integer or sum strings
* Type System - the type safety rules of a lang; typically either requires the user to be explicit or uses type inference
* Type-Driven Development - thinking about types at author time
* Typechecker - verifies type safety
* Types - like arrays, but of fixed length and each position has an explicitly declared type
* Unit Tests - static type checking replaces some of these
* Value Type - immutable data; as opposed to a reference
* Weakly Typed - compiler allows lots of type conversions, even ones that don't make much sense; JS does this

# Techs

* `npm init` - init a NodeJS project, generates package.json
* `tsc` - TypeScript compiler CLI, itself written in TypeScript, runs on NodeJS, provided as an npm package
* `tslint --init` - generates tslint.json config
* `typescript-node-starter` - scaffolding tool, generate a blank project structure
* Atom - code editor
* Babel - JS build tool
* Chakra - JS runtime engine, used in Edge
* ImmutableJS - Lee Byron lib for immutable collections, performant
* JSCore - JS runtime engine, used in Safari
* NodeJS - popular JS runtime, uses V8
* SpiderMonkey - JS runtime engine, used in Firefox
* Sublime Text - popular code editor
* tsconfig.json - TypeScript compiler config
* TSLint - TypeScript linter
* V8 - JS runtime engine, used in Chrome, Opera
* Vim - code editor
* VSCode - IDE with a good TypeScript experience
* WebStorm - IDE

# Names Dropped

* Tony Hoare - inventor of QuickSort; created the concept of a null reference in 1965 as part of Algol W, later called it the "billion dollar mistake"

# Publications

* https://github.com/bcherny/programming-typescript-answers

# Code
