# About

[Release It! Second Edition: Design and Deploy Production-Ready Software](https://pragprog.com/book/mnee2/release-it-second-edition)
by Michael Nygard, Katharine Dvorak
published by Pragmatic Bookshelf, 2018

# Thoughts

A lot of overlap here with Lean Software Development and Building Microservices.

# Take-Aways

- Look at the trade-off between development cost and operational cost; consider that projects spend more time in operation than in development. Feature-complete is not the same as production-ready.
- Anticipate failures in production, plan for swift recovery. Bugs cannot be prevented, they must be survived. Enterprise software must be cynical and expect bad things.
- Restarting an entire infrastructure typically works but takes too long; be able to quickly identify the culprit services during an incident.
- During an outage, restoring service takes precedence over investigation; having pre-built scripts to capture forensic info (database snapshots, callstacks, etc.) is essential for postmortem analysis.
- Beware of a finally block that can also throw another exception, eg. SQLStatement.close().

# Concepts

- Chaos Engineering
- Design For Manufacturability - product design and manufacturing are not separate processes; do not "throw it over the wall"
- Design For Production - software equivalent of design for manufacturability
- Evolutionary Architecture
- High Availability Architecture for Physical Infrastructure - when load balancers were boxes that you had connect plugs to
- Ivory Tower Architect - sets far-reaching policies without knowledge of practical concerns
- Post hoc, ergo propter hoc - you touched it last
- Pragmatic Architect - concerned about how a design holds up in production, what the observed resource consumption is

# Techs

- CORBA - dead alternative to RMI
- EJB - Enterprise Java Bean; lulzy
- J2EE - Java 2 Platform, Enterprise Edition
- Java thread dumps - go to stdout which is often not captured by startup scripts, some customization may be needed to get them
- RMI - Remote Method Invocation, dangerous because calls do not time out
- Stateless Session Bean - hardly a web service
- Veritas Cluster

# Publications

# Names Dropped

# Code
