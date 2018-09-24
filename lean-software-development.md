
# About

* [Lean Software Development: An Agile Toolkit](https://books.google.ca/books?id=IJ1gAgAAQBAJ)
* by Mary Poppendieck, Tom Poppendieck
* published by Addison-Wesley, 2003

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
* Maximizing resource utilization does not maximize value delivered if the resources are being used inefficiently. Having some slack in the system is often necessary for healthy optimization and maximum value delivery. Consider the performance of a web server if its CPU, memory, and disk are all running at capacity.
* The cost of delays in software projects are typically underestimated: introduction date tends to dominate long-term profitability. Being early to market is crucial.
* Consider that a project status page should summarize the current iteration (goals, what's done, what's in-progress, what's backlog) and overall mission (past accomplishments, future goals.)
* Post scientific management programs included MBO, TQM, Zero Defects, Optimized Operations, Service Excellence, ISO9000, Total Improvement Program, and Customers First. Badly applied management methodology intensifies job dissatisfaction factors (policy, supervision, administration) rather than promoting job satisfaction factors (achievement, recognition, responsibility.)
* Discard the idea that workers are motivated by their pay, and ask what will engage them to participate. Motivation requires a clear, achievable purpose, self-direction, feedback, and freedom from skepticism. This is built on a foundation of belonging (honesty, succeed or fail as a team), safety (tolerance, trust), competence (confidence), and progress (celebrate milestones,)
* Leadership differs from management. Managers tackle complexity and use planning, organization, and control. Leaders tackle change by setting direction, enabling colleagues, and motivating the team.
* Much knowledge is tacit and will never properly be documented or captured; encourage knowledge transfer through team interaction.

# Concepts

* Acceptance Tests Written And Passed - metric that show convergence as progress of features being built up
* Adaptive Development - Agile can be thought of as creating options that allow decisions to be delayed until requirements are better understood; premature design commitment is a design failure mode that restricts learning, exacerbates the impact of defects, limits product usefulness, and increases cost of change
* Agile
* Applied Ratio - metric for utilization; often incorrectly tied to profit (utilization = value delivered) except that utilization in of itself does not necessarily add any value; consider that maximization of CPU or memory usage does not mean a computer is "fast"
* Architecture Matrix - synchronization approach that has teams agree on a system architecture and interfaces before building subsystems
* Burn Down Chart - shows convergence as backlog being reduced
* Capability Maturity Model (CMM) - developed by Watts Humphrey; used as a certification program, tends to create bureaucracy and make changes difficult although that is not the intent; see also ISO9000
* Capability Maturity Model Integration (CMMI) - introduced to replace CMM around 2003, developed by SEI to incorporate the lessons of several maturity models; underlying assumptions are alarmingly similar to Scientific Management (central control and i/o optimization rather than holistic view and distributed decision-making)
* Center of Excellence - where learning occurs and standards of excellence are established within an organization
* Concurrent Development - deferring decisions to build a system in rough even while design is in progress; developers work closely with stakeholders and anticipate emerging requirements
* Convergence - a concern about rapid iterations is the lack of a predefined stopping point; there is no guarantee that the project will converge on a solution
* Crystal
* Cycle Time - total service time from queue entry until service complete
* Death March - as defined by Yourdon, a project whose project parameters are > 1.5 times typical
* Earl Wheeler, former head of IBM's software business: "the key thrust was delegating power down. It was like magic! Improved quality, productivity, and morale."
* Enrico Zaninotto - economist
* Extreme Programming
* Feature-Driven Development (FDD) - individual ownership of code modules; agile typically recommends common ownership
* Gantt Chart - used in waterfall to identify the critical path; a better approach is to work in small batches
* Harold Thimbleby 1988 paper in IEEE Software - Delaying Commitment - when faced with a new situation, experts delay firm decisions and investigate while amateurs over-commit to early decisions
* Intuitive Decision Making - knowing from experience what course to take without having to decide between options; it is more important to develop the expertise to make wise decisions than to develop processes that think for people
* ISO9000 certification - good at documenting process but creates resistence to change; can capture a successful organization structure, but does not help create one; bias toward documentation and standardization of process, and bias away from change; they are best applied after processes are made lean, otherwise they slow the rate of change and lock-in existing bad practices
* Jim McCarthy of Microsoft: "I can't emphasize enough the importance of empowerment, of the team being accountable to itself for its success."
* John Kotter - people cannot be managed into battle, they must be led
* Kanban - sign / placard; tracking system for restocking, it follows a pull system pattern for just-in-time delivery; requests emerge based on simple rules rather than being centrally controlled
* Kenneth Thomas - "people are hardwired to care about purposes"
* Last Responsible Moment - when failing to make a decision would eliminate an important alternative; beyond this point decisions will be made by default; a bias toward late commitment must not degenerate into a tendency to avoid commitment
* Lean Construction Institute - advises that construction sites should use a weekly schedule instead of a master plan
* Materials Requirements Planning (MRP) - scheduling tool; fails to account for variation amplifying down a chain of connected events
* Options - in financial markets, a mechanism for deferred decisions; typically provides an opportunity to profit from positive events (stock price rises) while limiting exposure to negative events (stock price falls); Eric Beinhocker quote about the 1988 Comdex trade show, where Microsoft had not yet committed to Windows as its strategy for the future, instead had several options open
* Point-Based Decision Making - start by applying a proposed solution and course correct as new requirements as uncovered; as opposed to Set-Based Decision Making
* Profit & Loss (P&L) - report typically used to decide whether to approve an investment
* Program Evaluation Review Technique (PERT) - waterfall style management methodology developed by the US Navy in the 1950s
* Project Parameters - project scope, time, quality, risks, costs, etc.
* Pull Systems - team members pull down work requests, rather than waiting for management to decide on a schedule and push out work requests
* Queueing Theory - study of how wait lines operate; considers cycle time as a measure of efficiency; can optimize rate of arrival (traffic shaping) or rate of service; some slack in the system often makes it more efficient, eg. avoid congestion
* Raymonde Guidon - studied experienced software designers in 1990, found that they freely move between problem examination, clarifying requirements, high-level problem decomposition, and low-level implementation ideas when faced with a loosely designed problem
* Scientific Management - managers optimize processes based on performance metrics; eg. engineers stand on a factory line and tell workers how to do their jobs; typically relies on pay to motivate workers; made obsolete by Lean Manufacturing
* Set-Based Decision Making - gather options as a set, apply constraints to narrow the possibilites; as opposed to Point-Based Decision Making
* Seven Lean Principles - Eliminate Waste, Amplify Learning, Wait to Decide, Deliver Fast, Empower the Team, Build Integrity In, See the Whole
* Seven Wastes of Manufacturing - Inventory, Extra Processing, Overproduction, Transportation, Waiting, Motion, Defects
* Shigeo Shingo - lean manufacturing expert, identifies seven types of waste: inventory, extra processing, overproduction, transportation, waiting, motion, defects
* Slack Time - 3M practice of giving people 15% of their time at work for self-chosen projects
* Software Engineering Institute (SEI)
* Spanning Application - a cross-cutting demo application of the system used to synchronize the efforts of various teams, like a vertical slice
* Standish Group Study - typically 45% of features are never used, and 19% are rarely used
* Synchronization - needed when requirements overlap; can be enforced by frequent prototype versions, commonly daily builds and smoke tests
* Theory Of Constraints - recommends focusing on bottlenecks in the organization; optimizations to a non-bottlenecked stream are ineffective
* Thrashing - occurs when a project responds so rapidly to feedback that no momentum develops in any one direction; a tight feedback loop and flexible priorities help to avoid this
* Toyota Production System - created by Taiichi Ohno
* Value Stream Mapping - graphical depiction of delays in production due to waiting on each step in a process; eg. an aluminum can may spend 300+ days in a production chain but only 3 hours of that time being processed; Kent Beck recommends spending about 30 minutes building a map, to keep it simple
* Visual Controls - what Alistair Cockburn calls Information Radiators; progress reports including the kanban board, burndown chart, acceptance test chart; telegraph progress to enable self-directing work
* William McKnight - implemented the 3M innovation formula; "Hire good people, and leave them alone." "If you put fences around people, you get sheep. Give people the room that they need."
* Winston Royce - proposed in 1970 that testing should happen early in software dev to generate feedback while it is most valuable
* Work-in-Queue - amount of work waiting for service, roughly proportional to cycle time
* Work-Out program - used by General Electric; teams surface best practices to their managers, inverting the control chain; successful process improvement and knowledge sharing technique
* Zero Defects Mentality - US Army - tolerate no mistakes, tends to kill motivation

# Books

* Adaptive Software Development - Jim Highsmith
* Agile Software Development with Scrum - Schwaber and Beedle book
* Classics in Software Engineering - Edward Yourdon
* Death March - Edward Yourdon
* Developing Products in Half the Time - Reinertsen and Smith
* Intrinsic Motivation at Work - Kenneth Thomas book
* Lean Thinking - Womack and Jones
* Managing the Design Factory - Donald Reinertsen book
* One More Time: How Do You Motivate Employees? - Frederick Herzberg book
* Slack - Tom DeMarco book
* Strategy as Simple Rules - article by Kathleen Eisenhart and Donald Sull
* The Machine that Changed the World - Womack, Jones, Roo
