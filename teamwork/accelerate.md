
# About

* [Accelerate: The Science of Lean Software and DevOps](https://itrevolution.com/book/accelerate/)
* by Nicole Forsgren, Jez Humble, Gene Kim
* published by IT Revolution, 2018

# Thoughts

A great follow-up read to Lean Software Development (Poppendieck).

# Take-Aways

* Four key software delivery performance predictors: lead time, deployment rate, MTTR, change failure rate
* Frequent deployments increase software stability; it is not a trade-off
* Grow Agile from the bottom-up; each team controls its own process
* Outcome-based teams focus on measurement, data-driven decisions
* Measure capabilities (the key performance predictors), not outputs; measuring outputs encourages busy-work
* Choosing the right metrics is key; many paths lead to success, many more lead to failure
* Consider that banks no longer deliver value by securely storing gold, but by providing fast, secure trades and engaging customers
* Maturity model is not the right mindset to have, DevOps is not a linear process
* Often-cited performance predictors that do not matter: age of technology stack, CAB, whether dev teams or ops teams perform deployments, greenfield vs. brownfield
* Attempts to increase tempo without building the supporting process lead to higher failure rates and slower progress
* Many efforts to measure software team performance focus on productivity as outputs (metrics) rather than outcomes (results) and focus on individual load rather than team or organization performance (aggregate upwards)
* In pathological and bureaucratic organizations measurement is used as a form of control, and people hide information that challenges existing rules, strategies, and power structures
* organizational culture exists at 3 levels: basic assumptions, values, and artifacts, from least visible to most visible (Schein, 1985)
* who is on a team matters less than how the team interacts - Google 2015 study
* Low performers are more likely to be working with an outsourcing partner or on a mainframe system (perhaps these are cases where coupling is tighter); other kinds of project like greenfield vs brownfield, or front-end vs back-end, do not affect software delivery performance
* Key factors are being able to test without an integrated environment (without deploying to a staging environment), and being able to release independently of other services; many so-called service oriented architectures neglect these factors
* Low performing orgs deploy less often as the number of devs increases; high performing orgs deploy much more often as the number of devs increases
* Architects should collaborate closely with dev teams; they focus on people and outcomes, not tech stacks
* remediating security issues after delivery tends to be more expensive than building security in

# Concepts

* [GitHub Flow](https://guides.github.com/introduction/flow/) - a git workflow that discourages trunk-based development, notably merge happens after deploy
* Architecture Capabilities - loosely coupled architecture, empowered teams
* Big Ball of Mud Enterprise Architecture - many tightly coupled systems; a big challenge to DevOps
* Bureaucratic Org - rule-oriented, modest cooperation, messengers ignored, narrow responsibilities, failure leads to justice, novelty is disruptive
* CAMS - culture, automation, measurement, sharing; a model for DevOps
* Change Advisory Board (CAB) - approves system changes and assists in prioritizing work
* Cluster Analysis - data analysis technique that groups responses so that responses in the same group are more similar to each other than responses in other groups
* Continuous Delivery - the practice of rapid software delivery; supported by building quality in, working in small batches, configuration management, trunk-based development, good test coverage, loosely coupled architecture; reduces deployment pain, improves IC quality of life, improves loyalty, improves trust
* Continuous Delivery Capabilities - CI/CD, trunk-based development, test data management, shift left on security
* Convergent Validity - checking that expected related items are shown to be related
* Cultural Capabilities - generative culture, job satisfaction, transformational leadership
* DevSecOps - coined by Topo Pal, Shannon Lietz; arguably DevOps is poorly named, because what about infosec, management, etc.
* Discriminant Validity - checking that expected unrelated items are shown to be unrelated
* Employee Net Promoter Score (eNPS) - would you recommend working here
* Extreme Programming (XP) - popular Agile framework when the Agile Manifesto was published in 2001; prescribes practices including CI and TDD; Scrum overtook Extreme Programming in 2006 according to Google Trends
* Faux Agile - long requirements gathering phase, large batches of work, customer feedback deferred
* Federal Information Security Act 2002 (FISMA)
* Feedback from Production - make monitoring data available and use it in planning
* Fuzzy Front-End of Lead Time - coined by Reinertsen; difficult to start the clock on lead time since customer requirements and design changes continue while development is under way; focus on the time it takes to develop, test, and deliver; Product Delivery has less variability than Product Development
* Generative Org - performance-oriented, high cooperation, messengers trained, shared risks, failure leads to inquiry, novelty is adopted
* Greenfield Project - a new system not yet released
* Lean Management and Monitoring Capabilities - monitoring, WIP limits, visualizing work
* Lightweight Change Approvals - make it easy to approve work; approval by an external body increases lead time, reduces deployment frequency, and increases time to recover from failure, but does not lower failure rate
* Likert Questions - rating "agree" or "disagree" on a 5 point scale
* Maturity Model - scale indicating transformational progress; tends to encourage linear, prescriptive thinking and tools adoption
* NFR - non-functional requirement; a requirement of the system architecture rather than the system design (eg. not a feature)
* OWASP Top 10 - hopefully you already know what this is
* Pathological Org - power-oriented, low cooperation, messengers shot, responsibilities shirked, failure leads to scapegoating, novelty is crushed
* PRINCE2 - management framework
* Product and Process Capabilities - customer feedback, value streams, working in small batches
* Project Management Institute - management framework
* Reverse Conway Maneuver - structure your org to match the system architecture that you want
* Risk Management Framework (RMF) - process for validating software security, often takes a long time
* Rugged DevOps - introduces the Rugged Manifesto; choose for your software to not be a source of vulnerability or weakness; Corman, 2012
* Security Assessment Report (SAR)
* Shift Left - build it into the software delivery process rather than making it a post-delivery phase
* Small Batch Sizes - enables shorter lead time, reduces risk; a key part of the Toyota production paradigm
* Snowball Sampling - growing your sample population by encouraging participants to invite their friends, colleagues, peers
* Survey Reliability - checking that respondents share their interpretation of the survey questions
* Systems of Engagement - interacted with directly by end-users
* Systems of Record - where data consistency and integrity is crucial
* Utilization - sometimes used as a proxy metric for performance; Queue Theory says that as utilization approaches 100%, lead times approach infinity
* Vanguard Method - created by John Seddon
* Velocity - Agile metric as story points over time; meant for capacity planning, but mistakenly used to gauge performance; relative measure, not an absolute one, is easily gamed
* Wall of Confusion - dev throws poor quality code over the wall to ops, and in response ops puts painful change management practices in place to inhibit change
* Westrum Typology of Organizations - orgs categorized on a spectrum from Pathelogical (power-oriented), through Bureaucratic (rules-oriented), to Generateive (mission-oriented)
* Work in Progress (WIP) - limiting this alone does not predict success; must be combined with visual displays and monitoring feedback loop from production

# Techs

* Cloud Foundry - by Pivotal
* cloud.gov - cloud platform based on Cloud Foundry with many FISMA security controls built-in; reduces time to deliver on security sensitive services
* Puppet - automation and delivery company

# Names Dropped

* Bill Atkinson - wrote "-2000 lines" as his weekly lines of code output ([Andy Hertzfield story](http://www.folklore.org/StoryView.py?project=Macintosh&story=Negative_2000_Lines_Of_Code.txt))
* Courtney Kissler - VP Digital Platform Engineering, Nike
* James Bessen - Boston University study found that strategic tech predicts revenue more than mergers and acquisitions or entrepreneurship
* Jerry Weinberg - quality is value to some person
* Martin Fowler - Chief Scientist, ThoughtWorks
* Ron Westrum - conducted research on human factors in the safety of complex technical systems such as aviation and healthcare
* Steve Yegge - Amazon's move to service oriented architecture required a standardized way to debug every service in a dev environment
* W. Edwards Deming - "Whenever there is fear, you will get wrong figures."

# Publications

* [A Typology of Organisational Cultures](https://qualitysafety.bmj.com/content/13/suppl_2/ii22) - Westrum
* [Choose Boring Technology](http://boringtechnology.club/ https://mcfunley.com/choose-boring-technology) - Dan McKinley; "how to be old, for young people" - Scott Ananian
* [Steve Yegge's Platforms Rant](https://gist.github.com/jezhumble/a8b3cbb4ea20139582fa8ffc9d791fb2)
* DevOps Enterprise IT Summit 2014 presentation - optimize for speed rather than cost
* Forrester Report - 31% of the industry are not using practices like CI/CD; orgs tend to overestimate their progress in DevOps transformation
* Gartner Study - 47% of CEOs face pressure to digitally transform their org
* Lean Software Development - Poppendieck book series
* State of DevOps Report - annual report published by Puppet; correlated IT performance to business outcomes; shows that Lean methodology works
* The Art of Business Value - Mark Schwartz; the goal of bureaucracy is to provide fairness and eliminate arbitrary decisions
* The Visible Ops Handbook - the difference between planned and unplanned work is paying attention to the low fuel indicator versus running out of gas on the freeway
* This American Life episode 561 - about lean manufacturing transformation, Toyota methodology
