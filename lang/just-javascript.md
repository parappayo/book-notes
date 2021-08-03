# About

* [Just JavaScript](https://justjavascript.com/)
* by Dan Abramov, Maggie Appleton
* self-published in 2021

# Thoughts

Beginner-intermediate level course. Does what it says on the box: solidifies a mental model of JS's reference semantics. I did pick up some nifty bits and pieces. It's short.

# Take-Aways

How my JS mental model differs from this book is that I think of the reference itself as being a type of value, like a pointer in C, but in JS there is no "refernce type."

# Gotchas

* `typeof([])` is "object" - this is true, arrays are objects
* `typeof(null)` is "object" - old JS bug maintained for backward compat; JS values were stored in 32 bits with 3 bits for the type; [more insight here](https://2ality.com/2013/10/typeof-null.html)
* assigning to a string subscript (eg. `myStr[0]`) either has no effect or throws an error if you are in strict mode
* do not think of properties or objects being "nested," since members always refer to other values
* funcs take values as args, so changing the value of an arg doesn't work; `function addOne(x) { x = x + 1; }` has no effect on the value of `let x = 1; addOne(x);` but you could change members of an object passed in as an arg

# Concepts

* `-0` - used in floating point math because often the most important part of a calc is the resulting sign
* `1n` - suffix of n denotes BigInt
* `__proto__` - dunder proto; object property; set to another object to use that as a cascading parent; useful to model "is-a" relationships; all objects have the Object Prototype, if you set proto to null then the object will not even have built-in props
* `const` - alternative to `let` that prevents the value from being reassigned, but it does not guard against mutation
* `hasOwnProperty()` - tells you whether property is on the object itself rather than being part of the prototype chain
* `Number.MAX_SAFE_INTEGER` - not all whole numbers greater than this can be represented exactly
* `Number.MIN_SAFE_INTEGER` - not all whole numbers less than this can be represented exactly
* `prompt()` - crude way of obtaining user input
* `prototype` - set this proprty to an object factory func, it automatically populates `__proto__` when called with `new`; old way of implementing classes
* `undefined` - represents a value that is unintentionally missing, unlike null which is assumed to be null on purpose, but in practice they are often used interchangeably
* Assignment Operator - left side cannot be a value, right side must be an expression
* BigInts - newer part of the JS runtime
* Classes - prior to JS support for this, people used `prototype`
* Expressions - always evaluate to a single value; variables resolve to their current value
* Fast Thinking - the default, pattern recognition
* Floating Point Math - don't worry about how this works exactly
* Functions - are objects, but `typeof` will say "function"
* Literal - an expression that is simply a value
* Loose Equality `==` - aka abstract equality, is arcane, typically avoided
* Mental Models - how we understand systems
* Mutation - setting properties on objects changes that data for every reference to that object
* Object - every non-primitive value is one of these; every time we create one, it is a new instance
* Object Prototype - common prototype to all objects, allows even empty objects to have properties
* Primitive Values - immutable part of the JS runtime environment, not objects; strings, numbers, null, undefined, booleans, symbols, BigInts
* Property - of an object, case-sensitive, like a var it refers to values; error is not thrown when trying to access a property that was not previously defined, instead it results in `undefined`
* Prototype Pollution - when code adds properties to the global prototype, causing unexpected members to appear elsewhere
* Rope - data structure for building strings out of immutable substrings
* Same Value Equality `Object.is` - true if the args are the same value (think object instance); can compare primitives too
* Shadowing - an object with a prototype shadows that prototype's property if the object itself has its own property with the same name
* Slow Thinking - careful, bug finding
* Strict Equality `===` - almost the same as Same Value Equality but with exceptions: `NaN === NaN` is false (prefer to use `Number.isNaN`) and `-0 === 0` is true
* Strings - not objects even though you can call methods on them; in JS primitives are not objects
* Values - separate from code; primitives, objects, functions
* Variables - do not reference each other, can only reference values; do not have types, only the values that they reference have types

# Publications

* Thinking Fast and Slow - Daniel Kahneman book
* [2ality](https://2ality.com/) - Axel Rauschmayer blog
