
# About

* [Kanban in Action](https://www.manning.com/books/kanban-in-action)
* by Marcus Hammarberg and Joakim Sundén
* published by Manning Publications, 2014

# Thoughts

# Take-Aways

* Stop starting and start finishing
* Anti-pattern is maximizing worker utilization instead of faster flow; customers seldom care if you're busy, they just want you to deliver stuff
* Problems are valuable opportunities to improve process; handle them with care
* Kanban is a visual system; utilize the brain's capacity to grok visualizations
* The goal is not to limit WIP, but to improve flow; limiting WIP is how to expose process improvements
* The common team challenges: often deliver late, inaccurate estimates, swamped with work, unclear priorities, work requests coming from many sources, unclear task assignments
* Inspect and adapt; don't try to define the ideal process, capture how things currently work and revisit it frequently; a goal of the process is to generate discussions about the process
* Teams define their own processes, task flow from investigation through planning, development, delivery, and customer validation; don't over-think it, plan to make continuous improvements
* KPIs often fail, but Lead Time and Throughput are relatively easy to track and worthwhile; the team should choose their own metrics
* Process improvements eventually involve identifying upstream and downstream dependencies of the team; Kanban spreads outward
* Introducing transparency can threaten the status-quo, be cautious
* Physical vs software boards; physical boards are bigger, more flexible, encourage community, tactile experience of physical cards promotes ownership and aids memory; software boards are more reliable, remote-friendly, automatically track metrics
* Drive improvements from observed problems; avoid basing changes on assumptions
* Define entry and exit criteria on Kanban board columns, reduce assumptions about what the columns mean
* Sticky notes should be pulled off sideways to prevent them from curling up
* Specifications have an expiry date; they go out of date relatively quickly
* Code that isn't integrated has an expiry date; it will likely eventually have merge conflicts, implement a feature that is no longer needed, and / or be done in an obsolete style
* WIP limit can be per-person rather than per-phase, typical when there is no hand-off from start to completion of a task
* WIP limit can be per-swimlane, can define "teamlets" as sub-project work in swimlanes

# Concepts

* Andon Boards - used by Toyota; reflect the state of production, where help is needed
* Andon Cord - stop-the-line cord, everything halts while the issue is resolved; yellow-light state calls attention to the problem, red-light means the line has stopped
* Avatars - colourful representations of team members make it visually easy to identify task owners; should resemble the person so that the mapping is clear
* Behaviour Driven Development (BDD) - specification by example
* Card Smells - stuck in a state too long, confusing information, disagreement over whether task is "done"
* Context Switching - one study found a 10 IQ point drop per context switch, more than the amount found from being high on pot
* CONWIP - constant WIP, one limit for the whole board; more common approach is to have per-column limits
* Deadlines - should stand out on the tickets, should be hard dates; timeboxing is another thing
* Expedite Lane - for high priority work that overrides other WIP
* Extreme Ticket Smells - use an actual banana peel that degrades with blocker age, so the ticket literally smells
* Information Fridge - data is available but hard to find; in the fridge you have to rummage around for what you want; there are often locks, restricted access
* Information Radiator - tool that makes data clear and accessible; big, obvious at a glance
* Kanban - from the Japanese "kan-ban," literally "signal card," Kanban tickets should be stickes on a board; not prescriptive, adapts the process that your team already has (unlike Scrum, XP, and RUP); timestamp cards with "in" and "out" to track lead times; card designs should make it obvious how to prioritize, err on the side of simplicity; blocked tickets should be clearly visible, consider separate blocker stickies over top of the blocked tickets, add info about why it is blocked, call out how long the ticket has been blocked for; typical colour scheme is green for maintenance (paying down technical debt / escalating risk), yellow for feature work (improving service), red for bugs (ensuring quality); consider drawing progress bars; emoji / emoticon for each ticket can be a useful metric (per user, per day?)
* Kanban Core Practices - visualize, limit WIP, manage flow, make processes explicit, use feedback, evolve experimentally (use models and measurements) / be Lean
* Kanban Method, The - capital-K Kanban, defined by David J. Anderson
* Kanban Principles - start where you are, pursue incremental improvement, leadership at all levels
* Kanban System - lower-case-k Kanban, visual process management; each visual aid is "a kanban"
* Ketchup Effect - nothing, nothing, nothing, then blam, everything happens at once
* Lead Time - how long it takes for a ticket to go through the entire process
* Lead Times - longer lead times means it takes longer to respond to platform changes, increases risk, drives a vicious cycle of decreasing quality
* Little's Law - cycle time = work in process / throughput; by John DC Little; cycle time aka lead time
* Mieruka - Japanese for "visualization;" many small visual guides provide transparency; bright outlines of tools show where everything is supposed to go when not being used
* Mob Programming - pioneered by Woody Zuill; temporary WIP limit of one, entire team is looking at the same task
* Penny Flipping Game - each worker flips pennies in a batch and passes along; smaller batches cause more work per individual worker but faster delivery overall
* Problem - an unrealized improvement opportunity
* Quality Software Management: Systems Thinking - Gerald Weinberg book; as much as 10% of time per parallel project is lost due to context switching
* Rational Unified Process (RUP) - alternative to Scrum, prescriptive
* Retro Meetings - can be triggered by a metric, eg. after every so many tickets get marked done
* Swim Lane - a track for work tickets to follow; eg. the expedite lane, used for high priority tickets
* T-Shirt Sizes - small, medium, large, etc. alternative to story points
* Task Flow - task journey from investigation through planning and development to delivery and customer approval; team defines their own stages
* Theory of Constraints (TOC) - process is limited by constraints, effective organizations continually identify constraints and adapt
* Throughput - how many tickets arrive in the finished state over a given timeframe
* Timeboxing - assigning a fixed period of time to spend on a ticket; it cannot fail, just spend the time and get as far as one can
* Toyota Production Systems (TPS) - not to be confused with Testing Procedure Specification
* Tracking IDs - it can make sense to put Jira ticket IDs on physical stickies; consider having a simplified workflow in Jira, fewer states
* User Story - describes a task as for whom (as a role), what (I want blah), and why (so that blah); considered an anti-pattern by some
* Work in Process (WIP) - smaller batches decreases lead time and creates slack time; balance fast flow and worker idle time; when WIP limit is too high, work sits idle; when WIP is too low, people sit idle; unfinished work is waste, including specs, merge requests, undeployed work, untested work, bugs; too much WIP causes increased context switching
* Work Items vs Tasks - task breakdown of steps like deployment and testing could be sub-ticketed or all considered one atomic "task"

# Techs

* HuBoard - Kanban board for GitHub
* Jira - Atlassian project management product; an information fridge
* Team Foundation Server (TFS) - Microsoft product with Kanban board feature, now called Azure DevOps Server

# Names Dropped

* Corey Ladas - Kanban expert, blog
* David P. Joyce - Kanban expert; It's not "the more you start, the more you finish," it's "the more you finish, the more you finish."
* Don Reinertsen - keynote at the Lean Kanban Central Europe 2012 conference
* Martine Devos - Kanban expert
* Rachel Davies - Kanban expert

# Publications

* Agile Software Development - Alistair Cockburn book; information radiators allow passers-by to answer their own questions
* Design Flaws, Hernias, and Anemic Quality - Scott Bellware article
* Hill Street Blues - Swedish 80's cop show; "one more thing: let's be careful out there"
* Implementing Lean Software Development: From Concept to Cash - Mary and Tom Poppendieck book
* Kanban: Successful Evolutionary Change for Your Technology Business - David J. Anderson book
* Lean Kanban conference
* Lean Software Development - Mary and Tom Poppendieck book
* Personal Kanban - book by Jim Benson
* Refactoring: Improving the Design of Existing Code - Kent Beck, Martin Fowler book
* The Toyota Way - book by Jeffrey Liker; Toyota is the inspiration of Kanban
