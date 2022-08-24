# About

* API Security in Action
* by Neil Madden
* publised by Manning Press, 2020

# Concepts

* Access Control - see Authorization; could also mean Authentication, Authorization, Audit logging (AAA); see Identity-Based and Capability-Based
* API Gateway - a type of reverse proxy that presents multiple back-end APIs as one unified API to the outside world
* API Security - exists in the intersection of AppSec, InfoSec, and Network Security
* Application Programming Interface (API) - in the past it commonly meant libraries (eg. OpenGL) but these days typically means a web REST API; conceptually it could be any software boundary where one system interfaces to another
* Application Security (AppSec) - the domain of securing the application layer, software security concerns
* Audit Logging - for accountability, monitoring; consider who did what op on what resource, when, did it work, what other requests were made
* Authentication - ensures that actors (users, clients) are who they claim to be; we don't authenticate users, but rather claims, eg. what they claim their username is, validated using credentials
* Authentication Factors - something you know (password), something you have (dongle), something you are (fingerprint, retina); note that passwords and security questions are both "something you know" and only count as one factor when used together
* Authorization - ensures that requests are allowed for the authenticated party
* BASIC + Z80 arch - simpler, happier times
* Capability-Based Access Control - client provides auth tokens for each resource they access
* CIA Triad - Confidentiality (privacy is ensured), Integrity (data changes require authorization), Availability (access is provided for legitimate users); other concerns may also matter such as accountability (audit trail of who performed what actions) and non-repudiation (actions cannot be denied / discredited)
* Encryption - prevents data from being read without authorization, data at rest or in transit (tls, ssl, https)
* Enterprise Java Beans - API work crushed under the weight of boilerplate code
* ForgeRock - start-up spun off of Sun Microsystems; author is the Director of Security
* General Data Protection Regulation (GDPR) - EU law that protects consumer data; orgs are required to report data breaches
* GraphQL - db query framework by Facebook
* gRPC - modern RPC framework by Google
* Hardening - process of securing an API against abuse; employs methods like encryption, rate limiting
* Identity-Based Access Control - resources granted based on client's ID
* Indistinguishability - a goal in encryption; attacker should not be able to tell which messages are which after encryption
* Information Security (InfoSec) - the domain of securing information for the duration of its lifetime, including transmission, backup, and destruction
* Internet of Things (IoT) - poses novel security challenges; rapidly expanding attack surface
* Intrusion Detection System (IDS) - can trigger actions when suspicious activity is detected
* Intrusion Prevention System (IPS) - lol yup
* JSON Web Token (JWT) - self-signed token format
* Kubernetes - poses novel security challenges
* Load Balancer - often employed at multiple levels, eg. one for each app server pool
* Macaroons - token format; cookies with contextual caveats
* Multi-Factor Authentication (MFA) - client provides multiple authentication factors
* Network Security - the domain of securing data transmission over network and network access
* Non-Functional Requirements (NFR) - security is often categorized here; difficult to quantify how much security is enough or whether it is working; security design is an iterative process, goals need continuing revision
* OAuth2 - token-based auth, provides federated auth
* Personally Identifying Information (PII) - data that can help to identify and individual
* Pooeys - pre-university IBM interns
* Rate-Limiting - prevent clients from hogging resources, prevents DoS attacks
* Remote Method Invocation (RMI) - variant of RPC with an object-oriented emphasis; formerly popular with frameworks like CORBA and Enterprise Java Beans
* Remote Procedure Call (RPC) - API style of abstracting requests as method calls, alternative to REST; tends to be lower overhead, may use efficient binary request formats; may require stub libs for clients
* Representational State Transfer (REST) - introduced by Roy Fielding; favours standard message formats over method calls (RPC)
* Reverse Proxy / Gateway - TLS encryption (SSL termination) is computationally expensive, typically handled here to keep load off of the back-end app servers
* SOAP - XML-based early effort at remote server calls
* STRIDE - Spoofing (pretending to be another party), Tampering (messing with data), Repudiation (denying you did something that you did do), Information disclosure (leaking data), Denial of service (preventing legitimate access), Elevation of privilege (gaining additional access privileges)
* Threat Model - a plan that predicts the threats relevant to your system design; try to identify actors, trust boundaries, actions, data flows
* Two-Factor Authentication (2FA) - client provides two authentication factors
* Web Application Firewall (WAF) - whereas a typical firewall inspects traffic at a low level, a WAF can enforce higher level traffic rules
* WebAuthn - standard for hardware auth; https://www.w3.org/TR/webauthn/
* XML-RPC - also like SOAP

# Names Dropped

* Dwight D. Eisenhower - "Plans are worthless, but planning is everything."
* Ward Cunningham - inventor of the wiki

# Publications

* Secure by Design - book by Dan Bergh Johnsson, Daniel Deogun, Daniel Sawano
