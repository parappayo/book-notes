
# About

* [Release It! Second Edition: Design and Deploy Production-Ready Software](https://pragprog.com/book/mnee2/release-it-second-edition)
* by Michael Nygard, Katharine Dvorak
* published by Pragmatic Bookshelf, 2018

# Thoughts

Some of the best stuff that you will ever read about operations concerns. Condenses a wealth of experience into anecdotes, recommendations, and practices. A good companion to Building Microservices.

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
* Well-placed timeouts provide fault isolation; commercial software client libs may lack sensible timeouts
* Dedicated pool of threads for admin requests can help a host be responsive to manual recovery
* Keep people off of the production servers to the greatest extent possible (see Immutable Infrastructure); servers (hosts, containers) are cattle, not pets
* Developer boxes are dirty, should never deploy to production from them
* On a typical Unix host, only root can consume the last 5% of disk space; typical Windows, any app can
* General exception handler that tries to log every exception to disk may cause a stack overflow when the exception is that no disk is available
* Best to purge old data using application logic rather than system level scripts; hard for sys admins to know how an app will be affected by data deletions
* Integration test environment creates the issue of what version(s) services test each other against; also how to simulate other services behaving badly
* Most businesses organize around their own calendar; eg. shopping cycle for retail, enrollment cycle for education
* Having a separate resource pool to manage outgoing connections to a particular service creates a safety breaker; can disable the pool if those connections are swamping a downstream service
* During an outage, there may not be time to add app logging; good visibility negates the need for thorough logging
* Common ops problem is when machine deployment state depends on the order of deployments and is not reproduced simply by deploying latest on a fresh slate
* Strategies for handling too much load are to refuse work or scale out
* Touting on hosts with multiple NICs can get confused and think that multiple routes are plausible including some that will fail; worst case, packets containing PII would intermittently be sent over the public internet when the intended route was over VPN; consider that a BIOS tweak could change what device ends up being eth0 even on identical hardware	

# Concepts

* 12-Factor App - Heroku principles for cloud-native; Codebase, Dependencies, Config, Backing Services, Build-Release-Run, Processes, Port Binding, Concurrency, Disposability, Dev-Prod Parity, Logs, Admin Processes
* Advanced Persistent Threat - if your system has the attention of a serious hacker, a breach is only a matter of time
* Anna Kournikova Trojan - famous virus
* ATG architecture - Oracle web commerce product, Art Technology Group was acquired
* Audit Trail - needed from source to production; need to secure against malicious code or config getting into production
* Auto-Scaling - impose a financial restraintas a risk management measure; there is a lag time while new servers spin up when autoscaling; need to build in lead time
* Back Pressure - response informs requester to cease further requests; could also be blocked threads (careful with that), works best within a system boundary
* Black-Box Observability - tools that monitor a service from outside the process
* Bogon - wandering TCP packets that arrive late and typically out of sequence; TCP TIME_WAIT state is a defense against, where recently closed ports remain unavailable until some time has elapsed
* Bonded Interface - two host network interfaces with a common IP address, aka teaming; when they connect to separate switches, it's easy to create a routing loop
* Botsign - IP addresses that use a variety of different agent strings in the same short timespan; no cookies being provided
* Build Pipeline - turns sources into builds ("executables")
* Bulkheads - allow one sub-cluster to fail without the problematic load spreading to every node in the cluster; use circuit breakers; maintains partial service during an outage; running services across regions in AWS is a bulkheads strategy; resource pools can act as bulkheads (component hogging resources will not starve others)
* Butterfly Architecture - antipattern; high integration with a central service with inputs on one side and outputs on the other
* Cache Hit Rate - useful metric
* Caches - eg. memcached, Redis; commonly used to move session data out of in-process service memory to an out-of-process in-memory store; should focus on the most expensive data, monitor hit / miss rates, and have an invalidation strategy
* Chaos Engineering
* Circuit Breaker - should log state changes, provide a manual reset control; consider whether state should be independent per process, not shared, otherwise introduces failure mode where one circuit breaker goes down, system goes with it; beware of integration point pain; beware rolling your own, non-blocking is tricky
* Circuit Breaker Half-open - when an open circuit breaker (rejects all requests immediately) enters the half-open state, it attempts the next request to see if recovery is possible, and if that request succeeds then it goes to the closed state (normal operation)
* Clock Skew - system clock on a VM can jump around unexpectedly; communication with the host OS clock is unpredictable, it may make more sense to rely on an external NTP server
* Code, Configuration, Connections - services need these to do work; audit the entire process from code check-in through deployment; keep records of all remote connections with destination name, address, desired route
* Command Query Responsibility Segregation (QCRS) - an approach to immutable domain objects; issue command objects to represent changes in state
* Competitive Intelligence Service - will spider and fuzz your services to extract data
* Configuration - hidden dependencies, high complexity, likely source of manual error; should be revision controlled, auditable, but kept separate from the code; passwords tend to get accidentally committed to revision control
* Configuration Service - queried by services on start to retrieve their configuration; must be highly available, can become a massive point of failure; injected config is typically safer
* Containers - need configuration to be injected at start-up time, such as connection strings
* Content Aware Load Balancing - service looks at the request body to help efficiently partition the work
* Control Plane - the services that manage the configuration, provisioning, logging, and telemetry of the rest of the app; bad data at this layer can cause serious problems
* Cookies - typically track session IDs; bots often don't handle them correctly, so each individual request becomes a new session which can rapidly consume memory
* Crumple Zones - parts of the system designed to fail first, protect other parts; eg. circuit breakers, fail in a safe state
* Data Centers - use many cheap hosts; huge shift from past eras when server hardware was much more powerful than dev workstations
* Data Purging - thankless, detail-oriented work
* Deep Links - can be a vulnerability; common dynamic web app attack is to rapidly request a deep link, without sending any cookies, and drop the connections immediately; this will often take down an un-hardened service
* Delayed Retires - an immediate retry is likely to fail again; be aware that a long request can trigger downstream timeouts
* Deployment Pipeline - turns builds plus configuration into deployments or installations
* Design For Manufacturability - product design and manufacturing are not separate processes; do not "throw it over the wall"
* Design for Production - production concerns are first-class, eg. network environment, monitoring, runtime control (selective component restarts), security, operability (ops team are users too)
* Design For Production - software equivalent of design for manufacturability
* DNS - services may find each other by configured host names; "discovery" is typically from talking to people; avoid hosting DNS servers on the same infrastructure as your production system
* DNS Round-Robin Load Balancing - one of the oldest methods; DNS server cycles between IP addresses from a pool, but those IP addresses must be routable from callers which means clients can reach out directly (some services cache IPs); no guarantee of balanced load, only balanced connection attempts; inappropriate for enterprise
* Dogpile - many services hit a shared resources at once; can be triggered by a deployment, cron job, or configuration management service pushing out a change; common blackout situation was that restoring electrical service activated many fridges, ovens, washers at once and cause a spike in demand that would take the system down again; clock skew can prevent dogpiling, backoff patterns can mitigate load pulses
* Dynamo Request Protocol (DRP)
* EC2 User Data - blob of text, user-defined config
* Email Campaigns - beware deep links, use landing pages; send mass emails in waves to control traffic
* Evolutionary Architecture
* Exceptions - not necessarily an actionable error, may not want to make these "error" level logs by default
* Executable - build artifacts that a host can launch as a process
* Expensive Users - converted users are often more expensive to serve than the free tier; whatever your expected conversion rate is, consider testing at 3x that capacity
* Failure Density - matters more than failure count
* Fight Club Bug - when increased front-end load causes exponential increase in back-end load
* Firewall Rules - may put a limit on TCP connection lifespan that the application layer is not aware of, leading to open connections that are non-responsive; see also: Oracle dead connection detection feature
* Fork, Run, Die - old school CGI way of handling sessions; new service instance for each request
* Fully Qualified Domain Name (FQDN) - hostname plus the search domain
* Global Server Load Balancing (GSLB) - routes requests by region, DNS is good for this
* Going Nonlinear - when a limited resource (eg. sockets) becomes increasingly more scarce under load (eg. request service time going up)
* Governor - safety limits pattern, an engine governor stops the engine from revving itself apart; must be stateful and time-aware, adds resistance to the system to keep measures within reason, buys time for human intervention to mitigate potential damage
* Guest OS - the OS that runs inside the virtual machine; as opposed to Host OS; the host machine is typically oversubscribed and the guest OS cannot typically monitor for resource contention from other VMs on the same host
* Guru Meditation - Amiga error message
* Handshaking / Backpressure - downstream services can tell upstream services to knock it off; also use circuit breakers and bulkheads
* Hardware Load Balancer - better capacity and throughput than app layer load balancers; application-aware and can load balance any connection-oriented protocol; useful for fail-over; typically expensive
* Health Check - typically an API endpoint that provides summary stats about a system's self-perceived health; should report at least the host IP address, runtime environment version, app version / commit ID, whether or not the API is accepting work, status of any connection pools, caches, and circuit breakers
* High Availability Architecture for Physical Infrastructure - when load balancers were boxes that you had connect plugs to
* Hostname - OS level name, but also used to refer to the DNS name; the OS hostname and DNS hostname are not guaranteed to match; the mapping from DNS name to IP address is many-to-many, but many system tools assume that the machine's self-assigned FQDN is a legitimate DNS name that resolves back to itself
* HotSpot Memory Management - a JVM garbage collection thing
* HTTP - not great at handshaking; many clients only recognize a handful of response codes
* HTTP Request Fault - common scenarios: service accepts tcp connection, never responds; service fails to read the full request body, sending the request fails; service responds with an unrecognized response status code; service unexpectedly responds with a content type other than what was requested (often html); service response body does not match the response type (eg. says JSON but is actually binary data)
* Immutable Domain Objects - helps with concurrency; having to sync state across threads is bad; catching deadlock bugs during testing is hard
* Immutable Infrastructure - hosts do not change once deployed; a new deployment version requires building a new machine image
* Installation - deployed build artifacts and accompanying configuration; I'd also call this a "deployment"
* Instance - installation on a single host out of a load-balanced array of the same executable
* Integration Point - where one service talks to another, each one is a potential failure; these may fail very slowly; be wary of convenient abstractions / wrappers that mask problems
* Interconnect layer - a process running on a desert island doesn't matter; at this layer we create availability; includes traffic management, load balancing, discoverability
* Ivory Tower Architect - sets far-reaching policies without knowledge of practical concerns
* JMX Notifications - Java Management Extensions; notifications are signals from beans
* Julian Calendar - has an accumulating drift flaw
* Layers Of Responsibility - operations (availability, status), control plane (monitoring, deployment, feature flags), interconnect (traffic management, failover), instances (services, processes, instance health), foundation (hardware, IP addresses, physical network)
* Least Recently Used (LRU) - cache invalidation algorithm
* Liskov Substitution Principle - subclasses that change a synchronous call to an async call violate this; concurrency does not compose
* Listen Queue Purge - script that quickly accepts connections and sends "503 Try Again\r\n\r\n"
* Little's Law - from queue theory, count of active requests = throughput * response time; queues must have size limits, or response times will be unbounded
* Load Balancer - if the client can tell that it's talking to a load balancer, that's typically a problem
* Load Shedding - ditching work to mitigate high load; a quick rejection is often better than a slow timeout; best place to do this is close to the network edge, return HTTP 503
* Load Testing - comparing QA to prod telemetry can help identify scaling effects; common mistake to test with bell curve distributions when actual load in production follows a power law distribution
* Log Files - sludge; one log file is like dung, many logs are like fertilizer; typically bad signal-to-noise ratio; where needed for audit purposes, best to get them out of prod and into tamper-proof storage promptly
* Logs - still the most versatile, reliable channel for metrics; should be human-readable, friendly, informative; typically abused; state transitions should be logged; containers often emit them to stdout; symlinks often used to redirect log location; debug level logging in prod is usually a bad idea
* Message Brokers - better implemented with silicon than carbon, nitrogen, and oxygen
* Middleware - aka Enterprise Application Integration; the unfortunate class of software that integrates two systems that were probably never meant to talk to each other; good middleware reduces coupling and introduces error handling, bad middleware increases coupling, integration points, and failure modes
* Mise en Place - chef best practice, gather all ingredients before starting; this is also a good services practice, fail immediately if any one resource is unavailable rather than waiting on a timeout
* Mock Objects - provide test cases that conform to the interface that they implement; test harnesses can violate the interface spec
* Monitoring Dashboards - team members ideally intuit normal operation metrics and can spot anomalies; monitoring dashboards are great when you don't know what you're looking for, but tedious when you know exactly what stat you need
* Morris Worm - famous virus
* Multihoming - a host often has IP addresses (each an NIC) on different networks at the same time, may be used to separate admin and monitoring connections
* Navel-gazing Failure Mode - runtime environment is up, but every thread is blocked
* Network Interface Controller (NIC) - what you see with ifconfig (Linux) or ipconfig (Windows); loopback NIC is the localhost virtual device, others may be attached to physical hardware (WiFi, Ethernet, etc.); the default for socket libs is often to open a socket on all host interfaces unless a specific one is given
* OSHA Guidelines For Industrial Robot Safety - detect when the system is not operating normally, apply hysteresis, limit resource consumption, build in momentum buffers
* OSI Model - good test harness will simulate failures at every level that it can
* Overlay Network - pattern where containers get their own VLAN
* PaaS - open-source PaaS tools are on the upswing; monitoring used to be considered a big team thing, but now no team is too small for it
* Package Repository - dependency packages should be serviced from a private, secure repository to help prevent security breaches in the wild from making it into prod
* Paranoia - aka good engineering
* Persnickety - lol
* Personally Identifying Information (PII) - when this goes public, bad stuff happens
* Point-to-point Communication - does not scale; connection count explodes as node count increases; consider alternatives like UDP broadcasts, TCP multicast, pub-sub message queues; broadcasts sacrifice bandwidth efficiency, multicasts and message queues are incrementally more efficient
* Port Numbers - are 16 bit, IANA recommended range is only 16k long, from 49152 to 65535
* Post hoc, ergo propter hoc - you touched it last
* Pragmatic Architect - concerned about how a design holds up in production, what the observed resource consumption is
* Process - runtime image of an executable, hosted by an OS
* Process Binding - by forcing a process to run on only one cpu core, it will not take down the entire host if it blocks the cpu
* Proxy Server - application layer multiplexer for IPs; many outgoing calls get mapped to a single IP address
* Query Object - domain object that holds query params; can be used to do parameter validation before bothering the db resource
* Queues - every failing system starts with a queue backing up somewhere; rough heuristic for queue length: `((max(wait_time) / avg(processing_time)) + 1) * count(request_processing_threads) * 1.5`
* Rate Limiting - can lead to unbalanced resources; provisioning more upstream services saturates downstream services
* Recovery-Oriented Computing (ROC) - joint research project at Berkeley and Stanford around 2005; accepts system failures as inevitable and focuses on smooth recovery; over-turns previous mindset of trying to identify and prevent sources of failure
* Reddit 2016 outage - caused by conflict between manual change and automated processes; autoscaler restored a manually disabled service, which then read partial configuration data; cluster became massively scaled down and as it was restored individual services had empty caches which lead to dogpiling
* Requests per Second - limited by the number of sockets available, NIC I/O bandwidth, buffer memory size
* Residence Time - total time that a request spends in a listen queue and in processing; common mistake is to only monitor the processing time
* Response Time - only measured on responses that complete; responses that never come back are effectively infinite and don't appear in this stat
* Reverse Conway Maneuver - team structure is the first draft of the software architecture
* Reverse Proxy Server - application layer demultiplexer for requests; calls coming in on a single IP address fan out to multiple IPs; should add the X-Forwarded-For header; may be configurable to cache responses; can be a bottleneck, may need load balancing in front of this (hardware load balancer)
* SAN vs NAS Religious War - what is the right paradigm for mass storage?
* Script Kiddies - dangerous despite the name
* Self-denial Attack - DoS from inside the house
* Server - loaded term, easily confused; could mean a physical host, virtual machine, container, service process; does "reboot the server" mean cycle the hardware or just restart a process?
* Service - collection of processes that deliver a unit of functionality; these processes are not necessarily all on the same host, the same binary executable, or the same IP address
* Service Discovery - instances of a service announce themselves to receive traffic and services can find each other; Container-based environments typically require this; the service discovery service itself becomes a failure point
* Service Level Agreement (SLA)
* Session Stickiness - load balancer stickiness trades less even balancing for better cache performance; requests are often grouped by stored token (cookie) or source IP address (outbound proxy such as AOL can break this)
* Shared-Nothing Architecture - when services do not have common dependency services (dbs, cluster managers); the ideal for horizontal scalability, scales better at the cost of failover, eg. user session data is lost if subsequent requests need to be handled by another server, often the session data is held in a shared cache service; can sometimes be approximated by reducing fan-in at a service layer, eg. pairs of services that act as failover for each other; shared resources that cannot be avoided should be prepared to scale horizontally, and their dependent services should have failover modes for when the resource is unavailable; consider falling back on optimistic locking when a pessimistic locking service goes down
* Shed Load - throw 503 quickly rather than accepting a connection slowly, load balancers can act as shock absorbers, the web is too vast to be able to scale for the whole thing
* Site Operations Center (SOC) - where the ops team lives
* Six Months - standard management estimate; probably as far in the future as can be reasonably imagined
* Six Sigma - no longer enough at Facebook scale, leaves hundreds of thousands of affected users per day
* SNMP Traps - Simple Network Management Protocol; traps send alert messages from a remote device to a central controller
* Sockets - apps that listen on sockets need to provide options to configure what network interface those sockets listen on
* Software Crisis - demand for new software has outstripped the industry's capacity to produce it; coined in 1968 at the first NATO Software Engineering Conference
* Spectrum Of Coupling - from same time, same host, same process to different time, different host, different process - in-process method calls, interprocess communication, remote procedure calls, message bus, tuple spaces
* Speculative Retry - aka auto-retry; ignoring an error from a downstream service and scheduling a retry can cause the failure to amplify
* Spiderweb Architecture - antipattern; many integration points in a chaotic web
* Square Cube Law - spider body weight increases `O(n**3)` with volume whereas leg strength increases `O(n**2)` thus limiting max size
* Steady State Load - system load when fully up may differ from when starting up
* Strain - stress produces strain; triggering a fault may stress a weak part of the system (a crack,) which causes cascading errors
* Superstitions - admins and ops often progress from observation to analysis to hypothesis to action very quickly and accept the result if it seemed to work without further scrutiny
* SYN/ACK Packets - when the listen queue is full, new requests fail immediately but those still in the queue may remain blocked on client-side for some long timeout
* TCP window header - limits how much data a response expects
* Test Harness - stand-alone app that integrates with your system and intentionally behaves badly to tease out problems; eg. responds to requests too slowly, or with random garbage data, or sends TCP packets out of order; tends not to be devious enough
* Thread Dumps - snapshot of what various threads on a hosts are doing; useful if many are stuck on the same spot
* Transparency - aka observability, metrics; allows operators to gain a sense of the system in production; needs to be designed in from the beginning, not added later; without service-level metrics you may know that your system is slow but have no insight into why; helps systems mature, enables optimizations and rational architectural decisions
* Two Weeks - standard dev estimate; probably as far in the future as can be reasonably imagined
* Unbalanced Capacities - scaling effect; when balancing provisioned resources, consider not just server / node count, but thread count as well
* URL Rewriting - can be used to track sessions
* Virtual Extensible Local Area Network (VXLAN) - like a VLAN but in layer 3; visible to IP on the host, uses 24 more bits in the IP header
* Virtual IP Address - overloaded term, generally an IP not tied to an Ethernet MAC address (load balancer context); cluster servers use it to migrate addresses between hosts, load balancers use it to multiplex services onto hosts; don't confuse "service address" with "migrating address" (cluster context); some JDBC / ODBC drivers can retry in case of a failover (db host IP switch) but assume that uncommitted transactions may be lost
* Virtual Local Area Network (VLAN) - multiplexes Ethernet frames on a single wire while allowing the switch to treat them like they came from different networks
* Weak Reference - aka soft reference; refers to an object in memory that will be reaped by the garbage collector if memory becomes low
* White-Box Observability - tools that emit metrics from inside the process
* Working Set - cache invalidation algorithm

# Techs

* Akamai - reverse proxy server cluster, content distribution network (CDN)
* Akka - Actor lib for Java
* Ansible - infrastructure and deployment tool
* Apache httpd - good option for reverse proxy load balancer
* ARIN - arin.net - IP address registry, can help identify malicious actors
* Bonnie 64 - disk benchmark tool
* Chef - infrastructure and deployment tool
* Consul - by HashiCorp, "AP" from CAP theorem, can build service discovery / dynamic discovery service; worth the cost if many teams need to coordinate rapid changes; direct DNS may work for small teams, but IP addresses change rapidly with containers
* CORBA - dead alternative to RMI
* Datadog - metrics and monitoring
* Docker Swarm - container control plane, can provide service discovery
* EIA-232C - formerly RS-232, serial protocol
* EJB - Enterprise Java Bean; lulzy
* Erlang - "let it crash" philosophy; actor model, an actor can be taken down without crashing the whole system
* etcd - often used as a configuration service, can build service discovery
* HAProxy - good option for reverse proxy load balancer
* Heroku - config is typically environment vars
* IBM MQseries - a pub-sub message bus
* J2EE - Java 2 Platform, Enterprise Edition
* Java thread dumps - go to stdout which is often not captured by startup scripts, some customization may be needed to get them
* JMeter - Java web request load testing tool
* Kubernetes - container control plane
* logrotate - Unix tool
* Logstash - centralized log server
* Marathon - Java test automation tool
* memcached
* Mesos - container control plane
* Nagios - an older monitoring system that expect to be reconfigured every time a host is added or removed, doesn't play well with containers
* Netflix - a monitoring system that streams movies as a side effect
* New Relic - metrics and monitoring
* nginx - good option for reverse proxy load balancer
* PDQ Analyzer Toolkit - by Dr. Neil Gunther
* Puppet - infrastructure and deployment tool
* Redis
* RMI - Remote Method Invocation, dangerous because calls do not time out
* robots.txt - a friendly robot will request and honor this
* Sarbanes-Oxley Act of 2002 (SOX) - requires adequate controls on any system that deals with financial data
* SiteScope - synthetic customer traffic, tells you if actual users can see the site
* Spinnaker
* Squid - good option for reverse proxy load balancer
* Stateless Session Bean - hardly a web service
* tcpdump - tool for inspecting packet traffic
* Varnish - http reverse proxy cache
* Veritas Cluster
* Wireshark - tool for inspecting packet traffic
* WS-I Basic - http protocol
* XML-RPC - lol
* ZooKeeper - by Apache, "CP" from CAP theorem, often a configuration service, can build service discovery; scalable but not elastic

# Publications

* Inviting Disaster - James R. Chiles book
* Java Concurrency in Practice - Brian Goetz
* Pattern Languages of Program Design 2 - book, RemoteAvailabilityCache, Leaky Bucket pattern
* Patterns of Enterprise Application Software - book; talks about query objects
* TCP/IP Illustrated - W. Richard Stevens book
* The TCP/IP Guide - Charles M. Kozierok book
* theagileadmin.com
* Why People Believe Weird Things - Michael Shermer

# Names Dropped

* Aloysius Lilius - inventor of the Gregorian calendar
* Paul Lord - "good marketing can kill you at any time"
