## Meetings Service
![Image](../diagrams/quanta/meeting-quanta.jpg)

This service enables users to raise tickets (technical / general) and track the status. It provides support team access to all tickets and current progress.

### Responsibilities
1. Let NPOs create & manage events.
2. Maintain RSVP - invited, accepted, rejected, Maybe.
3. Send notifications to respective participants regarding any update to event.
4. Collect feedback post event.
5. Archive event post completion and disable further updates.

### Driving Architectural Characteristics

#### Top 3
* **Availability** - The service must be available at all times since other services are dependent on it.
* **Scalability** - There might be additional load on the service during weekends / holidays when events are usually held vs. Weekdays. The service should scale accordingly.
* **Recoverability** - Service must recover from any failures fast and with minimal loss of data.

### Architectural Style Preferred
Microservices

### Relevant ADRs
NA

