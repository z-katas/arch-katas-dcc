## Chat Service
![Image](../diagrams/chat-service.jpg)

### Responsibilities
1. Initiate a new converstation with users.
2. View and reply to messages.
3. Support read receipts and last active status.
4. Integrate with 3rd party chat service for the functionalities.
4. Remind users through a email if a chat remains unread. 


### Driving Architectural Characteristics
#### Top 3
##### Driving Architectural Characteristics
1. Responsiveness
   The messages have to be sent and received with minimal latency
2. Data integrity
   Correctness of messages and intended recipients.
3. Feasibility (cost + time)

##### Characteristics which we do not need as we offloaded to 3rd party vendors
1. Security
   Security for messages during storage and transit.
2. Scalability and Availability  
    Service highly depends on third party service for scale and uptime


### Architectural Style Preferred
Microservices

