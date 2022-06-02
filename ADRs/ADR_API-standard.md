# Title
API Standard

## Status
proposed 

## Context
Frontend clients(Web and mobile) communicate to our microservices to fetch and mutate data. The APIs are the interface between microservices(platform) and the various(web,mobile, intergation systems). It becomes essential to choose an API standard suitable for usecases and client platforms as this will drive responsiveness, availaibility, usability of the platform. 

### Alternatives
* Rest 
* Graphql
* gRPC 

### PrOACT (if any)

| Criteria      | Rest | Graphql | gRPC | 
| ----------- | ----------- | ----------- | ----------- 
| Feasibility       |  high       |high | low
| Latency  | higher | higher | lower| 
| client friendly | no        | very much | no| 
| Maturity,maintainance | matured        |actively improving  | actively improving| 
|Community| Old and large market users  | growing community | growing community
|adaptability| easily adaptable | slight friction for new consumers | less likely adaptable as it is fairly new
## Decision
**Both Rest and Graphql**.
* Graphql APIs solve problems of over fetching and under fetching, making it extremely convinient especially for mobile apps. This will optimise perforamnce slightly due to less payload over mobile networks, further helping us achieve type safety with our APIs. 
* Rest APIs are resource oriented and have been around since decades, third party users feel easy to integrate with our systems

## Tradeoffs - Mitigations
* Supporting multiple standards will add an infrastrcture overhead.
* Low performance(compared to rpc) - This is something we can live with since our scale is small
* For streaming usecases we can go with web sockets