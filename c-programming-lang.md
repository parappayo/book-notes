# About

* [The C Programming Language](https://en.wikipedia.org/wiki/The_C_Programming_Language)
* by Brian Kernighan and Dennis Ritchie
* published by Prentice-Hall 1978
* notes made from 2nd Edition published 1988

# Thoughts

The ol' classic. It's more dense than I remember. There are fewer formal terminology definitions than I expected.

# Take-Aways

* Not advisable to use this book as a compiler implementation reference
* The definition of a function declaration vs a function prototype is made clear (eg. section 1.7) in spite of what I heard in the 1990s
* C lacks many nice features: string or array operators, file I/O, heap allocation, multithreading, coroutines
* C is not strongly typed but has type checking; unsafe conversions are explicitly stated by the user
* A program consists of data object declarations (variables and constants, optionally with initial state) and operators organized into expressions that change data
* Sizes of numeric data types are machine dependent; `int` could be 16-bit, 32-bit, 64-bit or other, along with `short`, `long`
* Prior to ANSI C, function prototypes did not specify parameters and function definitions listed the types of parameters after the brackets but before the curlys
* Global vars are initialized once at start-up, automatic vars are initialized every time they enter scope
* Console histogram as horizontal bars is easy; vertical bars is more challenging

## Best Practices

* Stick to only looping related operations in for loop control operators
* For better portability, some bitmasks can be converted to the machine's word length at compile-time, eg. `~0` is MAX_INT regardless of bit length,  `x & 01` returns the value of the trailing bit regardless of bit length
* Adhere to Structured Programming (avoid goto)
* Define constants instead of sprinkling magic numbers

## Undefined Behaviours and Gotches

* C has fewer sequence points than you expect; evaluation order of operands is not enforced (except for `&&`, `||`, `?:`, `,`), evaluation order of function arguments is not enforced; avoid expressions that have side effects as these may depend on each other and lead to undefined behaviour; side effects on arguments must occur before a function is called
* Precedence of `!=` is higher than `=`, causes confusion eg. `(c = getchar()) != EOF`
* Enum values must be globally unique, no validation is done on the values of enum variables
* Bitwise Right Shift can be Arithmetic Shift or Logical Shift
* Be careful with negative floats; the truncation direction when dividing negative floating point values, and the sign of the result of `%`, are implementation dependent; overflow and underflow results are implementation dependent
* The default sign of `char` is implementation dependent; for portability, explicitly use `signed` or `unsigned` when non-character data is used
* A function declaration without params is taken as an "old style" declaration and does no argument checking; use void explicitly to avoid this (C++ rules are different, though)
* ANSI C standard guarantees significance of the first 31 chars of internal function and variable names, and only the first 6 characters for external (also case-sensitivity is not guaranteed); they are case-sensitive, by convention variables are lower-case and constants are upper-case
* Switch statement misspelling of "default" case will be interpreted as a jump label, chaos ensues

# Concepts

* `!` - unary negation; yields one if value is zero, yields zero otherwise
* `**` - Fortran exponent operator; not valid C, use the standard `pow` function
* `,` - operator; forces expression evaluation left to right; commas that separate function arguments are not comma operators, no order of evaluation is guaranteed
* `0` - prefix for octal constant
* `0x` - prefix for hex constant
* `;` - the statement terminator; in Pascal it is a statement separator
* `<ctype.h>` - defines char helper funcs like `tolower` and `isdigit`
* `<math.h>` - typically uses `double`
* `<string.h>` - lib for dealing with null-terminated strings
* `?` - ternary operator; only one of the expressions after the conditional is evaluated
* `\0` - null char, value of 0, sometimes defined as `NULL`
* `a.out` - common default binary executable output of a C compiler
* `continue` - similar to `break` but skips to the start of the next loop instead of exiting the loop
* `do`-`while` - equivalent to Pascal's `repeat`-`until`
* `double` - constants can be written `1.0` and / or have an exponent like `1e-2`
* `EOF` - end of file marker, type `int`; typical value is `-1`, defined in `stdio.h`
* `extern` keyword - declare global variables that are not defined earlier in the same file as current scope
* `float` - constants look like `double` constants but require a `f` suffix
* `getchar` - read a single char,  `stdio.h`
* `goto` - jumps to a label; considered harmful, see Structured Programming
* `long double` - extended floating point precision
* `long` - guaranteed to be no shorter than `int`; constants require a `L` suffix, eg. `123L`
* `printf` - text output, `stdio.h`
* `putchar` - write a single char,  `stdio.h`
* `scanf` - text input, `stdio.h`
* `short` - guaranteed to be no longer than `int`
* `strpbrk` - find location of first char in string1 that does not match any chars in string2
* `strtol` - string to long integer
* `U` suffix - can be used to specify that a constant is unsigned
* ANSI - American National Standards Institute, standardization body
* ANSI C - 1988 C standard; added standard library, function signatures, signed and unsigned integer types, compile time string concatenation, enumerations; see `--std=c89`
* Argument / Actual Argument - expression used in a function call to populate an argument
* Arithmetic Shift - right shift that fills the sign bit into the new digits
* ASCII character set
* Automatic Variable - allocated anew each time it enters scope
* Bitwise Operators - `&`, `|`, `^` (XOR), `<<`, `>>` (right shift sign bit behaviour is implementation dependent), `~` (One's Complement); precedence is lower than `==` operator, take care
* Block - compound statement, delimited by `{` and `}`, needs no `;`
* Boolean Operators - `&&`, `||` are evaluated left to right; eval stops when the expression's value is known (short-circuiting)
* Call by Reference / Pass by Reference - default for Fortran, `var` keyword in Pascal; C can accomplish this indirectly via pointers
* Cast - aka type coercion, explicit conversion
* Character Array - another name for a string
* Character Constant - a char in single quotes, may use an escape sequence
* Comments - do not nest, cannot start inside a string constant
* Compound Expression - block of expressions enclosed in curlys
* Constant Expression - can be evaluated at compile time
* Data Types - basic types are `char`, `int`, `float`, and `double`; there are many modifiers like `unsigned`, `short`, `long`, `const`; `int` can often be omitted
* Declaration, Variable Declaration - announces the properties of vars
* EBCDIC character set - has non-alpha characters between `A` and `Z`
* Enumeration Constant - `enum week { MON = 1, TUES, WEDS, THURS, FRI, SAT, SUN }`; be careful, names must be distinct across enumerations (no namespace); enumeration variable values are not enforced
* Escape Sequence - for string formatting, represents special chars like `\n`
* Expression - typically terminated in a semicolon
* External Variable / Global Variable - external to all functions and accessible anywhere, must be defined exactly once, see also `extern`; similar to Fortran `COMMON` keyword, Pascal also has globals
* Floating Point - `float`, `double`
* Fortran - C-like lang
* Function - C function is like a Fortran subroutine or function, or a Pascal procedure or function
* Function Prototype - a declaration, specifies the parameters and return type of a function; must agree with the function definition and any calls
* Header File - convention of placing function and variable declarations in a `.h` file that is used by `#include` in other source files
* Hex Escape Sequence - `\hxx` where h is a hex digit specifies a char constant
* Integer Types - `short`, `int`, `long`
* Leap Year - `(year % 4 == 0 && year % 100 != 0) || year % 400 == 0)`, almost correct
* Logical Shift - right shift that fills new bits with zeros
* Magic Numbers - having arbitrary constants in your code is a bad practice
* Null Statement - empty statement, terminated by a semicolon; eg. while loop with no body
* Octal Escape Sequence - `\ooo` where o is an octal digit specifies a char constant
* Parameter / Formal Argument - local variable named in a function definition
* Pascal - C-like lang
* Pass by Value - function arguments in C are passed this way, unlike Fortran; arrays are an exception, the name of an array acts like a pointer; note that automatic memory during function invocation is cheap, since moving the stack pointer is a constant time operation
* Preprocessor - performs macro substitution on program text, includes, conditional compilation
* Shell Short - invented by D. L. Shell in 1959
* Sign Extension - negative numbers have a left-most bit of 1
* Statement - an expression or compound expression
* Statement - expression followed by a semicolon
* String Concatenation - at compile time, `"hello," " world"` is equivalent to `"hello, world"`
* Subscript - value of an entry in an array, the index starts at 0 and can be any integer expression
* Switch Statement - fall-through behaviour is a mixed blessing; allows adjacent cases to share code, but a missing break wreaks havoc, also beware misspelling `default`
* Symbolic Name / Constant - one way to do this in C is with a `#define` macro; with modern compilers, prefer a `const` variable
* Text Stream - sequence of chars split on newlines

# Techs

* B - predecessor to C, by Ken Thompson, for Unix on the DEC PDP-7; typeless lang
* BCPL - predecessor to B and C, by Martin Richards; typeless lang
* C - designed for Unix on the DEC PDP-11, by Denis Ritchie; low-level, often called a systems programming lang
* DEC VAX 8550 - computer
* Honeywell 6000 - computer
* IBM System/370 - computer
* Interdata 8/32 - computer

# Publications

* The C Answer Book - contains exercise solutions

# Code

* `pic|tbl|eqn|troff -ms` - typesetting pipeline
* `%3.2f` - floating point formatter for printf; limits to 3 digits before the decimal, 2 after; omit the 3 part for unconstrained width
* `a[i] = i++;` - undefined behaviour
* `for (count = 0; x != 0; x &= (x-1)) { count++; }` - count bits
