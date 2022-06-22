# Deployment methods - Containers Vs Serverless
Date: 2022-06-21

## Status
Accepted 

## Context
Deployment methods depict how a software service is deployed into a cloud or a machine to serve its users. It is an important aspect of software architecture as it impacts cost, performance, availability of the software. 

### Alternatives
* Containers
* Serverless

### PrOACT

| Criteria      | Containers | Serverless |
| ----------- | ----------- | ----------- |
| Cost  | High | low | 
| Maintenance | high        | low | 
| Portability | high, environment agnostic | Coupled with the environment.
| Feasibility(time) | large        | quick |
| Scalability | high(with auto scaling pods)        | high
| Availability | high        | low (cold-start)
| Latency | high        | low
| Security | high        | low


## Decision
**Use either containers or serverless where necessary**.
* The spotlight platform follows distributed architecture styles (event-driven, micro-services, microkernal) for various architectural quanta. So, both the methods can be used for their respective use-cases.
* Considering the cost and maintenance overhead of virtual containers, some services which do not require high availability can be deployed into serverless architecture. 
* Services that need to be highly available and responsive could be in virtualized containers.


## Tradeoffs - Mitigation Strategies
* Going serverless may affect availability of services while going with virtualized containers can add cost and maintenance overhead. And, as identified in [Requirement Analysis](../README.md#requirement-analysis), feasibility (cost) can be a concern.
  * Consider using managed deployment services (like AWS ECS or Google Cloud Run, depending on the chosen cloud provider) to mitigate operational overhead of scaling, patching, securing, and managing servers.
* The platform developers would need to have subject knowledge of both the deployment styles.

## References
https://www.datadoghq.com/knowledge-center/serverless-architecture/
