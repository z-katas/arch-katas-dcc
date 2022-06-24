## Chat Quantum

![Image](../diagrams/quanta/chat-quanta.jpg)

### Context

Having in-app chat support on the platform is a great way to engage with the community. Also, a candidate doesn't have to leave the app to engage with the mentors (say, over email).

However, Building a reliable chat service within the platform would take time and is not the core value proposition. (See [ADR](../ADRs/adr-build-vs-buy.md)). Recommended to use a 3rd party calendar service.

### Responsibilities

1. Initiate a new conversation with users.
2. View and reply to messages.
3. Support read receipts and last active status.
4. Integrate with 3rd party chat service for the functionalities.
5. [Long Term] Remind users through an email if a chat remains unread.

### Driving Architectural Characteristics

![Image](../images/chat-quantum-worksheet.jpg)

#### Top 3

##### Driving Architectural Characteristics

* **Extensibility** - Should support addition of platform specific features not provided by the 3rd party meetings provider.
* **Abstraction** - The chat service acts like a facade to the 3rd party chat provider.
* **Testability**

##### Characteristics that we do not need as we offloaded to 3rd party vendors
* **Security** - Security for messages during storage and transit.
* **Scalability** - Service highly depends on third party service for scale
* **Availability** - Service highly depends on third party service for uptime
* **Responsiveness** - The messages have to be sent and received with minimal latency

### Architectural Style Preferred

![Image](../images/chat-quantum-arch-characteristics.jpg)
Microservices

### Relevant ADRs

- [Build vs buy](../ADRs/adr-build-vs-buy.md)