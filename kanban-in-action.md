
# About

* [Kanban in Action](https://www.manning.com/books/kanban-in-action)
* by Marcus Hammarberg and Joakim Sundén
* published by Manning Publications, 2014

# Thoughts

Perhaps not a concise introduction to the topic, but includes many helpful references.

# Take-Aways

* Stop starting, start finishing! Never be blocked.
* Introducing transparency can threaten the status-quo, be cautious
* Sticky notes should be pulled off sideways to prevent them from curling up
* Problems are valuable opportunities to improve process, handle them with care
* Waste can be a red herring, also focus on reducing lead times and managing risk
* Flow matters most when managing high risk; consider fire fighter idle time spent being prepared to respond
* Maximizing utilization is an anti-pattern, focus on of faster flow; customers don't care that you're busy, they want you to deliver; be aware that sometimes utilization does matter more than flow (eg. at the bottleneck)
* Kanban is a visual system, utilizes the brain's capacity to grok visualizations; reduce wait times by visualizing the state of work and making it ready for the next state
* The goal is not to limit WIP, but to improve flow; limiting WIP is how to expose process improvements (draining the river)
* Common challenges: deliver late, inaccurate estimates, swamped with work, unclear priorities, work requests coming from many sources, unclear task assignments
* Inspect and adapt; don't try to define the ideal process, capture how things currently work and revisit it frequently; a goal of the process is to generate discussions about the process
* Teams define their own processes, task flow from investigation through planning, development, delivery, and customer validation; don't over-think it, plan to make continuous improvements
* KPIs often fail, but Lead Time and Throughput are relatively easy to track and worthwhile; the team should choose their own metrics
* Process improvements eventually involve identifying upstream and downstream dependencies of the team; Kanban spreads outward
* Physical vs software boards; physical boards are bigger, more flexible, encourage community, tactile experience of physical cards promotes ownership and aids memory; software boards are more reliable, remote-friendly, automatically track metrics
* Drive improvements from observed problems; avoid basing changes on assumptions
* Define entry and exit criteria on Kanban board columns, reduce assumptions about what the columns mean
* Specifications have an expiry date; they go out of date relatively quickly
* Code that isn't integrated has an expiry date; it will likely eventually have merge conflicts, implement a feature that is no longer needed, and / or be done in an obsolete style
* WIP limit can be per-person rather than per-phase, typical when there is no hand-off from start to completion of a task
* WIP limit can be per-swimlane, can define "teamlets" as sub-project work in swimlanes
* Inventory and batching are places for problems to hide; waste lengthens feedback loops (having a problem, discovering it, delivering a fix)
* Failing to remember mistakes and having to relearn is a form of waste, both at the team and individual level

# Concepts

* Andon Boards - used by Toyota; reflect the state of production, where help is needed
* Andon Cord - stop-the-line cord, everything halts while the issue is resolved; yellow-light state calls attention to the problem, red-light means the line has stopped
* Avatars - colourful representations of team members make it visually easy to identify task owners; should resemble the person so that the mapping is clear
* Behaviour Driven Development (BDD) - specification by example
* Big Daily - inter-team stand-up, often an effort to improve org-wide comm
* Blockers - special class of waiting; often perceived to be outside of the team's control, but this typically is not the case (consider follow-ing up, applying pressure, proceeding with fakes, splitting the work item up, helping with other WIP items); track time spent blocked
* Build Quality In - Lean principle; helps to avoid rework
* Card Smells - stuck in a state too long, confusing information, disagreement over whether task is "done"
* Component Team - organized around a system component or service; eg. database team, networking team, UI team; may increase inter-team communication load; try not to organize teams such that the slowest team sets the pace
* Context Switching - one study found a 10 IQ point drop per context switch, more than the amount found from being high on pot
* CONWIP - constant WIP, one limit for the whole board; more common approach is to have per-column limits
* Cross-Functional Team - has a variety of skills and capabilities, less dependent on other teams
* Daily Scrum - Scrum's version of the daily standup
* Daily Standup - focus on work items (pull from the right), not what individual people are doing; people tend to be on time for meetings that are consistent, short, focused, engaging, start promptly
* Deadlines - should stand out on the tickets, should be hard dates; timeboxing is another thing
* Elevation Improvement - process improvement that increases capacity at the bottleneck, often expensive
* Expedite Lane - for high priority work that overrides other WIP
* Exploit the Bottleneck - maximize efficiency at the bottleneck; cheaper than an elevation improvement; queues keep the bottleneck busy, but avoid the Ketchup Effect (even out the arrival of new work); to be efficient, build in quality, prioritize work, limit interruptions
* Extreme Ticket Smells - use an actual banana peel that degrades with blocker age, so the ticket literally smells
* Failure Demand - work caused by failure to serve the customer right the first time; eg. call center fielding customer complaints, bugs, redesign and rework
* Feature Team - organized around a project feature, ideally is cross-functional and can independently deliver the feature
* Five Focusing Steps - from The Goal; identify the constraint, exploit the constraint, subordinate all other work to the constraint, elevate the constraint, repeat (the bottleneck has probably moved elsewhere)
* Gold Plating - continuing work past the point where it add value; adding unnecessary features
* Information Fridge - data is available but hard to find; in the fridge you have to rummage around for what you want; there are often locks, restricted access
* Information Radiator - tool that makes data clear and accessible; big, obvious at a glance
* Just in Time Delivery - no work "just in case," only in response to a need
* Kanban - from the Japanese "kan-ban," literally "signal card," Kanban tickets should be stickes on a board; not prescriptive, adapts the process that your team already has (unlike Scrum, XP, and RUP); timestamp cards with "in" and "out" to track lead times; card designs should make it obvious how to prioritize, err on the side of simplicity; blocked tickets should be clearly visible, consider separate blocker stickies over top of the blocked tickets, add info about why it is blocked, call out how long the ticket has been blocked for; typical colour scheme is green for maintenance (paying down technical debt / escalating risk), yellow for feature work (improving service), red for bugs (ensuring quality); consider drawing progress bars; emoji / emoticon for each ticket can be a useful metric (per user, per day?)
* Kanban Core Practices - visualize, limit WIP, manage flow, make processes explicit, use feedback, evolve experimentally (use models and measurements) / be Lean
* Kanban Kata - formalized process improvement process
* Kanban Method, The - capital-K Kanban, defined by David J. Anderson
* Kanban Principles - start where you are, pursue incremental improvement, leadership at all levels
* Kanban System - lower-case-k Kanban, visual process management; each visual aid is "a kanban"
* Ketchup Effect - nothing, nothing, nothing, then blam, everything happens at once
* Lead Time - how long it takes for a ticket to go through the entire process
* Lead Times - longer lead times means it takes longer to respond to platform changes, increases risk, drives a vicious cycle of decreasing quality
* Little's Law - cycle time = work in process / throughput; by John DC Little; cycle time aka lead time
* Mieruka - Japanese for "visualization;" many small visual guides provide transparency; bright outlines of tools show where everything is supposed to go when not being used
* Mob Programming - pioneered by Woody Zuill; temporary WIP limit of one, entire team is looking at the same task
* One-Piece Continuous Flow - Toyota workflow ideal, each deliverable progresses one value-adding step at a time without batching or stockpiling of inventory; work is delivered just-in-time, on demand
* Penny Flipping Game - each worker flips pennies in a batch and passes along; smaller batches cause more work per individual worker but faster delivery overall
* Prime Directive of Agile Development - never be blocked
* Problem - an unrealized improvement opportunity
* Pull Principle - move work on the Kanban board starting from the right side first (the work items furthest along in the flow)
* Quality Software Management: Systems Thinking - Gerald Weinberg book; as much as 10% of time per parallel project is lost due to context switching
* Rational Unified Process (RUP) - alternative to Scrum, prescriptive
* Release Sync - meeting to discuss what is being released today; may evolve out of inter-team "big daily"
* Retro Meetings - can be triggered by a metric, eg. after every so many tickets get marked done
* Return on Time Invested (ROTI) - determine whether spending time was a waste
* Self Organization - Kanban board should enable team members to independently decide what to work on next
* Seven Forms of Waste - Partially Done Work, Extra Features (Overproduction), Relearning, Handoffs, Delays, Task Switching, Defects
* Specification by Example - work item defined by example use case, done when the example is satisfied
* Spontaneous Kaizen - ad-hoc process improvement meeting, often occurs in response to a problem being identified
* Sticky Questions - when a question is taken "offline," visualize it by putting a sticky note with the question on the person who asked it
* Swarming - issue arises, several people jump on the problem to resolve it quickly
* Swim Lane - a track for work tickets to follow; eg. the expedite lane, used for high priority tickets
* T-Shirt Sizes - small, medium, large, etc. alternative to story points
* Task Flow - task journey from investigation through planning and development to delivery and customer approval; team defines their own stages
* Theory of Constraints (TOC) - there is always a bottleneck; process is limited by constraints, effective organizations continually identify constraints and adapt
* Throughput - how many tickets arrive in the finished state over a given timeframe
* Timeboxing - iteration of a set length, allows scope to vary; spend the time and get as far as one can
* Toyota Production Systems (TPS) - not to be confused with Testing Procedure Specification
* Tracking IDs - it can make sense to put Jira ticket IDs on physical stickies; consider having a simplified workflow in Jira, fewer states
* User Story - describes a task as for whom (as a role), what (I want blah), and why (so that blah); considered an anti-pattern by some
* Value Demand - contrary to Failure Demand; when work requests add overall value to the platform, not just fixing how it should have been
* Work in Process (WIP) - smaller batches decreases lead time and creates slack time; balance fast flow and worker idle time; when WIP limit is too high, work sits idle; when WIP is too low, people sit idle; unfinished work is waste, including specs, merge requests, undeployed work, untested work, bugs; too much WIP causes increased context switching
* Work Items vs Tasks - task breakdown of steps like deployment and testing could be sub-ticketed or all considered one atomic "task"

# Techs

* HuBoard - Kanban board for GitHub
* Jira - Atlassian project management product; an information fridge
* Team Foundation Server (TFS) - Microsoft product with Kanban board feature, now called Azure DevOps Server

# Names Dropped

* Arne Roock - Without slack, there cannot be improvements.
* Corey Ladas - Kanban expert, blog
* David Joyce - Kanban expert; It's not "the more you start, the more you finish," it's "the more you finish, the more you finish."
* Don Reinertsen - keynote at the Lean Kanban Central Europe 2012 conference
* John Seddon - coined "Failure Demand"
* Martine Devos - Kanban expert
* Rachel Davies - Kanban expert
* Taiichi Ohno - there is no greater waste than over-production; in software, this is unnecessary features

# Publications

* Agile Software Development - Alistair Cockburn book; information radiators allow passers-by to answer their own questions
* CHAOS Report - The Standish Group - 45% of all software features are never used
* Clean Code - Rob Martin book
* Design Flaws, Hernias, and Anemic Quality - Scott Bellware article
* Freedom from Command and Control - John Seddon book
* Hill Street Blues - Swedish 80's cop show; "one more thing: let's be careful out there"
* Implementing Lean Software Development: From Concept to Cash - Mary and Tom Poppendieck book
* Kanban: Successful Evolutionary Change for Your Technology Business - David J. Anderson book
* Lean Kanban conference
* Lean Software Development - Mary and Tom Poppendieck book
* Personal Kanban - book by Jim Benson
* Refactoring: Improving the Design of Existing Code - Kent Beck, Martin Fowler book
* Specification by Example - Gojko Adzic book
* Tame the Flow - book by Steve Tendon, Wolfram Muller
* The Clean Coder - Rob Martin book
* The Goal - book by Eliyahu Goldratt, Jeff Cox
* The Toyota Way - book by Jeffrey Liker; Toyota is the inspiration of Kanban
* This is Lean: Resolving the Efficiency Paradox - Niklas Modig and Par Ahlstrom book; Lean is an ops strategy, increases resource efficiency by improving flow
* Toyota Production System: Beyond Large-Scale Production - Taiichi Ohno book; reduce the timeline between a customer order and a product delivery by reducing wastes
