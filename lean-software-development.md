
# About

[Lean Software Development: An Agile Toolkit](https://books.google.ca/books?id=IJ1gAgAAQBAJ)
by Mary Poppendieck, Tom Poppendieck
published by Addison-Wesley, 2003

# Thoughts

A fantastic book overall. On-point about the principles that lead to success in software development. Describes a great many frustrations that experienced developers feel when dealing with inexperienced or ineffective management. It feels like this book would burn any Electronic Arts executive to touch.

# Take-Aways

* Focus on adopting lean principles, not practices. Practices follow from principles, and should be continually decided upon by teams rather than dictated by management.
* Software development is a design process, not a production process. A common mistake is to apply production principles (execution through conformance to requirements, consistency, getting it right the first time) to software development instead of design principles (creating solutions that are a best fit by embracing variable results and rapid iteration.)
* Work in small batches. By shortening the feedback loop, your project responds to observations rather than predictions. Features should not span iterations. Project tooling needs to support rapid iteration (CI, TDD.)
* Conservative management principles stifle lean design practices: conservative management wants to uphold early planning decisions, feels threatened by feedback and learning, fights for more discipline in reaction to mistakes, and demands adherence to rigidly defined processes.
* Increase feedback to deal with project challenges: test early to catch defects sooner, write experimental code instead of more docs, gather stakeholder feedback instead of formalizing requirements, evaluate new tools, release experimental features sooner with small front-ends, and focus on immediate customers.
* Distributed decision-making and concurrent processes tend to out-perform centralized decision-making and sequential processes.
* Defer decisions until they are needed, avoid making irreversible decisions. Favour set-based decision making: consider multiple options in parallel and converge on a solution. Use early iterations to explore options and later iterations to eliminate options. Ask each stakeholder what solutions could work, look for intersections.
* The most natural process for software development is short learning cycles comprised of investigation, experimentation, and analysis. It should be cheap to test and experiment, but tempered with peer review. The optimal failure rate for an experiment to generate new information is 50%.
* Only analysis and coding contribute to the final product, but all software development steps cost time and money - Winston Royce
* Inventory is a form of waste; in software, this can be unfinished code, dead code, obsolete documentation, unnecessary features, backlog of tasks, etc.
* Belief in the escalating cost of design changes (Barry Bohem quote about fixing a software problem after delivery costing 100 times more) may drive one-shot sequential design process, but the sequential process itself is often the cause of the high cost escalation. Build tolerance for change rather than trying to avoid making changes.
* Tools for building software to tolerate change includes defining helpful interfaces (encapsulating variation), modularizing code (separating concerns), using declarative or functional programming (rather than sequential), using common tools (frameworks should be extracted from successful implementations, not built on speculation), and deferring future work (YAGNI).
* Depth-first and breadth-first decision making is affected by personality: explorative types may be better suited for planning phases while doers may be better suited for creation and delivery phases.

# Concepts

* Acceptance Tests Written And Passed - metric that show convergence as progress of features being built up
* Adaptive Development - Agile can be thought of as creating options that allow decisions to be delayed until requirements are better understood; premature design commitment is a design failure mode that restricts learning, exacerbates the impact of defects, limits product usefulness, and increases cost of change
* Agile
* Architecture Matrix - synchronization approach that has teams agree on a system architecture and interfaces before building subsystems
* Burn Down Chart - shows convergence as backlog being reduced
* Concurrent Development - deferring decisions to build a system in rough even while design is in progress; developers work closely with stakeholders and anticipate emerging requirements
* Convergence - a concern about rapid iterations is the lack of a predefined stopping point; there is no guarantee that the project will converge on a solution
* Crystal
* Death March - as defined by Yourdon, a project whose project parameters are > 1.5 times typical
* Enrico Zaninotto - economist
* Extreme Programming
* Feature-Driven Development (FDD) - individual ownership of code modules; agile typically recommends common ownership
* Harold Thimbleby 1988 paper in IEEE Software - Delaying Commitment - when faced with a new situation, experts delay firm decisions and investigate while amateurs over-commit to early decisions
* Intuitive Decision Making - knowing from experience what course to take without having to decide between options; it is more important to develop the expertise to make wise decisions than to develop processes that think for people
* ISO9000 certification - good at documenting process but creates resistence to change; can capture a successful organization structure, but does not help create one
* Last Responsible Moment - when failing to make a decision would eliminate an important alternative; beyond this point decisions will be made by default; a bias toward late commitment must not degenerate into a tendency to avoid commitment
* Options - in financial markets, a mechanism for deferred decisions; typically provides an opportunity to profit from positive events (stock price rises) while limiting exposure to negative events (stock price falls); Eric Beinhocker quote about the 1988 Comdex trade show, where Microsoft had not yet committed to Windows as its strategy for the future, instead had several options open
* Point-Based Decision Making - start by applying a proposed solution and course correct as new requirements as uncovered; as opposed to Set-Based Decision Making
* Project Parameters - project scope, time, quality, risks, costs, etc.
* Raymonde Guidon - studied experienced software designers in 1990, found that they freely move between problem examination, clarifying requirements, high-level problem decomposition, and low-level implementation ideas when faced with a loosely designed problem
* Set-Based Decision Making - gather options as a set, apply constraints to narrow the possibilites; as opposed to Point-Based Decision Making
* Seven Lean Principles - Eliminate Waste, Amplify Learning, Wait to Decide, Deliver Fast, Empower the Team, Build Integrity In, See the Whole
* Seven Wastes of Manufacturing - Inventory, Extra Processing, Overproduction, Transportation, Waiting, Motion, Defects
* Shigeo Shingo - lean manufacturing expert, identifies seven types of waste: inventory, extra processing, overproduction, transportation, waiting, motion, defects
* Spanning Application - a cross-cutting demo application of the system used to synchronize the efforts of various teams, like a vertical slice
* Standish Group Study - typically 45% of features are never used, and 19% are rarely used
* Synchronization - needed when requirements overlap; can be enforced by frequent prototype versions, commonly daily builds and smoke tests
* Thrashing - occurs when a project responds so rapidly to feedback that no momentum develops in any one direction; a tight feedback loop and flexible priorities help to avoid this
* Toyota Production System - created by Taiichi Ohno
* Value Stream Mapping - graphical depiction of delays in production due to waiting on each step in a process; eg. an aluminum can may spend 300+ days in a production chain but only 3 hours of that time being processed; Kent Beck recommends spending about 30 minutes building a map, to keep it simple
* Winston Royce - proposed in 1970 that testing should happen early in software dev to generate feedback while it is most valuable

# Books

* Adaptive Software Development - Jim Highsmith
* Classics in Software Engineering - Edward Yourdon
* Death March - Edward Yourdon
* Developing Products in Half the Time - Reinertsen
* Lean Thinking - Womack and Jones
* Strategy as Simple Rules 0 article by Kathleen Eisenhart and Donald Sull
* The Machine that Changed the World - Womack, Jones, Roo
