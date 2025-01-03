---
# These are optional metadata elements. Feel free to remove any of them.
status: "{ accepted }"
date: {2024-01-04 when the decision was last updated}
decision-makers: {Thuu Shan Phoye, Kyaw Zin Thu}
consulted: {Thuu Shan Phoye, Kyaw Zin Thu}
informed: {Thuu Shan Phoye, Kyaw Zin Thu}
---

# {short title, representative of solved problem and found solution}

## Context and Problem Statement

{Describe the context and problem statement, e.g., in free form using two to three sentences or in the form of an illustrative story. You may want to articulate the problem in form of a question and add links to collaboration boards or issue management systems.}

<!-- This is an optional element. Feel free to remove. -->
## Decision Drivers

* {decision driver 1, e.g., a force, facing concern, …}
* {decision driver 2, e.g., a force, facing concern, …}
* … <!-- numbers of drivers can vary -->

## Considered Options

* {title of option 1}
* {title of option 2}
* {title of option 3}
* … <!-- numbers of options can vary -->

## Decision Outcome

Chosen option: "{title of option 1}", because {justification. e.g., only option, which meets k.o. criterion decision driver | which resolves force {force} | … | comes out best (see below)}.

<!-- This is an optional element. Feel free to remove. -->
### Consequences

* Good, because {positive consequence, e.g., improvement of one or more desired qualities, …}
* Bad, because {negative consequence, e.g., compromising one or more desired qualities, …}
* … <!-- numbers of consequences can vary -->

<!-- This is an optional element. Feel free to remove. -->
### Confirmation

{Describe how the implementation of/compliance with the ADR can/will be confirmed. Is the chosen design and its implementation in line with the decision? E.g., a design/code review or a test with a library such as ArchUnit can help validate this. Note that although we classify this element as optional, it is included in many ADRs.}

<!-- This is an optional element. Feel free to remove. -->
## Pros and Cons of the Options

## ADR for Software Architecture Design

{Context and Problem Statement: The Advanced Media Library (AML) is a library network across England. It faces issues such as outdated systems, inefficient media management, limited payment options, and inconsistent access to resources. AML requires a modern, scalable, and accessible system to handle increased user demand and to improve internal workflows.
}

## Decision Drivers

Scalability: The system must handle many users and requests efficiently.
Ease of Use: Staff and library members should find the system easy to navigate.
Easy Updates: The system should allow easy updates for staff and administrators.
Resource Sharing: Media should be shared effectively among branches.
Availability: The system should be available 24/7 across multiple channels (web, mobile, telephone).
Cost Efficiency: The system should be cost-effective to maintain.

## Considered Options

Three-Tier Architecture
Microservices Architecture
Monolithic Architecture

## Decision Outcome
AML will adopt the Three-Tier Architecture. This architecture will ensure scalability and flexibility, handle the growing user base, and support efficient resource sharing across branches. Microservices are not necessary because the project is not yet large or complex enough.

## ADR for Database Selection
{Context and Problem Statement: AML needs a reliable, scalable database to store media (books, journals), user information, and transactions, all while ensuring GDPR compliance and high availability.
}

## Decision Drivers

Scalability: Should handle growing user and transaction volume.
Data Accuracy: Ensure consistency across branches.
High Availability: The system should be available 24/7.
Cost Efficiency: The database should be cost-effective.
GDPR Compliance: Must comply with data privacy laws.

## Considered Options

MySQL
Oracle Database
Microsoft SQL Server
PostgreSQL
## Decision Outcome
AML will use MySQL. It is cost-effective, scalable, and has strong community support. It is a good balance of features and cost-efficiency, making it suitable for AML's current needs.

### Consequences
*Good:
Free to use with strong community support.
Ensures data accuracy and security.
Scalable through replication.
*Bad:
Requires extra tuning for very large datasets.
Lacks some advanced features found in paid databases.

## ADR for Choosing a Programming Language

{Context and Problem Statement: AML is building a new system and needs to choose a suitable programming language for backend and frontend services, supporting scalability, speed of development, and security.
}

## Decision Drivers

Scalability: Handle high user load.
Speed of Development: Should support quick development.
Maintenance: Code should be easy to read and maintain.
Security: The language should support safe system design.
Talent Pool: Availability of skilled developers.

## Considered Options

Java
Python
C# (.NET)

## Decision Outcome
AML will use Java for the backend to ensure scalability, performance, and long-term growth. React (with TypeScript) will be used for the frontend to provide a responsive, dynamic user experience.

### Consequences
*Good:
Java ensures scalability and performance.
React and TypeScript offer a streamlined approach for modern web development.

*Bad:
Using multiple languages means managing different sets of tools.
Java can be slower to develop with compared to other languages.

## ADR for API Design

{Context and Problem Statement: AML needs a structured API design to integrate various components of the system smoothly. The API must be easy to use, scalable, and reliable.
}

## Decision Drivers
Ease of Use: The API should be developer-friendly.
Scalability: Must accommodate future changes and features.
Reliability: Should have clear error handling and stability.

## Considered Options
RESTful API
GraphQL
SOAP

## Decision Outcome
AML will implement a RESTful API due to its simplicity, widespread adoption, and ease of integration with various services.

### Consequences
*Good:
Simpler for developers to work with.
Consistent with standard HTTP methods.
Supports versioning to enable seamless updates.

*Bad:
May become cumbersome with complex queries.

## ADR for Frontend UI/UX Design

{Context and Problem Statement: AML needs a user-friendly interface that allows smooth navigation for both staff and users. The interface must be responsive, accessible, and easy to maintain.
}

## Decision Drivers
Usability: The interface must be intuitive and user-friendly.
Responsiveness: The design should work seamlessly across devices (desktop, mobile, tablet).
Accessibility: The design must comply with WCAG 2.0 standards for accessibility.
Development Speed: The framework should allow rapid development.

## Considered Options
Bootstrap
Custom CSS and JavaScript
Other Frameworks (e.g., Foundation, Bulma)

## Decision Outcome
Tailwind CSS will be used for UI styling due to its flexibility, extensive documentation, and ability to rapidly build custom, responsive designs. React with TypeScript will handle the frontend, ensuring strong typing and component-based development for scalability.

### Consequences
*Good:
Simpler for developers to work with.
Consistent with standard HTTP methods.
Supports versioning to enable seamless updates.

*Bad:
May become cumbersome with complex queries.

## ADR for Security (JWT Authentication)
{Context and Problem Statement:
AML requires a secure authentication mechanism for users accessing the system. The solution must ensure that only authorized users can access sensitive data.}

## Decision Drivers:
Security: The authentication system must be robust and secure.
Scalability: The solution should be scalable to accommodate future growth.
Integration: The security mechanism should integrate seamlessly with the backend API.

## Considered Options:
Session-based Authentication
JWT Authentication

## Decision Outcome:
JWT Authentication will be used for secure, stateless user authentication. This approach will ensure that user sessions are easily manageable, and secure access is granted only to authorized users, without the need for server-side session storage.

## ADR for Google Cloud API Integration
{Context and Problem Statement:
AML requires integration with Google Cloud APIs for storing media and handling file uploads efficiently.}

## Decision Drivers:
Scalability: The API must handle large volumes of data.
Cost: The solution must be cost-effective.
Ease of Integration: The API should be easy to integrate with the existing infrastructure.

## Considered Options:
Google Cloud Storage API
AWS S3
Azure Blob Storage

## Decision Outcome:
Google Cloud Storage API will be used for storing and managing media files. It offers scalability, ease of integration, and a cost-effective solution for AML’s requirements.

