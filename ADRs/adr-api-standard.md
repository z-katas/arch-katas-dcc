# Title
API Standard

## Status
Proposed 

## Context
Frontend apps (web and mobile) of the spotlight platform communicate with the platform services to fetch and mutate data. Service APIs determine the iteroperability between services and the apps. So, it becomes essential to choose the right API standard to support the usecases and provide better responsiveness and usability of the apps.

### Alternatives
* REST
* Graphql
* gRPC 

### PrOACT (if any)

| Criteria              | REST                       | Graphql | gRPC | 
|-----------------------|----------------------------| ----------- | ----------- 
| Feasibility           | high                       |high | low
| Latency               | higher                     | higher | lower| 
| Client/app friendly   | no                         | very much | no| 
| Maturity,maintainance | matured                    |actively improving  | actively improving| 
| Community             | Old and large market users | growing community | growing community
| Adaptability          | easily adaptable           | slight friction for new consumers | less likely adaptable as it is fairly new

## Decision
**Both REST and Graphql**.
* Graphql APIs solve problems of over fetching and under fetching, making it extremely convenient especially for mobile apps. This will optimise performance slightly due to a smaller payload over mobile networks. Further, since Graphql is schema based, it can help achieve type-safety with service APIs. 
* REST APIs are resource oriented and have been around since decades. Third party users or NGOs might feel it easy to integrate with the Spotlight platform using REST.

## Tradeoffs - Mitigations
* Supporting multiple API standards will add an infrastructure overhead.
  * Mitigation - Initially, introduce Graphql on just the backend-for-frontend (BFF) service to support the Spotlight web/mobile app. All the other platform services can start with supporting REST and the BFF can talk these services via REST. Long term, the platform services can support Graphql as well and the existing infra can be migrated to a Graphql federation design.
* Low performance (compared to gRPC) but this may not impact the use cases as there are not many services and the operations are not mission critical (do not affect human life or money).
* For streaming (in-app notifications), if any, consider using web sockets.