## NPO-Candidate Quantum
![Image](../diagrams/quanta/np-candidate-quanta.jpg)

### Components and Responsibilities
* **NP Service**
  * Manages NPO registration, profile, capability assessment, posts, comments, offerings, NP User / Mentor profiles, npo partnerships, offering feedback.
  * Publishes events when posts are created, comments are added, there is a need to notify users, NPO is assessed, feedback is provided on offering, NPO Admin / User is registered.
* **Candidate Service**
  * Manages candidate registration, career assessment,  profile, testimonials, road map, incentives
  * Publishes events when candidate is assessed, testimonials are added, candidate registration is made, there is a need to notify users.
  * Listens to assignment updates to incentivize candidate.
  * Acts as an interface to **LinkedIn** to fetch candidate career profile.
* **Assignment Service**
  * Manages candidate and NPO assignments, feedback on assignments.
  * Listens to NPO assessed and Candidate assessed events to create corresponding assignments.
  * Listens to assignment created event to search for mentors to be tagged to the assignment.
  * Publishes events when assignments are updated and there is a need to notify users.
* **Auth Service**
  * Enables user management, access control. More details can be found in [Auth Service](../other-services/auth-service.md)



### Driving Architectural Characteristics
![Image](../images/np-candidate-quantum-worksheet.jpg)

#### Top 3
* **Feasibility (cost & time, in MVP)** - Since it is a green field project and quick market validation of the idea is paramount. Also, initial funding may be hard to come by.

* **Extensibility (Evolvability)** - Since it is a green field project and there is ambiguity at the beginning, the architecture should be flexible to introduce new features or change existing ones.
  
* **Scalability** - The components in this quantum form the core operational aspect of the platform and must be scalable to accommodate the capacity planned for the system.

* **Availability (Post MVP)**  - The components in this quantum form the core operational aspect of the platform and must be available in multiple zones across USA.

#### Other Driving Characteristics
  
* **Testability** - The components in this quantum hold policies and rules (such as incentive programs, registrations, mentor assignment rules, etc.) and must be testable easily.

* **Interoperability** - The service APIs in this quantum would be used by external NPOs to integrate with the platform. So the API documentation becomes important.

* **Recoverability** - The operational data captured by the components in this quantum used by the system for analytics and reports. So, it must be recoverable in case of disasters.

* **Data integrity** - Tracking candidate progress is a hard requirement and the operational data captured by the components in this quantum used by the system for analytics and reports. So, accuracy becomes important.

### Architectural Style
![Image](../images/np-candidate-quantum-style-worksheet.jpg)
* MVP - Modular monolith (see [ADR - NP Candidate Arch style MVP](../ADRs/adr-arch-style-np-candidate-mvp.md))
* Long-Term - Hybrid - Microservices and Event-Driven

### Trade-offs - Mitigation strategies
* Event driven + microservices is a costly architecture. Setting up the infrastructure (CI/CD pipelines, continuous delivery, aggregated logging and monitoring, etc.) becomes really important. 
  * Mitigation - Given the advancements in the devops world and so much guidance out on the internet, this should not be a concern. Also, setting up the infrastructure at the beginning of the project might reap benefits later on.
* Data is not consistent in an event driven system. It would be eventually consistent. 
  * Mitigation - This trade-off may be acceptable as the system is not dealing with mission critical information (such as affecting human life / money). 
* Having a microservices architecture may reduce the performance and reliability of the services due to network hops.  
  * Mitigation - Having an event-driven system internally with a reliable message queue would increase the reliability and performance of the system. 


### Call Flow diagrams

#### Course enrollment for a course call flow
![Image](../diagrams/call-flows/call-flow-course-enrollment.jpg)

### Post notification call flow
![Image](../diagrams/call-flows/call-flow-post-notification.jpg)

### NPO user updating an excel sheet to update candidate assignment progress call flow
![Image](../diagrams/call-flows/call-flow-candidate-assignment-progress.jpg)

### Relevant ADRs

- [Build vs buy](../ADRs/adr-build-vs-buy.md)
- [Identity Provider](../ADRs/adr-idp.md)