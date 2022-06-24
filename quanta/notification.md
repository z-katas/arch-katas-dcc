## Notification Quantum
![Image](../diagrams/quanta/notifications-quanta.jpg)

### Responsibilities
1. Send in-app and push notifications to users, this will increase the usability of the app.
2. Saves users' preferences about the type and frequency of notifications they would like to be subscribed to.
3. Notify users via emails.
4. Integrate with 3rd party notification and email providers.
4. Enable users to send and notify user(s) through emails and notifications


### Driving Architectural Characteristics

![Image](../images/notification-quantum-worksheet.jpg)
#### Top 3
##### Driving Architectural Characteristics
1. **Scalability** - The quantum is highly scalable and can be scaled to the growing NPO + Candidate community adopting to the platform.
2. **Extensibility** - Should be able to add new notification channel easily.
3. **Availability** - Notifications for all the events in the system depend on this service. So this service needs to be highly available

##### Characteristics that we do not need as we offloaded to 3rd party vendors
* **Security** - Security around emailing service will be the responsibility of the emailing vendor.


### Architectural Style Preferred
Hybrid - Microservices + Event Driven

![Image](../images/notification-quantum-arch-characteristics.jpg)

### Relevant ADRs

