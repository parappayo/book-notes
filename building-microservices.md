
# Thoughts

Building Microservices is a fantastic book and one of the best I've read. It provides a concise summary of the state of tech thought in 2015 in the form of good general advice liberally sprinkled with helpful, concrete references to important resources.

# Concepts

* "Small" = Rewrite and redeploy in 2 weeks (Jon Eaves)
* [12-Factor App](https://12factor.net/)
* Architectural Safety Measures: Timeouts, Bulkheads, Circuit Breakers
* Backends for Frontends (BFFs) - layer between FE and underlying system
* Blue/Green Deployment
* Canary Release
* CAP Theorem
* Class-Responsibility-Collaboration model
* Command-Query Responsibility Segregation (CQRS)
* Consumer-Driven Contract
* Continuous Integration (CI)
* Control Objective for Information and Related Technologies (COBIT)
* Conway's Law
* Cross-Functional Requirements
* Data Pump Service
* Event Sourcing
* Evolutionary Architecture
* Exemplars - projects that demo good practices
* Hash-Based Message Authentication Code (HMAC)
* Hexagonal Architecture (Alistair Cockburn)
* HTTP Cache-Control, ETags, Expires header
* Hypermedia as the Engine of Application State (HATEOAS)
* Hypertext Application Langauge (HAL)
* Idempotent Request - eg. request ID
* Immutable Server
* JSON Web Tokens (JWT)
* Linux Containers (LXC)
* Mean Time Between Failures (MTBF) vs Mean Time to Repair (MTTR)
* Message Hospital / Dead Letter Queue - isolate events that have failed once
* Monolith Proof of Concept, Decompose into Services
* Postel's Law / Robustness Principle
* REST API over HTTP
* Semantic Versioning
* Service Oriented Architecture
* Sidecar Services
* Single Responsibility Principle (Bob Martin)
* Strangler Application Pattern
* Strategic Goals -> Principles -> Practices
* Stub Service - mock service for test environment
* Synthetic Transaction Monitoring
* Tailored Service Templates
* Type 1 vs Type 2 Virtualization
* UI Fragment Composition
* Universal Description, Discovery, and Integration (UDDI)

## via Martin Fowler

* [Bounded Context](https://martinfowler.com/bliki/BoundedContext.html)
* [Catastrophic Failover](https://www.martinfowler.com/bliki/CatastrophicFailover.html)
* [Humane Registry](https://martinfowler.com/bliki/HumaneRegistry.html)
* [Microservies](https://www.martinfowler.com/articles/microservices.html)
* [Richardson Maturity Model](https://martinfowler.com/articles/richardsonMaturityModel.html)
* [Tolerant Reader](https://martinfowler.com/bliki/TolerantReader.html)
* Microservice Envy
* Test Doubles

## Anti-Patterns

* Anemic CRUD Service - thin datastore wrapper
* Configuration Drift - server config differs from repo
* Database Integration - services talk via DB
* Deferring performance testing until last step before deployment
* Integration Spaghetti - coupling to vendor solution
* Monolithic Gateway Service - all access through one API
* Onion Architecture - many vertical layers, hard to cut
* Overly fine-grained roles - eg. role for each resource
* PaaS trying to be too smart - their heuristic may fail for your app
* RPC disguised as local call
* Separate reporting for business metrics and system metrics
* Single Sign-on (SSO) Gateway as a single point of failure

# Techs

* Ansible (auto config tool)
* Apache Storm (analytics)
* Bouncy Castle (.NET crypto lib)
* Cassandra (column-oriented data store)
* Chef (auto config tool)
* Chocolately (package manager for Windows)
* circuit_breaker (Ruby gem)
* Codahale Metrics (JVM lib)
* Consul
* CoreOS (minimal Linux distro for Docker)
* Dapper (monitoring)
* Deis (Docker based PaaS)
* Docker (LXC with registry)
* Dropwizard (JVM microcontainer)
* Eureka
* Fabric (cli as Python funcs)
* Gluu (OpenID provider)
* Graphite (metrics aggregator)
* Hadoop (distributed processing)
* Heroku (PaaS)
* Hystrix (JVM circuit breaker lib)
* Java Remote Method Invocation (RMI)
* Jersey (REST framework)
* Jetty (embeddable http server)
* Karyon (JVM microcontainer)
* Kibana (log aggregator)
* Logstash.net (log processor)
* Memcache (db cache)
* mod_proxy (http load balancer)
* MongoDB (doc store)
* Mountebank (stub server)
* Nagios (monitoring)
* Nancy (.NET microservices)
* Neo4j (graph db)
* Ngnix (http server / load balancer)
* Okta (SAML identity provider)
* Open Source Gateway Initiative (OSGI)
* OpenAM (OpenID provider)
* Packer (OS imaging tool)
* Polly (.NET circuit breaker)
* Puppet (auto config tool)
* RabbitMQ (message broker)
* Reactive Extensions (event stream API)
* Reddis (doc store cache)
* Reimann (event server / router)
* SchemaSpy (db schema visualizer)
* Selenium Grid (parallel test runner)
* Sensu
* Serf
* Shibboleth (integrate Apache with SAML provider)
* Squid (cache proxy)
* SSH Multiplexer
* Suro (Netflix's data pipeline)
* Swagger (web API auto doc)
* Terraform (infrastructure as code)
* Thrift (remote invocation protocol)
* Vagrant (VM provisioning)
* Varnish (http caching proxy)
* Web Service Definition Language (WSDL, .NET)
* WebLogic (Oracle Java app server)
* Zipkin (monitoring)
* Zookeeper

# Books

* Agile Testing (Lisa Crispin, Janet Gregory; Addison-Wesley)
* Antifragile (Nassim Taleb)
* Challenger Launch Decision (Diane Vaughn)
* Continuous Delivery (Jez Humble, Dave Farley)
* Cryptography Engineering (Ferguson, Schneier, Kohno; Wiley)
* Domain-Driven Design (Eric Evans)
* Enterprise Integration Patterns (Addison-Wesley)
* Growing Object-Oriented Software, Guided by Tests (Freeman, Price)
* Implementing Domain-Driven Design (Vaughn Vernon)
* Information Dashboard Design: Displaying Data for At-a-Glance Monitoring (Stephen Few)
* Lightweight Systems for Realtime Monitoring (O'Reilly)
* Release It! (Michael Nygard)
* REST in Practice (O'Reilly)
* Succeeding with Agile (Mike Cohn; Addison-Wesley)
* The New Hacker's Dictionary (Eric S. Raymond; MIT Press)
* Working Effectively with Legacy Code (Michael Feathers)

# Articles

* [Challenges in Building Large-Scale Information Retrieval Systems](https://ai.google/research/pubs/pub37797) (Jeff Dean)
