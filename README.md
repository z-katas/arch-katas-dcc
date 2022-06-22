# Spotlight Platform

## Table of Contents
* [About the team](#about-the-team)
* [Glossary](#glossary)  
* [Prelude](#prelude)  
* [Requirement Analysis](#requirement-analysis)
* [User Experience](#user-experience)  
  * [Candidate Flow](#candidate-flow)
  * [Non Profit Flow](#non-profit-flow)
* [Assumptions](#assumptions)
* [User Roles](#user-roles)
* [Identifying Architectural Quanta](#identifying-architectural-quanta)
  * [Quanta](#quanta)
  * [Other Services](#other-services)
* [Overall Architecture](#overall-architecture)
  * [Logical View](#logical-view)
  * [Component View](#component-view)
* [Platform Roadmap](#platform-roadmap)
* [Call Flow diagrams](#call-flow-diagrams)
* [Engineering Practices](#engineering-practices)
* [Resources](#resources)

<a name="about-the-team"></a>
## About the team

We are a team of passionate software engineers & designers from product-market-fit studio [Zemoso](https://www.zemosolabs.com/).

* [Ashish Kumar Das](https://www.linkedin.com/in/das-ashish/) 
* [Naveen Chevuru](https://www.linkedin.com/in/naveenchevuru/) 
* [Pranava Shashank P](https://www.linkedin.com/in/pranavashashank/) 
* [Sai Venkatesh Vemuri](https://www.linkedin.com/in/saivenkateshvemuri/) 
* [Vasanth Kumar](https://www.linkedin.com/in/vasanth-kumar-22b9a4109/) 

<a name="glossary"></a>
## Glossary
* NPO / NP - Both acronyms are used to refer to non-profit organizations.
* NFR - Non-functional requirement
* MVP - Minimum Viable Product
* PII - Personal Identifiable Information
* UI - User Interface
* UX - User Experience
* IA - [Information Architecture](https://en.wikipedia.org/wiki/Information_architecture)
* The team - Pegasuz team

<a name="prelude"></a>
## Prelude
There are about 1.6 million non-profit organizations [[Source](https://independentsector.org/about/the-charitable-sector/)] and more than 100 million underrepresented people [[Source](https://www.governing.com/archive/gov-nonprofits.html)] in the US. But the problem today is that these NPOs are decentralized and there is no support / framework for active collaboration. Also, lack of visibility of the NPOs creates a barrier of access to the underrepresented demographics. 

Let's imagine a use case - A candidate plans to enrol for a course in an institution in **City A**, away from his home city. He would need to travel to **City A**, find an affordable place to stay, search for places to get groceries and food, etc. Also, after completion of the course, he would need to prepare for interviews and get placed. Without a centralized system and collaboration between NPOs, the candidate may end up spending a lot more than what he can afford and his career path / shift may not be feasible.

The number of NPOs and underrepresented people mentioned above are quite large and provide tremendous opportunities to build a platform to enable the collaboration.

Diversity Cyber Council has come forward with a vision to enhance inclusion and representation in the tech industry through training, mentoring, networking, and visibility programs.

### Goal of the platform
To establish a sustainable and diverse talent pipeline that extends career equity to underrepresented demographics by providing access to competent training programs that lead to direct employment opportunities.


## Non-Functional Requirements

After the [analysis of business requirements and ideas](other-arifacts/Requirement-analysis.md) the team has come up with the below NFRs for the system

| NFR | Relevance | 
| -- | -- | 
| Configurability | To introduce or update new incentive rules and rewards systems with no to minimal engineering effort
| Performance | The platform must be performant to provide faster matches between NPO offerings and Candidates and provide relevant recommendations. Indexing categories on various data entities may help in this regard.|
| Usability| The underrepresented demographics may not be tech-savvy. So, the Spotlight App's Information Architecture should be simple and intuitive to improve engagement. |
| Interoperability| To enable NPOs to integrate with the Spotlight platform, platform needs to have well defined and documented APIs.|
|Workflow | For NPOs which have their own APIs for their offerings, data must be regularly pulled from the APIs to update candidate progress in the platform.|
| Data Integrity|Warrants data integrity in the system to accurately show candidate progress as and when his course progress is updated. |
|Recoverability & Fault tolerance | Since the files/documents are essential for any NGO to operate, they must be safely stored and recoverable (in case of disaster).  | 
| Reporting & analytics| System should reliably store user activity and data coming from various services in the platform. | 
|Feasibility & Evolutionary | Shorter iterations to get market feedback and pivoting, if necessary, becomes important. So, the architecture should be in such a way that it can evolve with the growth in the business.|
| Security & Privacy | Sensitive data stored in the system includes - Candidate career profiles, PII (email, phone, address, ethnicity, SSN, etc.). System should allow users to erase all their data permanently at any point in time..

<a name="user-experience"></a>
## User experience
The team went through a design thinking exercise to understand the Candidate and NP user profiles, and empathize their needs and pain points. The following golden paths were considered:

[Design artifacts](./design/design-artifacts.md)

<a name="candidate-flow"></a>
### Candidate Golden Path

![Image](./images/candidate-golden-path.jpg)

https://www.loom.com/share/7d1540ecfed24c0191f7087d7a747260

<a name="non-profit-flow"></a>
### Non-Profit Golden Path

![Image](./images/non-profit-organization-golden-path.jpg)

https://www.loom.com/share/2f3be1ded8bd438e958ffd8cc9595e83

<a name="assumptions"></a>
## Assumptions
#### Capacity planning
Going by the no. of NPOs and under represented demographics mentioned in [Prelude](#prelude), we decided to design the system for the following capacity:
![Image](images/capacity-planning.jpg)

<a name="user-roles"></a>
## User Roles
* PLATFORM_ADMIN (associated with the Spotlight Platform)
* COMMUNITY_LEADER (associated with the Spotlight Platform)
* NP_ADMIN (associated with the NPO)
* NP_USER (associated with the NPO) - Can be NPO offering's mentor 
* CANDIDATE

<a name="identifying-architectural-quanta"></a>
## Identifying Architectural Quanta
**Architecture quantum** - *An independently deployable artifact with high functional cohesion and synchronous connascence*

Quanta identification helps in defining different parts of the platform and the scope of architectural characteristics. We followed a mixture of event storming + actor-action approach to identify aggregates, components and quanta.

[Click here for more details on the exercise.](./quanta/quanta-identification.md)


<a name="quanta"></a>
### Quanta
* [NPO - Candidate](./quanta/npo-candidate.md)
* [Reports](./quanta/reports.md)
* [Notification](./quanta/notification.md)
* [Recommendations](./quanta/recommendation.md)
* [Chat](./quanta/chat.md)
* [Meetings](./quanta/meetings.md)
* [Document](./quanta/document.md)
* [NPO Integrations](./quanta/npo-integration.md)


<a name="other-services"></a>
### Other Services
* [Infrastructure Services](./other-services/infrastructure-services.md)
* [Support](./other-services/support-service.md)
* [BFF](./other-services/bff-service.md)


<a name="overall-architecture"></a>
## Overall Architecture

<a name="logical-view"></a>
### Logical View
![Image](./diagrams/logical-arch/spotlight-logical-architecture.jpg)
[View as pdf](./diagrams/logical-arch/spotlight-logical-architecture.pdf)

<a name="component-view"></a>
### Component View
![Image](./diagrams/component/spotlight-component-diagram.jpg)

[View as pdf](./diagrams/component/spotlight-component-diagram.pdf)

[For better navigation on the image, use this miro board](https://miro.com/app/board/uXjVOv-nlBo=/?moveToWidget=3458764526827413301&cot=14)

<a name="platform-roadmap"></a>
## Platform Roadmap

### MVP
The MVP is envisioned to bring out the unique value proposition of the platform and solve the key business problem / pain points. It should be sufficient for the business to get market feedback and pivot, if needed.

Areas to be addressed:
* Base platform infrastructure
  * CI / CD pipelines with continuous delivery.
  * Logging
  * Monitoring
* Candidate - NPO quantum
* Reports quantum - Without Analytics
* Notification quantum
* Recommendations quantum - Simple, without model training
* Meetings quantum
* Document quantum
* Chat quantum

### Long Term
Areas to be addressed:
* Reports quantum - Advanced predictive analytics
* Recommendations quantum - with model training
* NPO Integrations

<a name="call-flow-diagrams"></a>
### Call Flow diagrams

#### Course enrollment for a course callflow
![Image](diagrams/call-flows/call-flow-course-enrollment.jpg)

### Post notification call flow
![Image](diagrams/call-flows/call-flow-post-notification.jpg)

### NPO user updating an excel sheet to update candidate assignment progress callflow
![Image](diagrams/call-flows/call-flow-candidate-assignment-progress.jpg)


<a name="engineering-practices"></a>
## Engineering Practices

* [Continuous Integrations and Continuous Deployment ](./engineering-practices/CI-CD.md)
* [Continuous Delivery](./engineering-practices/Continous-Delivery.md)
* [Data compliance and Security](./engineering-practices/Data-compliance-security.md)
* [Twelve Factor app](./engineering-practices/twelve-factor.md)
* [Sidecar Pattern](./engineering-practices/sidecar-pattern.md)
* [Monitoring and Observability](./engineering-practices/Monitoring.md)
* [Feature Toggles](./engineering-practices/Feature-Toggles.md)


<a name="resources"></a>
## Resources
* [Design Thinking](https://miro.com/app/board/uXjVOv-nLZE=/)
* [Arch Katas Artifacts](https://miro.com/app/board/uXjVOv-nlBo=/)
