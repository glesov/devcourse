Microservices patterns:

API Gateway Pattern:
Pattern: The API Gateway Design Pattern is used in microservices-driven systems to create a centralized entry point for client interactions
Purpose: It improves the performance , security and centralized management of the microservices 

Circuit Breaker Pattern: 
Pattern: This prevents cascading failures if the Authentication Service becomes unresponsive.
Purpose: It improves system resilience and fault tolerance.

Intervention patterns:
Allows you to modify or enhance the behavior of a process without changing its core implementations.
Saga Pattern: 
Pattern: For complex authentication flows that involve multiple steps or services.
Purpose: It manages distributed transactions and allows for compensating actions if authentication fails at any step. 


Data patterns:

1. Database per Service Patterns
Pattern: In a microservices architecture, each service has its own database.  It allows each service to be decoupled from the others, which means that a failure in one service does not affect the others. 
Purpose:
a. Keep each microservice’s persistent data private to that service and accessible only via its API. 
b. Allows for better performance, as each service can be optimized independently based on its specific needs.
c. Optimized data schemas.
d. Security
e. Separation of concerns
f. Simpler queries


2. Command Query Responsibility Segregation (CQRS)
Pattern: CQRS is a microservices design pattern that separates read and write operations. 
It proposes the use of separate models for update (Command) and read (Query) operations. 
This segregation enables you to optimize each model for its specific purpose, thereby improving performance and scalability.
Purpose: Allows the read and write workloads to scale independently, and may result in fewer lock contentions.


Observability design patterns:

1. Distributed Tracing Pattern
Pattern: Trace is a unique component that distinguishes observability from other monitoring mechanisms. Distributed tracing tracks application requests as they flow from frontend devices to backend services and databases. 
Purpose: It helps quickly identify the technical glitches that cause infrastructure disruption.

2. Health Check Pattern
Pattern: Sometimes, it may happen that a particular service instance is running but is incapable of processing any request. Such services can be termed “unhealthy”.  Whenever an instance of an unhealthy service occurs, monitoring systems should generate an alert.
Purpose: It helps quickly identify  “unhealthy” service state.


3. Log Aggregation Pattern
Pattern: Logging is an essential part of effective troubleshooting. It’s an ongoing record of all the events in an application. When a service encounters an issue, a log message can help you find out the specific event that caused the disruption by describing what happened in the system and when. 
Purpose: It helps quickly identify the event that may have disrupted the production environment.

4. Audit Logging Pattern
Pattern: Audit logging (auditing) records all user activities in the database. An audit log comprises an event that occurs as a result of a user activity, the user’s identity, the action taken by them, the time at which they took action, and the entity affected by the event. 
Purpose: While regular system logs are recorded to help developers troubleshoot any errors, audit logs are maintained to keep a sequential record of user activity within the organization to ensure compliance with relevant industry regulations and your organization’s business policies.

5. Exception Tracking
Purpose: An exception may sometimes occur despite building highly reliable systems with zero bugs. When it does, it’s crucial to find its root cause and fix the problem.

6. Application Metrics
Pattern: Application metrics are a numerical representation of data that determines the current state of the service or particular component. 
Purpose: It provides a holistic view of the system’s health and performance.



AML Microservice Architecture Diagram
Attached in separeted file.
 
Here's an overview of an AML Microservice Architecture:
1.	API Gateway: 
        Acts as the entry point for all client requests
        Handles routing, load balancing, and security
2.	Authentication Service: 
        Manages user authentication and authorization
        Integrates with identity providers and manages tokens
3.	Transaction Monitoring Service: 
        Core of the AML system
        Analyzes transactions in real-time or batch processing
        Utilizes a Rules Engine for predefined scenarios
        Incorporates a Machine Learning Model for advanced pattern detection
4.	Customer Due Diligence (CDD) Service: 
        Manages Know Your Customer (KYC) processes
        Performs risk scoring on customers
        Integrates with external data sources for verification
5.	Reporting Service: 
        Generates regulatory reports (e.g., SARs, CTRs)
        Provides internal reporting and dashboards
6.	Databases: 
        Transaction Database: Stores all transaction data
        Customer Database: Stores customer information
        Alerts Database: Stores generated alerts and their statuses
        Reports Database: Stores generated reports
This architecture allows for scalability, flexibility, and easier maintenance of individual components. Each service can be developed, deployed, and scaled independently.
