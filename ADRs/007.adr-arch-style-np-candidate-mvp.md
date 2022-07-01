# Arch style for NP candidate quanta
Date: 2022-06-23

## Status
Proposed 

## Context
Np candidate quanta consists of the core services in our architecture
![Image](../diagrams/quanta/np-candidate-quanta.jpg)

Spotlight platform is a greenfield project. It comes with ambiguities and risks.

### Alternatives

* Modular Monolith
* Microservice

### PrOACT

| Factor      | Modular Monolith | Microservice |
| ----------- | ----------- | ----------- |
| Cost(time+money)  | Low | High | 
| Maintenance | Low        | High | 
| Coupling | High | Low
| Scalability | Low        | High |
| Extensibility | Low | High

## Decision
* **Modular Monolith** if there is a cost constraint.  Start with the monolith and later migrate to microservice + event driven after there is a product market fit and a system required to scale.


* **Microservice + Event Driven** If there is no cost constraint 


## References

[Monolith vs micorservices](https://www.geeksforgeeks.org/monolithic-vs-microservices-architecture/)