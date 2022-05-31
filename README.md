# Spotlight Platform

## Prelude

## Golden Path

### Candidate Flow

### Non-Profit Flow

## Requirement Analysis



## Assumptions

## Identifying Architectural Quanta

### Event Storming

### Quantum - Responsibilities and Architectural Characteristics

#### Support Service

##### Responsibilites

1) Let users / NPOs raise support tickets.
2) View raised tickets and status.
3) Let support team view all tickets and status.
4) Notify users / support team any update on the ticket.
5) Multichannel support (Optional) - Chat, Voice, Email.

##### Architectural Characteristics

1) Availability - Support service must be highly available (24x7) to raise any issues.
2) Workflow - The tickets follow progress across statuses in a defined workflow.
3) Data integrity - Data captured in tickets is of most importance - overall accuracy, completeness,  of data is necessary.

#### Reports Service

##### Responsibilites

1) Let users generate and download reports on demand in requisite formats - PDF, CSV etc.
2) Scheduler to send reports - EOD, Weekly, Monthly etc.
3) Provide most commonly used reports by default
4) Enable creation of custom reports (using custom query language)

##### Architectural Characteristics

1) Performance - Since reports can be fetched for varying time periods, the amount of data to be processed might be high - necessary optimizations must be done to ensure decent performance.
2) Recoverability - Service must recover from any failures fast and with minimal loss of data.
3) Configurability - Users can create and configure the way reports need to be generated. 

#### Meetings Service

##### Responsibilites

1) Let NPOs create & manage events.
2) Maintain RSVP - invited, accepted, rejected, Maybe.
3) Send notifications to respective participants regarding any update to event.
4) Collect feedback post event.
5) Archive event post completion and disable further updates.

##### Architectural Characteristics

1) Availability - The service must be available at all times since other services are dependent on it.
2) Scalability - There might be additional load on the service during weekends / holidays when events are usually held vs. Weekdays. The service should scale accordingly.
3) Recoverability - Service must recover from any failures fast and with minimal loss of data.

## Architectural Style

### Logical View

### Component View


## Design Principles