# KETI Development Standards

This document provides guidelines for the development of student-initiated applications under the KETI umbrella or elsewhere in the Kellogg ecosystem.

Application development and maintenance in an environment with institutionalized turnover and dispersed management requires a strong focus on continuity. The guidelines are designed to provide this focus without imposing onerous requirements on ‘entrepreneurial’ product development.

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](http://www.ietf.org/rfc/rfc2119.txt).


## 1. Hosting

Applications SHOULD be hosted on SESP’s OpenShift servers.

Northwestern's SESP has an Enterprise installation of Red Hat's OpenShift PAAS that provides: 
- Secure servers that meet Northwestern's standards
- Easy to provision instances with a variety of pre-configured environments
- Automated deployment tools (e.g. deploy straight from git)

Instructions for using OpenShift can be found at the [OpenShift Developer's Website](https://developers.openshift.com/index.html).


## 2. Data Access and Authentication

All Kellogg data MUST be sourced from a KIS-approved service, unless authorization has been obtained from the Dean’s Office to use another source. Instructions for using the API can be found at <insert link>.

> @todo Include link to instructions.

Applications MAY collect any other data they require either directly from users or using social authentication.

Applications MUST NOT store any data accessed through APIs in persistent storage. This ensures applications accurately reflect the state of Kellogg’s master data. Additionally, applications SHOULD NOT cache any data accessed through APIs for longer than X.

> @todo How long should the cache recommendation be?

Applications MUST NOT ask for or retain a user’s NetID password in any way.

Applications SHOULD use NetID based authentication.

> @todo Include additional information on authentication options.


## 3. Platforms, Languages and Frameworks

Web apps or server backends MAY use any combination on languages required to achieve the desired functionality. Developers SHOULD be parsimonious with language and framework choice to reduce maintenance overhead. This includes:
- Limiting the number of languages used
- Choosing common, low learning curve languages
- Only using well established frameworks

Web apps and servers SHOULD use a backend framework to simplify and secure the request/response process.

Mobile Apps SHOULD use a container framework rather than native code for easier maintenance.


## 4. Backups

Applications MUST contain information to completely reconstruct any database schemas. Schema definition MAY be implemented as orm-based migrations, plain SQL files, or any other reasonable method.

Applications SHOULD include an simple routine to back up and restore user-generated data (databases and files). Simple means not requiring more than 10 minutes of an admin's time to execute the procedure.

Applications MUST be backup up on a weekly basis to a 3rd party server.

> @todo Check if SESP runs backup routines that are sufficient for this requirement.

Source code MUST be made available to KIS and KETI executive. This can be done through a public Github repository, or a private repository 


## 5. Code Guidelines

Good coding practices MUST be adhered to in order to ensure the future viability of the application. Defining general code standards is difficult and beyond the scope of this document, however we do provide some guidelines. Third party developers are not worth paying for if they don't do this. Developing yourself is not the right answer if you can't do this yourself.

Code SHOULD adhere to the following guidelines:
- Follow conventions for the language or framework you are using
- Use simple, descriptive code; keep objects and functions short
- Follow separation of concerns (e.g. don't mix languages, separate business logic from display logic, etc.)
- Keep code DRY (Don't Repeat Yourself)
- Obey [SOLID principles](https://en.wikipedia.org/wiki/SOLID_(object-oriented_design)) if writing object oriented code
- Use descriptive variable, function and object names in consistent format (using language specific conventions)
- Use constants rather than hard-coded values
- Use consistent indentation
- Detect and deal with errors as they occur
- Write comments when something isn't obvious from the code, comment reasons rather than re-stating what the code does
- Write block comment headers in every file
- Use a logical file/folder structure


## 6. Testing and Documentation

Applications MUST include complete deployment instructions.

Applications MUST include a functional specification document. Applications MUST include a suite of functional tests. Applications MUST include a mapping of functional specifications to functional tests. This mapping MAY be included as comments in the functional tests or as a separate document.

Applications SHOULD include unit tests with reasonable code and feature coverage (see [this SO post](http://stackoverflow.com/questions/90002/what-is-a-reasonable-code-coverage-for-unit-tests-and-why) for reaonable).

> @todo Decide if we should be more specific about unit testing code coverage.