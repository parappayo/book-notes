# About

[Release It! Second Edition: Design and Deploy Production-Ready Software](https://pragprog.com/book/mnee2/release-it-second-edition)
by Michael Nygard, Katharine Dvorak
published by Pragmatic Bookshelf, 2018

# Thoughts

A lot of overlap here with Lean Software Development and Building Microservices.

# Take-Aways

* Anticipate failures in production, plan for swift recovery. Bugs cannot be prevented, they must be survived. Enterprise software must be cynical and expect bad things. Hope is not a design method. Tightly coupled and complex systems provide more opportunities (integration points) for errors to propagate. Fail-fast can be a good approach.
* Look at the trade-off between development cost and operational cost; consider that projects spend more time in operation than in development. Feature-complete is not the same as production-ready.
* The inevitable difference between an operator's mental model and the reality of how a system works creates difficult to anticipate situations where an operator's attempted remedial actions make a crisis worse. Eg. surprising control behaviour contributed to the Three Mile Island incident.
* During an outage, restoring service takes precedence over investigation; having pre-built scripts to capture forensic info (database snapshots, callstacks, etc.) is essential for postmortem analysis. Restarting an entire infrastructure typically works but takes too long; be able to quickly identify the culprit services during an incident. Pinging a status page doesn't tell you what is actually healthy.
* Slow memory leaks and disk consumption are a sludge that consumes system lifespan. Systems that fail this way may be unable to even write log errors. Caches should always be configured with a memory limit. Typically this problem doesn't manifest in the dev environment; consider tools like JMeter or Marathon to put synthetic stress on the dev systems.
* Vendor provided client API libraries may not be as well hardened as their services, may also be closed source.
* Beware of a finally block that can also throw another exception, eg. SQLStatement.close().
* TCP performance can be tuned at the OS level, eg. kernel buffers
* Put bounds on result sets, don't blindly consume an entire DB result, limit how many rows will be processed by the requester, not just on the query itself, don't overly trust your DB server

# Concepts

* Advanced Persistent Threat - if your system has the attention of a serious hacker, a breach is only a matter of time
* Anna Kournikova Trojan - famous virus
* ATG architecture - Oracle web commerce product, Art Technology Group was acquired
* Auto-Scaling - impose a financial restraintas a risk management measure; there is a lag time while new servers spin up when autoscaling; need to build in lead time
* Bogon - wandering TCP packets that arrive late and typically out of sequence; TCP TIME_WAIT state is a defense against, where recently closed ports remain unavailable until some time has elapsed
* Bot Sign - IP addresses that use a variety of different agent strings in the same short timespan; no cookies being provided
* Bulkheads - allow one sub-cluster to fail without the problematic load spreading to every node in the cluster; use circuit breakers
* Butterfly Architecture - antipattern; high integration with a central service with inputs on one side and outputs on the other
* Caches - eg. memcached, Redis; commonly used to move session data out of in-process service memory to an out-of-process in-memory store; should focus on the most expensive data, monitor hit / miss rates, and have an invalidation strategy
* Chaos Engineering
* Command Query Responsibility Segregation (QCRS) - an approach to immutable domain objects; issue command objects to represent changes in state
* Competitive Intelligence Service - will spider and fuzz your services to extract data
* Control Plane - the services that manage the configuration, provisioning, logging, and telemetry of the rest of the app; bad data at this layer can cause serious problems
* Cookies - typically track session IDs; bots often don't handle them correctly, so each individual request becomes a new session which can rapidly consume memory
* Crumple Zones - parts of the system designed to fail first, protect other parts; eg. circuit breakers, fail in a safe state
* Deep Links - can be a vulnerability; common dynamic web app attack is to rapidly request a deep link, without sending any cookies, and drop the connections immediately; this will often take down an un-hardened service
* Design For Manufacturability - product design and manufacturing are not separate processes; do not "throw it over the wall"
* Design For Production - software equivalent of design for manufacturability
* Dogpile - many services hit a shared resources at once; can be triggered by a deployment, cron job, or configuration management service pushing out a change; common blackout situation was that restoring electrical service activated many fridges, ovens, washers at once and cause a spike in demand that would take the system down again; clock skew can prevent dogpiling, backoff patterns can mitigate load pulses
* Email Campaigns - beware deep links, use landing pages; send mass emails in waves to control traffic
* Evolutionary Architecture
* Expensive Users - converted users are often more expensive to serve than the free tier; whatever your expected conversion rate is, consider testing at 3x that capacity
* Fight Club Bug - when increased front-end load causes exponential increase in back-end load
* Firewall Rules - may put a limit on TCP connection lifespan that the application layer is not aware of, leading to open connections that are non-responsive; see also: Oracle dead connection detection feature
* Fork, Run, Die - old school CGI way of handling sessions; new service instance for each request
* Guru Meditation - Amiga error message
* Handshaking / Backpressure - downstream services can tell upstream services to knock it off; also use circuit breakers and bulkheads
* High Availability Architecture for Physical Infrastructure - when load balancers were boxes that you had connect plugs to
* HotSpot Memory Management - a JVM garbage collection thing
* HTTP Request Fault - common scenarios: service accepts tcp connection, never responds; service fails to read the full request body, sending the request fails; service responds with an unrecognized response status code; service unexpectedly responds with a content type other than what was requested (often html); service response body does not match the response type (eg. says JSON but is actually binary data)
* Immutable Domain Objects - helps with concurrency; having to sync state across threads is bad; catching deadlock bugs during testing is hard
* Integration Point - where one service talks to another, each one is a potential failure; these may fail very slowly; be wary of convenient abstractions / wrappers that mask problems
* Ivory Tower Architect - sets far-reaching policies without knowledge of practical concerns
* Liskov Substitution Principle - subclasses that change a synchronous call to an async call violate this; concurrency does not compose
* Load Testing - comparing QA to prod telemetry can help identify scaling effects; common mistake to test with bell curve distributions when actual load in production follows a power law distribution
* Morris Worm - famous virus
* Navel-gazing Failure Mode - runtime environment is up, but every thread is blocked
* OSHA Guidelines For Industrial Robot Safety - detect when the system is not operating normally, apply hysteresis, limit resource consumption, build in momentum buffers
* Point-to-point Communication - does not scale; connection count explodes as node count increases; consider alternatives like UDP broadcasts, TCP multicast, pub-sub message queues; broadcasts sacrifice bandwidth efficiency, multicasts and message queues are incrementally more efficient
* Port Numbers - are 16 bit, IANA recommended range is only 16k long, from 49152 to 65535
* Post hoc, ergo propter hoc - you touched it last
* Pragmatic Architect - concerned about how a design holds up in production, what the observed resource consumption is
* Rate Limiting - can lead to unbalanced resources; provisioning more upstream services saturates downstream services
* Reddit 2016 outage - caused by conflict between manual change and automated processes; autoscaler restored a manually disabled service, which then read partial configuration data; cluster became massively scaled down and as it was restored individual services had empty caches which lead to dogpiling
* Reverse Conway Maneuver - team structure is the first draft of the software architecture
* Script Kiddies - dangerous despite the name
* Self-denial Attack - DoS from inside the house
* Service Level Agreement (SLA)
* Shared-Nothing Architecture - when services do not have common dependency services (dbs, cluster managers); the ideal for horizontal scalability, scales better at the cost of failover, eg. user session data is lost if subsequent requests need to be handled by another server, often the session data is held in a shared cache service; can sometimes be approximated by reducing fan-in at a service layer, eg. pairs of services that act as failover for each other; shared resources that cannot be avoided should be prepared to scale horizontally, and their dependent services should have failover modes for when the resource is unavailable; consider falling back on optimistic locking when a pessimistic locking service goes down
* Six Sigma - no longer enough at Facebook scale, leaves hundreds of thousands of affected users per day
* Software Crisis - demand for new software has outstripped the industry's capacity to produce it; coined in 1968 at the first NATO Software Engineering Conference
* Speculative Retry - aka auto-retry; ignoring an error from a downstream service and scheduling a retry can cause the failure to amplify
* Spiderweb Architecture - antipattern; many integration points in a chaotic web
* Square Cube Law - spider body weight increases `O(n**3)` with volume whereas leg strength increases `O(n**2)` thus limiting max size
* Steady State Load - system load when fully up may differ from when starting up
* Strain - stress produces strain; triggering a fault may stress a weak part of the system (a crack,) which causes cascading errors
* SYN/ACK Packets - when the listen queue is full, new requests fail immediately but those still in the queue may remain blocked on client-side for some long timeout
* TCP window header - limits how much data a response expects
* Unbalanced Capacities - scaling effect; when balancing provisioned resources, consider not just server / node count, but thread count as well
* URL Rewriting - can be used to track sessions
* Weak Reference - aka soft reference; refers to an object in memory that will be reaped by the garbage collector if memory becomes low

# Techs

* Akamai - content distribution network
* ARIN - arin.net - IP address registry, can help identify malicious actors
* CORBA - dead alternative to RMI
* EJB - Enterprise Java Bean; lulzy
* J2EE - Java 2 Platform, Enterprise Edition
* Java thread dumps - go to stdout which is often not captured by startup scripts, some customization may be needed to get them
* JMeter - Java web request load testing tool
* Marathon - Java test automation tool
* memcached
* Redis
* RMI - Remote Method Invocation, dangerous because calls do not time out
* robots.txt - a friendly robot will request and honor this
* Stateless Session Bean - hardly a web service
* tcpdump - tool for inspecting packet traffic
* Veritas Cluster
* Wireshark - tool for inspecting packet traffic
* Zookeeper Cluster

# Publications

* Inviting Disaster - James R. Chiles book
* Java Concurrency in Practice - Brian Goetz
* Pattern Languages of Programming Design 2 - book, RemoteAvailabilityCache
* TCP/IP Illustrated - W. Richard Stevens book
* The TCP/IP Guide - Charles M. Kozierok book

# Names Dropped

* Paul Lord - "good marketing can kill you at any time"
