
# About

* [The Imposter's Handbook](https://bigmachine.io/products/the-imposters-handbook/)
* by Rob Conery
* published by Big Machine Inc, November 2016

# Thoughts

A light, accessable overview of core Computing Science concepts. It attempts to provide practical context, but strays into being too casual and has some major errors. Tone is a matter of taste: this book might reach some people, but might seem condescending or dumbed-down to others. I like what this book is trying to be but I wish it was stronger overall.

# Take-Aways

* Ability comes from a combination of knowledge, practice, and aptitude
* Embrace being wrong, it is the path to growth; but if you cross the line from "I think that," to "this is how it is," then you'd better be right
* Hard tech stuff is chunks of knowledge with names you don't know yet; if a college student can learn it, so can you?

# Concepts

* `(x => x)(y)` - ES2016 lambda syntax, identity function with invocation on it
* Boolean Satisfiability Problem (SAT) - whether a given set of boolean terms can be satisfied
* Church Encoding - how Lambda Calculus represents data
* Church Encoding Conditional - `λx.λy.λz.x y z`
* Church Encoding Natural Number - uses successor style calls; eg. 3 = `λf.λx.f(f(f(x)))`
* Church's Thesis - all total functions are computable
* Clique - set of nodes that each connect to every other node in the set; identifying a clique is NP-Complete
* Combinator - higher-order function in Lambda Calculus
* Communications of the ACM - monthly journal of the Association for Computing Machinery
* Complexity Class - P, NP, NP-Complete, NP-Hard, Exp, etc. are orders of time complexity
* Complexity Theory - categorizes problems by complexity class
* Computing Science - focus is on data structures, algorithms, complexity
* Constant Function - `λx.y`, note that here x is a bound variable and y is a free variable
* Cook-Levin Theorem - Leonid Levin, Stephen Cook; any NP problem can be reduced to SAT
* Currying - Lambda Calculus functions only have one variable (arity of one), so currying is necessary to have multiple bound variables, eg. `λx.λy.t`
* Decision Problem Reduction - pattern where an optimization problem is replaced by a simpler decision problem; eg. find the optimal path vs. is the given path valid
* ES2016 - JavaScript standard / dialect
* Identity Function - `λx.x`
* Imposter Syndrome - an anxiety that is tickled by knowledge gaps
* Karp's 21 NP-Complete Problems - includes SAT, 0-1 Integer, Clique, Set Packing, Vertex Cover, Directed Hamiltonian Circuit, 3-SAT, Chromatic Number / Graph Coloring, Exact Cover, Hitting Set, Steiner Tree, Knapsack, etc.
* Knapsack - given set of items with weight, value, choose a set that maximizes value while meeting a weight limit constraint; NP-Complete
* Magicicada - cicadas that emerge from the ground on a period of 7, 13, or 17 years; evolutionary trait, may be to avoid overlapping emergences
* Markov Chain - imposter trigger
* Monad - imposter trigger
* Nondeterministically Polynomial (NP) - set of problems that can be solved in polynomial time given a "lucky guess" or an oracle; solvable in exponential time, but a solution can be verified in polynomial time
* NP-Complete - decision problems classifiable in NP
* NP-Hard - problems not in NP but that can be reduced to NP decision problems; often combinatorial problems
* Omega Combinator / Ω Combinator - `λx.xx (λx.xx)`, self-replicating, endless loop
* P=NP? - will we ever be able to solve problems nondeterministically?
* Recursive (R) - the set of all computable functions
* Reducibility Among Combinatorial Problems - paper by Richard Karp, expanding on work by Cook and Levin
* Sieve of Eratosthenes - prime number generator from around 250 BC
* Software Engineering - focus is on project management, testing, profiling, iterating, shipping
* Substitution - in Lambda Calculus, use the syntax `λx.x[x:=y]` means that we are substituting the bound variable x for another variable, y
* The Halting Problem - posited by Turning, not a member of R; example of an undecidable problem
* Travelling Salesman - classic NP-Hard problem; the nearest-neighbour greedy algorithm returns a path within 25% the length of the optimal solution on average
* Ubiquity Symposium - a type of organized debate
* Weak Law of Large Numbers - Bernoulli; results converge on a pattern over many samples
* Y Combinator / Fixed-Point Combinator - `λf. (λx. f (x x))(λx. f (x x))` recursive, fixed-point function; acts as a quine; calls the function you give it, and returns the function again, used to "bootstrap" recursion; in ES2016, `let Y = f => (x => x(x))(x => f(y => x(x)(y)));`

# Techs

* Analytical Engine - mechanical computer, successor to the Difference Engine, had something like a general purpose assembly language with variables and branching
* Apple II - popular PC in the 1980s
* Bombe - Alan Turing computer, 1939
* Colossus Mark I - Tommy Flowers computer, predecessor to ENIAC
* Difference Engine - mechanical computer designed by Babbage around 1820
* EDVAC - successor to ENIAC
* ENIAC - first general purpose electronic computer
* Jacquard Loom - programmable loom
* Note G - algorithm for the Analytical Engine to compute Bernoulli Numbers, program by Ada Lovelace, the first published computer program implementation
* TRS-80 - Tandy computer

# Names Dropped

* Ada Lovelace - widely regarded as the first computer programmer, daughter of Lord Byron, started working with Babbage in 1833
* Alan Turing
* Alonso Church - invented Lambda Calculus in the 1930s
* Chad Fowler - CTO of Wunderlist, VC for BlueYard Captial
* Charles Babbage
* John Conery - author's brother, wrote [a paper on the nature of computation](https://ubiquity.acm.org/article.cfm?id=1889839) for the ACM
* Plato - hypothesized that the world we see is an abstraction of its true form
* Scott Hanselman - works on Open Source .NET at Microsoft

# Publications

* [Church Encoding in JS](https://github.com/benji6/church) - Ben Hall github repo
* [Ruby Conf 12 - Y Not- Adventures in Functional Programming](https://www.youtube.com/watch?v=FITJMJjASUs) by Jim Weirich
* [The Y Combinator (no, not that one)](https://medium.com/@ayanonagon/the-y-combinator-no-not-that-one-7268d8d9c46#.czis6rxni) - Ayaka Nonaka article, introduces Y Combinator and Omega Combinator 
* MIT Open Courseware - learning resource
* The Code - 2011 BBC show
* Your Favourite NP-Complete Cheat Sheet - article by Jeff Atwood

# Code

```
// ES2016 Lambda Conditional
let True  = (x => y => x);
let False = (x => y => y);
let If = (x => y => z => x(y)(z));
If ( True )( "true" )( "false" ); // "true"
If ( False )( "true" )( "false" ); // "false"
```
