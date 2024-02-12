# Architecture Exercise

This is an exercise to design a cloud based solution to high level requirements. The requirements are deliberately loose to allow for maximum freedom with design. Please see the requirements below and design an architecture for hosting this service, diagrams are highly encouraged but anything that effectively gets the point across is acceptable. Your supplied diagram(s) and explanations should describe enough of the design without you needing to talk through it all in person.

Due to the high level nature of this task, there may be some ambiguity in the functioning of services; please write down any assumptions you have made about how the services work to aid your design. Let your mind fill in the blanks, the point of completing this is to spark conversation during the interview. You may use whichever cloud provider terminology you're most familiar with, just please mention which provider you're using.

**You should aim to spend no more than 90 minutes on this task, if you run out of time, write down what you what have done next.**

## Requirements

* Highly available deployment authentication/authorization service (ref: Auth Service)
  * Delivered via CI pipeline output as a Java JAR file
  * Is a microservice that is responsible for checking authentication/authorization on an inbound HTTP request before it is forwarded downstream to the main application
  * This service reads from a backend database in PostgreSQL
* Highly available deployment of main application (ref: Main App)
  * A NodeJS JavaScript application, available as a tar file from CI pipeline output
  * Is responsible for responding to periodic connections from a mobile app
  * This service reads/writes from/to a backend database in Cassandra
* Task that runs periodically to archive old data (ref: Cleanup Job)
  * A Python application, available as a Python script file from CI pipeline output
  * This script reads/writes from/to the same backend database as the NodeJS application

## Considerations

Please be mindful of the following considerations as you work through this solution:

* Security
* Scalability
* Maintainability
* Cost effectiveness

Our questions will be around these topics mainly.
