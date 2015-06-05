# KETI Development Standards

This document provides guidelines for the development of student-initiated applications under the KETI umbrella or elsewhere in the Kellogg ecosystem.

Application development and maintenance in an environment with institutionalized turnover and dispersed management requires a strong focus on continuity. The guidelines are designed to provide this focus without imposing onerous requirements on ‘entrepreneurial’ product development.

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](http://www.ietf.org/rfc/rfc2119.txt).

## 1. Hosting

Applications SHOULD be hosted on CESP’s OpenShift servers.

> @todo Include link to instructions.

## 2. Data Access and Authentication

All Kellogg data MUST be sourced from a KIS-approved service, unless authorization has been obtained from the Dean’s Office to use another source.

> @todo Include link to instructions.

Applications MUST NOT/SHOULD NOT store any data accessed through APIs in persistent storage. This ensures applications accurately reflect the state of Kellogg’s master data. Additionally, applications MUST NOT/SHOULD NOT cache any data for longer than X.

> @todo Which one and how long?

Applications MUST NOT ask for or retain a user’s NetID password in any way.

## 3. Platforms, Languages and Frameworks

Mobile Apps SHOULD use a container framework rather than native code for easier maintenance.

## 4. Backups
Applications MUST contain information to completely reconstruct any database schemas. Schema definition MAY be implemented as orm-based migrations, plain SQL files, or any other reasonable method.

## 5. Code Guidelines

## 6. Testing and Documentation

Applications MUST include complete deployment instructions.

Applications MUST include a functional specification document. 

Applications MUST include a mapping of functional specifications to functional tests. This mapping MAY be included as comments in the functional tests or as a separate document.

Applications SHOULD include unit tests with X.

> @todo Include definition subparagraphs for functional specs and functional tests, unit tests and note a coverage condition.