## Meetings
![Image](../diagrams/quanta/meeting-quanta.jpg)

This service enables users to raise tickets (technical/general) and track the status. It provides support team access to all tickets and current progress.

### Responsibilities
1. Let NPOs create & manage events.
2. Maintain RSVP - invited, accepted, rejected, Maybe.
3. Send notifications to respective participants regarding any update to event.
4. Collect feedback, post an event.
5. Archive event post completion and disable further updates.

### Driving Architectural Characteristics

#### Top 3
* **Availability** - The service must be available at all times since other services are dependent on it.
* **Feasibility** - Meetings is the core value proposition of the platform to enable better engagement between the user, especially Candidates and Mentors. So, building it as part of the MVP is inevitable and feasibility becomes important. One can consider going for a 3rd party chat provider, rather than building in-house.
* **Recoverability** - Service must recover from any failures fast and no loss of data.

### Architectural Style Preferred
Microservices

### Relevant ADRs
NA

