
# About

* [Lean Software Development: An Agile Toolkit](https://books.google.ca/books?id=IJ1gAgAAQBAJ)
* by Mary Poppendieck, Tom Poppendieck
* published by Addison-Wesley, 2003

# Thoughts

A fantastic book. On-point about the principles that enable success in software development, as well as the stifling, downward spiral effect of conservative leadership. Describes a many frustrations that developers feel when dealing with ineffective management. Contact with this book would cause any Electronic Arts executive to burst into flames, like a vampire in the sun.

# Take-Aways

* Software development is a design process, not a production process; a common mistake is to apply production principles to software projects. Production principles include conformance to detailed requirements, delivering consistent results, and getting it right the first time. Design principles include embracing variable results, rapid iteration, and seeking best-fit solutions.
* Practices follow from principles; focus on adopting lean principles and let practices emerge. Practices should be decided by teams rather than dictated by management. Practices need to be continually updated and refined. Process certification programs may help to document successful practices, but hinder the creation of them.
* There are too many critical performance metrics to properly capture them individually. Aggregate performance metrics and offer bonuses and incentives for performance at one level higher, eg. team bonuses based on company performance or individual bonuses based on team performance. Protect against scrutiny of individual performance.
* When encountering difficulty, look to the bigger picture: drill down to root causes, eliminate constraints to growth, and incentivize aggregate performance one level up.
* Discard the idea that workers are motivated by their pay, and ask what will engage them to participate. Motivation requires a clear, achievable purpose, self-direction, feedback, and freedom from skepticism. This is built on a foundation of belonging (honesty, succeed or fail as a team), safety (tolerance, trust), competence (confidence), and progress (celebrate milestones.)
* Leadership differs from management. Managers tackle complexity and use planning, organization, and control. Leaders tackle change by setting direction, enabling colleagues, and motivating the team.
* Conservative management principles stifle lean design practices. Such principles include committing to early planning decisions, being threatened by feedback and learning, increasing discipline to avoid mistakes, and demanding adherence to rigidly defined processes. These principles are better suited for production processes, not design processes.
* Work in small batches to shorten feedback loops and respond to observations rather than predictions. Features should not span iterations. Project tooling (CI, TDD) needs to support rapid iteration.
* Increase feedback to in response to challenges. Test early to catch defects sooner, prototype experimental features, gather stakeholder feedback rather than formalizing requirements, evaluate new tools, and focus on immediate customers.
* Distributed decision-making and concurrent processes tend to out-perform centralized decision-making and sequential processes.
* Employ set-based decision making. Communicate constraints rather than features. Defer decisions until they are needed, and avoid making irreversible decisions. Use early iterations to explore options and later iterations to eliminate options.
* Premature design commitment is a design failure mode that restricts learning, obscures customer needs, exacerbates defects, and increases cost of change. Conservative management may over-specificy as a strategy for absolving responsibility, thus planning to fail. Document decisions, but don't make that a reason to decide early.
* The natural process for software development is short learning cycles comprised of investigation, experimentation, and analysis. Make it cheap to test and experiment, but tempered with peer review. The optimal failure rate for an experiment to generate new information is 50%.
* Inventory is a form of waste that risks obsolesence and undiscovered defects. In software, this includes unfinished code, dead code, obsolete documentation, unnecessary features, and tasks in the backlog. Rapidly delivery reduces risk by tying up fewer resources in-process.
* Only analysis and coding contribute to the final product, but all software development steps cost time and money - Winston Royce
* Build tolerance for change rather than trying to avoid making changes. Belief in the escalating cost of design changes (eg. Barry Bohem) drives one-shot sequential design processes, but the sequential process itself contributes to the cost escalation.
* Tools for software to tolerate change: interfaces (encapsulate variation), modular code (separate concerns), declarative or functional code (reduce sequential logic), standard tools, and deferred work (YAGNI).
* Frameworks should be extracted from successful implementations, not built on speculation.
* Depth-first and breadth-first decision making is affected by personality: explorative types may be better suited for planning phases while doers may be better suited for creation and delivery phases.
* Maximizing resource utilization oftend does not maximize value delivered. Having slack in the system is often necessary for system health and capacity to change. Consider the performance of a web server if its CPU, memory, and disk are all running at max capacity.
* The cost of delays in software projects are typically underestimated: introduction date tends to dominate long-term profitability. Being early to market is crucial.
* A project status page should summarize the current iteration (goals, what's done, what's in-progress, what's backlog) and overall mission (past accomplishments, future goals.)
* Post scientific management programs included MBO, TQM, Zero Defects, Optimized Operations, Service Excellence, ISO9000, Total Improvement Program, and Customers First. A badly applied management methodology intensifies employee dissatisfaction.
* Much knowledge is tacit and will never properly be documented or captured; encourage knowledge transfer through team interaction.
* Software dev performance factors include application domain knowledge across the entire staff, acceptance of change, capability to accommodate emerging design, and an environment that fosters good communication.
* Use integrated problem solving instead of "throw it over the wall." Avoid design process pipelines that isolate developers from customers. Engineers tend to lose sight of customer values amidst technical details; their vision for perceived integrity needs to be refreshed regularly.

# Concepts

* Acceptance Tests Written And Passed - metric showing convergence as progress of features being built up
* Adaptive Development - Agile can be thought of as creating options to defer decisions until requirements are better understood
* Agile - a form of Lean design practice
* Applied Ratio - metric for utilization, often incorrectly tied to profit; utilization does not necessarily add value
* Architecture Matrix - synchronization approach: teams agree on a system architecture and interfaces before building subsystems
* As-Built Documentation - docs that are up-to-date with the actual code; very difficult to have in practice
* Barry Bohem - quote about fixing a software problem after delivery costing 100 times more than when the problem was first introduced; quote about the best way to develop low-cost, high-quality software is to write less code (with Philip Papaccio)
* Burn Down Chart - shows convergence as backlog being reduced
* Capability Maturity Model (CMM) - developed by Watts Humphrey; used as a certification program, tends to add bureaucracy and hinder change although that is not the intent; see also ISO9000
* Capability Maturity Model Integration (CMMI) - introduced to replace CMM around 2003, developed by SEI to incorporate the lessons of several maturity models; underlying assumptions are alarmingly similar to Scientific Management (central control and i/o optimization rather than holistic view and distributed decision-making)
* Center of Excellence - where learning occurs and standards of excellence are established within an organization
* Co-Source Contract - shared development responsibility; vendor tends to be working themselves out of a job by enabling the client to take over the work
* Conceptual Domain Model - captures the problem domain from the user's point of view; all documentation should use domain language, not technical language
* Conceptual Integrity - the system's concepts work together cohesively; a prerequisite for perceived integrity, since without it usability suffers; requires organization-wide buy-in at every level; eg. online reservation system should not have dramatically different UI for slightly different kinds of reservation
* Concurrent Development - deferring decisions to build a system in rough even while design is in progress; developers work closely with stakeholders and anticipate emerging requirements
* Convergence - a concern about rapid iterations is the lack of a predefined stopping point; there is no guarantee that the project will converge on a solution
* Cost Plus Fixed Fee - type of target-cost contract - vendor works at cost and collects an additional fee on completion
* Crystal Methods - management methodologies developed by Alistair Cockburn in the mid-1990s
* Customer Tests aka Acceptance Tests - as opposed to developer tests (unit, integration, smoke); whether the customer's needs are met
* Cycle Time - from queuing theory, total service time from queue entry until service complete
* Death March - as defined by Yourdon, a project whose project parameters exceed 150% of typical
* Donald Norman - design researcher
* Earl Wheeler - former head of IBM's software business; "the key thrust was delegating power down. It was like magic! Improved quality, productivity, and morale."
* Enrico Zaninotto - economist
* Extreme Programming (XP) - software development methodology meant to improve responsiveness to customer needs
* Feature-Driven Development (FDD) - individual ownership of code modules; agile typically recommends common ownership
* Five Whys - a method to drill down to the root causes behind a problem
* Fixed-Price Contract - often goes to lowest bidder; can lead to a vendor hoping to profit from design changes; lowest bidder may not understand the true cost of the project and the customer ends up having to bail them out; encourages selfish customer behaviour
* Flexible-Price Contract aka Time-and-Expenses Contract - designed to deal with uncertainty, but merely shifts the risk from the vendor to the customer; under these the vendor lacks an incentive to be efficient; DoD tried using extensive vendor controls, but the controls themselves are costly; incremental development helps, small batches of work protect the customer from risk; encourages selfish vendor behaviour
* Gantt Chart - used in waterfall to identify the critical path; a better approach is to work in small batches
* Harold Thimbleby - wrote 1988 paper in IEEE Software, "Delaying Commitment;" when faced with a new situation, experts delay firm decisions and investigate while amateurs over-commit to early decisions
* Henry Petroski - engineering historian
* Integrated Problem Solving - understanding the problem and solving the problem happen in parallel; information is transmitted in frequent, small batches and in every direction; the opposite is the "throw it over the wall" approach
* Intuitive Decision Making - knowing from experience an effective course to take; it is more important to develop the expertise to make wise decisions than to develop processes that replace decision-making; how do you know whom to listen to? Dunning-Krueger is a potential problem
* ISO9000 certification - good at documenting process but creates resistence to change; can capture a successful organization structure, but does not help create one; bias toward documentation and standardization of process, and bias away from change; they are best applied after processes are made lean, otherwise they slow the rate of change and lock-in existing bad practices
* James Womack - "We suggest that 'faster is dearer' will now join 'quality costs more' on the junk heap of ideas left over from the age of mass production."
* Jay Forrester - system dynamics guru
* Jim McCarthy - of Microsoft, "I can't emphasize enough the importance of empowerment, of the team being accountable to itself for its success."
* Job Dissatisfaction Factors - policy, supervision, administration
* Job Satisfaction Factors - achievement, recognition, responsibility
* John Kotter - people cannot be managed into battle, they must be led
* Kanban - sign / placard; tracking system for restocking, it follows a pull system pattern for just-in-time delivery; requests emerge based on simple rules rather than being centrally controlled
* Kenneth Thomas - people are hardwired to care about purposes
* Kim Clark - of Harvard Business School, "integrity" is a differentiator between average and high-performing companies
* Last Responsible Moment - when failing to make a decision would eliminate an important alternative; beyond this point decisions will be made by default; deferring decisions must not degenerate into avoiding commitment
* Lean Construction Institute - advises that construction sites should use a weekly schedule instead of a master plan
* Limits To Growth - policies that improve performance often have secondary effects that limit their effectiveness; amplifying those policies can disproportionately increase the secondary effect and cause setbacks
* Materials Requirements Planning (MRP) - scheduling tool; fails to account for variation amplifying down a chain of connected events
* Multi-Stage Contracts - work has to be delivered up to a certain point to unlock the next stage of the contract
* OODA Loop - observe, orient, decide, act; developed by John Boyd
* Options - in financial markets, a mechanism for deferred decisions; typically provides an opportunity to profit from positive events (stock price rises) while limiting exposure to negative events (stock price falls); Eric Beinhocker quote about the 1988 Comdex trade show, where Microsoft had not yet committed to Windows as its strategy for the future, instead had several options open
* Perceived Integrity - the product achieves function, usability, reliability, and economy that delights its users; feels like the product anticipates what the user wants
* Point-Based Decision Making - start by applying a proposed solution and course correct as new requirements as uncovered; as opposed to Set-Based Decision Making
* Principle-Agent Problem - challenging to implement Agile when managers want to cover their own ass; remedy is to view success or failure as a team, not as individuals
* Profit & Loss (P&L) - report typically used to decide whether to approve an investment
* Profit Not To Exceed - type of target-cost contract - vendor collects a profit on work up to a target cost, reduces rates after; provides no incentive for early completion unless one is added
* Profit-schedule Contract - vendors and clients share in risk and reward
* Program Evaluation Review Technique (PERT) - waterfall style management methodology developed by the US Navy in the 1950s
* Project Parameters - project scope, time, quality, risks, costs, etc.
* Pull Systems - team members pull down work requests, rather than waiting for management to decide on a schedule and push out work requests
* Queueing Theory - study of how wait lines operate; considers cycle time as a measure of efficiency; can optimize rate of arrival (traffic shaping) or rate of service; some slack in the system often makes it more efficient, eg. avoid congestion
* Raymonde Guidon - studied experienced software designers in 1990, found that they freely move between problem examination, clarifying requirements, high-level problem decomposition, and low-level implementation ideas when faced with a loosely designed problem
* Scientific Management - managers optimize processes based on performance metrics; eg. engineers stand on a factory line and tell workers how to do their jobs; typically relies on pay to motivate workers; made obsolete by Lean Manufacturing
* Set-Based Decision Making - gather options as a set, apply constraints to narrow the possibilites; as opposed to Point-Based Decision Making; consider multiple options in parallel and converge on a solution; ask each stakeholder what solutions could work, look for intersections
* Seven Lean Principles - Eliminate Waste, Amplify Learning, Wait to Decide, Deliver Fast, Empower the Team, Build Integrity In, See the Whole
* Seven Wastes of Manufacturing - Inventory, Extra Processing, Overproduction, Transportation, Waiting, Motion, Defects
* Shifting The Burden - addressing symptoms rather than underlying causes
* Shigeo Shingo - lean manufacturing expert, identifies seven types of waste: inventory, extra processing, overproduction, transportation, waiting, motion, defects
* Six Sigma - management methodoloyg; has different flavours for production and development, make sure the right one is used
* Slack Time - 3M practice of giving people 15% of their time at work for self-chosen projects
* Software Engineering Institute (SEI)
* Spanning Application - a cross-cutting demo application of the system used to synchronize the efforts of various teams, like a vertical slice
* Standish Group Study - typically 45% of features are never used, and 19% are rarely used
* Suboptimization - too narrow of a focus on performance leads to local maximums; narrow utilization metrics (applied ratio) fail this way; even project cost and schedule concerns can be suboptimizations when they neglect the success of the organization
* Synchronization - needed when requirements overlap; can be enforced by frequent prototype versions, commonly daily builds and smoke tests
* Systems Dynamics - simulating an organization using a computer model
* Systems Thinking - analyzing how the parts of an organization interrelate; the broader impact of local policies is often poorly understood, and policies intended to address organizational problems may be making those problems worse
* Target-Cost Contracts - parties negotiate a split of who bears the cost of running over-budget, a split also applies if the project is under-budget, ie. the vendor gets a bonus; freedom is needed in order for customer requirements to take priority over being on-time and on-budget; encourages reducing scope as the most effective cost control measure; avoids over-specifying scope
* Target-Schedule Contracts - for when schedule matters more than cost; requires delivering features in priority order, deploying early
* Technical Qualifiers - captures basic functionality needed to deliver business value; what response time, availability, scalability, and security concerns are relevant to the product
* Theory Of Constraints - rather than pushing growth, find and remove limits to growth; yesterday's remedial policies may become today's bottlenecks
* Theory Of Constraints - recommends focusing on bottlenecks in the organization; optimizations to a non-bottlenecked stream are ineffective
* Thrashing - occurs when a project responds so rapidly to feedback that no momentum develops in any one direction; a tight feedback loop and flexible priorities help to avoid this
* Toyota Production System - created by Taiichi Ohno
* Trunk-Based Development - no release branches, ship latest from master, tight deployment loop
* Trust Gaps - especially important for stakeholders to believe that devs can / will deliver on what they promise
* Use Case Model - captures tacit knowledge about system usability; user stories
* Value Stream Mapping - graphical depiction of delays in production due to waiting on each step in a process; eg. an aluminum can may spend 300+ days in a production chain but only 3 hours of that time being processed; Kent Beck recommends spending about 30 minutes building a map, to keep it simple
* Visual Controls - what Alistair Cockburn calls Information Radiators; progress reports including the kanban board, burndown chart, acceptance test chart; telegraph progress to enable self-directing work
* William McKnight - implemented the 3M innovation formula; "Hire good people, and leave them alone." "If you put fences around people, you get sheep. Give people the room that they need."
* Winston Royce - proposed in 1970 that testing should happen early in software dev to generate feedback while it is most valuable
* Work-in-Queue - amount of work waiting for service, roughly proportional to cycle time
* Work-Out program - used by General Electric; teams surface best practices to their managers, inverting the control chain; successful process improvement and knowledge sharing technique
* Zero Defects Mentality - US Army - tolerate no mistakes, tends to kill motivation

# Challenges in Dysfunctional Management

This is a bonus section for me to riff on issues that inhibit Lean Development.

* Management in good faith - managers may want to limit the success of individual employees and even be willing to risk team failure for it. Principle-Agent problem, bi-directional Trust Gaps between management and teams.
* Recognizing simplicity - there may be disagreement over whether a minimal viable product was much less work to deliver than a fully realized version. Leads to "why didn't you just build what I asked?" Breaking work into smaller batches is hindered because management fails to appreciate why some work is "smaller" in the first place.
* Recognizing cleanliness - to a naive audience, clean code appears to be less work to produce than unnecessarily complicated code. There may be mistaken assumptions such that the clean code accomplishes less, handles fewer error cases, etc. Clean code may fool managers into thinking that the problem was not difficult to solve in the first place.
* Hero obsession - management may reward the last-minute hero who jumps at every crisis without asking why the crises keep occurring. Common assumption is that most software development crises are inevitable. Unethical developers learn to court crises knowing that they'll be valued more for fixing them later.
* Allowing velocity to build - various mis-management methods can stifle velocity, such demanding that a developer only work on one task at a time, only giving a developer menial tasks, only giving a developer hard tasks, etc.
* Assumption of isolation - management may set expectations assuming decoupled subsystems, leading to unpleasant surprises when changing system X breaks system Y. Test processes may be too narrow in scope and fail to account for the Butterfly Effect. Blame-oriented managers may blame today's troubleshooters for yesterday's job security coders.
* Excruciating pontification - managers, leads, and peers alike may be uninterested in sharing information effectively but make a lot of noise and take credit for it anyway. Mentorship can degenerate into hazing and talking-down.

# Books

* Adaptive Software Development - Jim Highsmith
* Agile Software Development with Scrum - Schwaber and Beedle
* Classics in Software Engineering - Edward Yourdon
* Death March - Edward Yourdon
* Developing Products in Half the Time - Reinertsen and Smith
* Domain Driven Design - Eric Evans
* Intrinsic Motivation at Work - Kenneth Thomas
* Lean Thinking - Womack and Jones
* Managing the Design Factory - Donald Reinertsen
* Measuring and Managing Performance in Organizations - Rob Austin
* One More Time: How Do You Motivate Employees? - Frederick Herzberg
* Product Development Performance - Kim Clark, Takahiro Fujimoto
* Slack - Tom DeMarco
* Software for Use - Larry Constantine and Lucy Lockwood
* The Machine that Changed the World - Womack, Jones, Roo

# See Also

* A Field Study of the Software Design Process for Large Systems - Bill Curtis
* Collaborative Advantage - Jeffrey Dyer documentary
* Strategy as Simple Rules - article by Kathleen Eisenhart and Donald Sull
