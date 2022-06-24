## Auth Service

This service handles identity management and access control in the platform.

### Responsibilities

1. Listen to NPO and Candidate registrations in the system to create corresponding users.
2. User management APIs - CRUD
   1. Create/update a user profile, metadata (npo_id, etc)
   2. Update user avatars
   3. Reset & Change Password
3. Roles and permissions management - CRUD
4. Send emails (publish to an email topic) to users on successful creation, reset/change password, etc.

### Driving Architectural Characteristics

#### Top 3

- **Feasibility (time)** - Since all the users and many services in the platform rely on auth service for identity and access control, this service becomes core to the platform and should be developed the earliest.
- **Availability** - Since this is a core service, this service needs to be highly available to support features in the platform.
- **Data integrity** - Auth service will not be able to function as expected if the data it stores is not accurate or consistent. So, data integrity is important for this service.

#### Other Driving Characteristics

- **Scalability** - Since this is a core service, traffic on this service is expected to quickly rise with the increase in no. of NPOs and candidates.
- **Responsiveness** - Since this service is a core service, it should be able to respond to requests as quickly as possible.
- **Security** - Since this service stores PII, data life cycle needs to follow certain compliance rules.

### Architectural Style Preferred

Hybrid - Microservices and Event-Driven

### Relevant ADRs

- [External IdP](../ADRs/adr-idp.md)