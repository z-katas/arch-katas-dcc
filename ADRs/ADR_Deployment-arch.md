# Title
Deployment methods

## Status
proposed 

## Context
Deployment methods depict how a software is deployed into cloud or a machine to serve its users. It is an important piece of software architecture as it impacts cost, performance, availaibility of the software. 

### Alternatives
* Containers
* Serverless

### PrOACT (if any)

| Criteria      | Containers | Serverless |
| ----------- | ----------- | ----------- | ----------- 
| Cost  | High | low | 
| Maintainance | high        | low | 
| Portability | high, environment agnostic | Coupled with the environment.
| Feasibility(time) | large        | quick |
| Scalability | high(with auto scaling pods)        | high
| Availability | high        | low
| Latency | high        | low


## Decision
**Combination of Containers and serverless archiecture**.
* While both the methods come with their pros and cons and spotlight platform follows a microservice architecture, both the methods can be used for their respective usecases.
* Considering the cost and maintainance overhead by virtual containers some services which do not require high availability can be deployed into a serverless architecture. 
* Services which need to be highly available and responsive could be in virtualised containers.


## Tradeoffs
Team would need to have subject knowledge of both the architectures