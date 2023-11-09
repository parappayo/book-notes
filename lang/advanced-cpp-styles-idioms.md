# About

* [Advanced C++ Styles and Idioms](https://books.google.ca/books/about/Advanced_C++_Programming_Styles_and_Idio.html?id=AKJQAAAAMAAJ)
* by James Coplien
* published by Addison-Wesley, 1992
* [Archive.org link](https://archive.org/details/advancedcbsprogr00copl/)

# Take-Aways

* docs don't capture everything; a book on child rearing won't explain why your kid is weird
* C++ beat out other OOP langs with compile-time type safety and runtime efficiency; standardization efforts started in 1989; accepts compiler complexity to help the user
* two major design principles behind C++ were automatic initialization of variables (constructors) and classes controlling their own memory allocation (destructors)
* beware initialization order when using global extern consts where the value is calculated at runtime rather than compile time

# Concepts

* 80/20 Rule - when optimizing, look for the 20% of the code where your program spends 80% of its time
* `((X*)0)->f()` - non-portable hack to simulate static member functions; no reasonable semantics are guaranteed
* `delete[]` - deletes a vector of objects, use this when `new[]` was used
* `inline` - inline funcs must be defined before they are used; typically better than preprocessor macros, can be configured compiler flags, may be better optimized by the compiler; member functions are considered inline automatically if the definition is part of the declaration
* `protected` - introduced so that devs would use `friend` less
* `while (*cp1++ = *cp2++);`
* Abstract Data Type (ADT) - defines the interface to data without any implementation details
* Algol 68 - lang, 1968, influenced C++
* Anarchical Language - provides a very broad programming model, gives the user incoherent options for the software architecture, makes it difficult to establish idioms
* Bliss - lang
* C - lang, 1973
* C-with-classes - lang, 1980
* CAD System - computer-aided design; software used for designing mechanical parts
* Canonical Forms - patterns that complete the underlying language, eg. separating construction from initialization
* Class - signifies that a structure is being used as a user-defined type (abstract data type), not merely a data record; members are private by default
* Classes - implementations of ADTs, introduced by Simula 67
* Clu - lang
* Concrete Data Type - user-defined type that can be used like built-in types
* Constness - const methods can reference their object through an alias to `this`, the compiler cannot know; legitimate reasons to subvert const-correctness include modifying object state that is not relevant to application state, such as debugging info or optimizing the data structure (eg. rebalance a tree, sort a set)
* CRC Cards - bonus content; Class-Responsibility-Collaborator, used in Object-Oriented Design
* Destructor - can have space between ~ and class name, but conventionally don't
* Dynamic Multiple Inheritance - alternative to static multiple inheritance; avoids the combinatorial explosion of types
* Exemplars - objects that take on some of the roles that people often use classes for
* Flavours - early Lisp machine OOP lang designed by Howard Cannon at MIT
* Functors - function object, alternative to function pointers
* Idiom - familiarity with commonly applied ideas is part of mastery; gleaned from experience, gives the lang its character
* Incremental Loading - updating code at runtime
* Indigenous Type - part of the core lang, built-in; eg. `int`, `float`; these types are not automatically intialized
* Inheritance Fever - over-zealous OOP use of is-a relations
* iostream - makes it seem like `operator<<` was designed for I/O, whereas the core C++ language actually provides no I/O capability
* Manifest Constants - constant values in the code; `#define` gives these symbolic names, in C++ const symbols are preferred
* Member Functions - functions on a class; structs can also have them
* Mesa - lang
* Meta-Features - by providing useful building blocks instead of specifying too much, the language provides idioms to provide features beyond what is in the core lang
* Object Inversion - instead of data being organized into structs and having functions operate on those structs, the functions belong to the type itself; the object-oriented design is inside-out compared to the structured programming design
* Object-Oriented Programming (OOP) - evolved alongside Object-Oriented Design; objects are often known as entities in OOD
* Paradigm - pattern for dividing the world into manageable parts
* Release 3.0 - C++ standard; Release 3 of the AT&T USL Language System
* RLC circuit - a type of electronic filter; resistor, inductor, capacitor in series; step response is the output generated when the voltage changes abruptly, can be overdamped, underdamped, or critically damped; formulae to model this are the same as for a mass attached to a spring moving through a medium of some viscosity
* Simula - lang, 1967, influenced C++
* Smalltalk - OOP lang, 1980; don't try to write C++ as if it were this
* Smart Pointers - pointer-like objects
* State - of an object, the values of all of its members
* Static Data Members - unlike global constants, they do not pollute the namespace, access control modifiers can be applied to them
* Static Member Functions - typically manage resources common to all instances of the class
* Struct - from C, proto-class like type, represents a data record; in C the tag and type are separate things, so the struct has an identifier and a separate typedef; members are public by default
* Style - makes the difference between accomplishment and excellence; goes beyond rote knowledge
* Symbolic Language - more in the style of Smalltalk or Lisp
* T* This = (T*)this; // easy hack to circumvent const-correctness, modern C++ uses const_cast<T*> this
* Typed Langs - invented in the 1950s to improve runtime efficiency; over time type safety became a tool for improving program correctness
* Tyrannical Language - constrains the programming model, opinionated about the software architecture, improves transparency of the code
* Weak Typing - aka Dynamic Typing; simulated in C++ through indirection

# Techs

* GNU C++ - compiler
* Sun Workstation - hardware platform
* Zortech C++ - compiler

# Names Dropped

* Don Stein - some kind of electrical engineer
* Stroustrup - good programming and good design are the result of taste, insight, and experience

# Publications

* C++ Annotated Reference Manual - Margaret Ellis and Stroustrup book
