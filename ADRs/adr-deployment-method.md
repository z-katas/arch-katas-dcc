# Title
Deployment methods - Containers vs serverless

## Status
proposed 

## Context
Deployment methods depict how a software service is deployed into cloud or a machine to serve its users. It is an important aspect of software architecture as it impacts cost, performance, availaibility of the software. 

### Alternatives
* Containers
* Serverless

### PrOACT

| Criteria      | Containers | Serverless |
| ----------- | ----------- | ----------- |
| Cost  | High | low | 
| Maintainance | high        | low | 
| Portability | high, environment agnostic | Coupled with the environment.
| Feasibility(time) | large        | quick |
| Scalability | high(with auto scaling pods)        | high
| Availability | high        | low (cold-start)
| Latency | high        | low
| Security | high        | low


## Decision
**Use either containers or serverless where necessary**.
* While both the methods come with their pros and cons and spotlight platform follows a hybrid (event driven + microservices) architecture for most of the architectural quanta, both the methods can be used for their respective usecases.
* Considering the cost and maintainance overhead of virtual containers, some services, like  which do not require high availability can be deployed into a serverless architecture. 
* Services which need to be highly available and responsive could be in virtualised containers.


## Tradeoffs
Team would need to have subject knowledge of both the architectures

## References
https://www.datadoghq.com/knowledge-center/serverless-architecture/
