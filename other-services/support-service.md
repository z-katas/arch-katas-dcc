## Support Service
![Image](../diagrams/support-service.jpg)

This service enables users to raise tickets (technical / general) and track the status. It provides support team access to all tickets and current progress.

### Responsibilities
1. Let users / NPOs raise support tickets.
2. View raised tickets and status.
3. Let support team view all tickets and status.
4. Notify users / support team any update on the ticket.
5. Multichannel support (Optional) - Chat, Voice, Email.

### Driving Architectural Characteristics

#### Top 3
* **Availability** - Support service must be highly available (24x7) to raise any issues.
* **Workflow** - The tickets follow progress across statuses in a defined workflow.
* **Data integrity** - Data captured in tickets is of most importance - overall accuracy, completeness,  of data is necessary.

### Architectural Style Preferred
Microservices

### Relevant ADRs
NA

