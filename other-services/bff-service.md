## Backend for frontend Service

This service handles all the frontend client interactions with the platform services.

### Responsibilities
1. Expose a graphql interface for all the frontend use cases.
2. Route Graphql API requests from UI to respective microservices translating them into rest requests.
3. Address the functional requirements which are different for UI from the backend.
4. Stream system events to UI incase of failures in async commits.
5. Merge data from different microservices and supply to the UI. (this helps when there is low network bandwidth)
6. Completely stateless

### Driving Architectural Characteristics

#### Top 3
* **Fault tolerance (time)** - This will be a single point of failure for the UI apps. Hence this has to be highly fault-tolerant.
* **Scalability** - Service should be highly scalable as 
* **Testability** - This needs to be testable and maintainable as we introduce more APIs to this service as the platform keeps growing, thus adding more room for bugs.


### Relevant ADRs
* [API standard](../ADRs/002.adr-api-standard.md)
* [Backend for frontend](../ADRs/004.adr-bff.md)

