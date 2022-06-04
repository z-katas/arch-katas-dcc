## Assignment Service

![Image](../diagrams/candidate-service.jpg)

### Responsibilities

1. Role-based training is assigned to new Non-Profit
2. Create an assignment for the Non-profit organization
3. Create an assignment for the candidate
4. Assigning a mentor to the candidate
5. Assigning community leader to the Non-profit organization
6. Tracking candidate progress
7. Feedback from the candidate
8. Feedback from the Non-profit user

### Driving Architectural Characteristics

#### Top 3

- **Testability** - The service entails creating an assignment as well as designating community leaders and mentors, and testability will aid in the detection of bugs.

- **Interoperability** - As service needs to integrate with the organizations system to fetch candidate progress on the program enrolled.
- **Availability** - As the other service are dependent on this service, it has to be highly available.
