
# About

* Domain-Driven Design Distilled
* by Vaughn Vernon
* published by Addison-Wesley, 2016

# Thoughts

Quick and dense introduction to DDD.

# Take-Aways

* DDD models the core domain of the business, focuses software projects on solving the right problem; the business can't excel at everything, must decide what has the most value
* Software projects should be considered a profit center rather than a cost center; lack of collaboration leads businesses departments to see tech as a nuisance
* Using the wrong abstraction is worse than not having an abstraction
* Strong coupling leads to modules that are difficult to change

# Concepts

* Acceptance Tests - validation tests written in ubiquitous language; should be more readable than unit tests
* Aggregate - cluster of closely related entities and value objects that live within a bounded context; comprised of multiple entities, one of which is the aggregate root
* Aggregate Right-Sizing - design steps: start with one root entity per aggregate, add properties and transactions, apply business invariant rules (which other entities need to be updated in the same transaction), consider how much eventual consistency delay is acceptable (for entities that need immediate updates, they may need to belong to the same aggregate); beware too much data modeling thinking that leads to large transactions
* Aggregate Rules - protect business invariants inside each aggregate, design small aggregates, reference other aggregates by ID only, update other aggregates using eventual consistency
* Anemic Domain Model - when aggregates primarily have getters and setters but don't capture significant business logic; can result from an overly technical focus during modeling; can surface as anemic CRUD services; beware delegating business rules from services to helper / utility / common libs; note functional programming stresses the separation between data and behaviour, can resemble anemic domain model, consider Functional Domain Modeling
* Anticorruption Layer - context mapping where inputs are translated from the domain of the supplier into the domain of the consumer, isolates the bounded context; use where possible, but beware cost
* At Least Once Delivery - unacknowledged messages will periodically retry
* Behaviour-Driven Development (BDD) - method for collaboration between technical and non-technical stakeholders, defines requirements
* Big Ball of Mud - monolithic implementation where the context is too large, lacks explicit boundaries; often the result of over-keen developers who started on the implementation without consulting the business experts; characterized by unwarranted connections and dependencies; system collapse is only avoided through heroics, tribal knowledge, speaking all domain languages at once
* Bounded Context - semantic contextual boundary, "what is the core?"; each component inside is specific to the context; each bounded context should have its own ubiquitous language, team, code repo, data schema, etc.; bounded contexts only interact with each other through their official interfaces
* Business Logic - should never be found in UI or persistence modules
* Command Query Responsibility Segregation (CQRS) - architecture pattern
* Conformist - context mapping where the supplier is unresponsive and the customer has no option but to conform; eg. large API provider that becomes a defacto standard
* Context Mapping - a relationship or integration between two subdomains
* Core Domain - key strategic initiative of your organization; the competitive advantage, what you excel at; primary value proposition of DDD is to identify it
* Customer-Supplier - context mapping with upstream and downstream subdomains; the upstream teams (suppliers) produce work used by the downstream teams (customers)
* Data Modeling - often the primary method used to design solutions, should not come at the expense of modeling the business domain; tends to focus on defining transactions and having immediate consistency among aggregates; making transactions larger increases the rate at which they will fail and increases memory overhead
* DDD Police - nobody is enforcing the "rules" of DDD
* Domain Expert - concerned with business problems, not with tools and solutions
* Domain Model - should be free of coupling to specific technologies; Application Services adapters are used to define what dependencies your app has
* Effective Design - meets the needs of the business; design is how it works, not just how it looks (Steve Jobs)
* Enrichment vs Query-Back - trade-off: enriched event data is convenient for consumers, but may compromise security; it is difficult to predict what data downstream services will actually care about
* Entity - models an individual thing with a unique ID, may have mutable state
* Eventual Consistency - state changes are pushed out to other aggregates by publishing events as messages
* Generic Subdomain - common business problem for which there may be off-the-shelf software
* Given-When-Then - pattern for unit tests
* Idempotent Receiver - duplicate message delivery is handled safely
* Knowledge Acquisition - in Scrum, employs experimentation and collective learning
* Logical Subdomain - when you reason about a system as being broken up into components even though in practice it is not
* Maintenance Phase - worst thing that can happen is for this term to be applied to the Core Domain; continuous learning is not a phase, rather improvement is always happening; if your org is not committed to the core domain, it is not correctly chosen
* Microservice - arguably should be smaller than a bounded context
* No Design - false economy, yields low quality software; skipping design step leads to bad design
* Open Host Service - context mapping that provides access to the domain as a set of well-defined services (open protocol, API)
* Partnership - context mapping between subdomains where the teams succeed or fail together, must align on objectives; requires heavy commitment and unlikely to be permanent
* Ports and Adapters Architecture - layers of adapters that form the implementation of a bounded context; includes Input Adapters (eg. REST API), Output Adapters (eg. persistence layer), and Application Services (transaction coordination)
* Problem Space - where strategic analysis happens and context maps are useful; defines your core domain
* Product Owner - concerned with product backlog; may overlap with the domain expert
* Published Language - context mapping where a well documented exchange language exists for bounded contexts to both send and receive
* Red-Green-Refactor - write a failing test and observe it fail before implementing the solution
* Remote Procedure Call (RPC) - attempts to disguise asynchronous network requests as local procedure calls, a leaky abstraction
* REST API - be careful so that changes in the service's model do not affect the shape of the resources provided to clients; a synthetic resource schema is best, where the client provides the schema and the service formats resources to match the client's specifications
* Scrum - knowledge acquisition is frequently neglected; carefully decide what to build, not just how to build
* Separate Ways - context mapping where integration is not providing value so the relationship is severed
* Services Oriented Architecture (SOA) - architecture pattern
* Shared Kernel - context mapping between subdomains that overlap; the kernel is the shared part of the subdomains; could be shared libs, often a source of trouble
* Simple Object Access Protocol (SOAP) - RPC over SOAP is a thing
* Single Responsibility Principle (SRP) - an aggregate should have a single, well-defined purpose and be easy to test
* Solution Space - where solutions are designed
* Specification by Example (SBE) - method for collaborative requirements gathering
* Strategic Design - the broad strokes; why the work is important, how it will be divided, where it will integrate
* Subdomains - divide the business domain into smaller, easier to reason about subdomains; ideally there is only one subdomain for each bounded context
* Supporting Subdomain - necessary to the Core Subdomain, may be something you want to outsource
* Tactical Design - more detailed design
* Task-Board Shuffle - team focuses on busy-work tasks at the expense of design; often the result of pressure to deliver fast
* Transaction - modification made to an aggregate under business invariants; an aggregate's state is internally consistent both before and after a transaction; transactions should only affect one aggregate at a time
* Ubiquitous Language - terminology used in the design and implementation of the system, agreed on between stakeholders and developers; must be strict and rigorous; the same term can mean different things in different bounded contexts
* Unbounded Legacy System - when the design is so contrary to DDD that it cannot be disentangled into independent subsystems
* Unified Modeling Language (UML) - barf
* Value Object - an immutable conceptual whole; often used to quantify an entity

# Techs

* Avro - wire format
* Coherence - json doc store
* Cucumber.io - library for writing acceptance tests
* GemFire / Geode - json doc store
* GigaSpaces - json doc store
* HipTest - platform for BDD
* Protobuf - wire format

# Names Dropped

* Douglas Martin - the alternative to good design is not "no design," but rather bad design
* Wall Street Journal - "software is eating the world"

# Publications

* [Aggregates in DDD - Event Sourcing Docs](https://eventsourcing.readthedocs.io/en/v3.0.0/topics/user_guide/aggregates_in_ddd.html)
* [DDD Aggregate - Martin Fowler](https://martinfowler.com/bliki/DDD_Aggregate.html)
* Book Design: A Practical Introduction - Douglas Martin book
* Essential Scrum - Kenneth Rubin book
* Implementing Domain-Driven Design (IDDD) - Vernon's previous book and DDD workshop
* Reactive Messaging Patterns with the Actor Model - Vaughn Vernon book
* Rest in Practice - book
