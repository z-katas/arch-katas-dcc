# Title
Backend for frontend(BFF)

## Status
proposed 

## Context
Following the [API standard decision](./adr-api-standard.md) the spotlight apps would require to consume graphql APIs and external consumer services would prefer Rest APIs.It is a infrastructure overhead for all the microservices to supports both the standards initially. A Backend for frontend is a service catered for frontend needs and can follow a different API standard from rest of the system. 

<b>Advantages of BFF pattern with Graphql</b>

* Solves problems of over fetching and underfetching. 
* Solve functional requirements which are different for UI from backend.
* The frontend client would only need to hit a single service. 

## Decision
Decision and justification

## Tradeoffs - Mitigations

* <b> Single point of failure</b> : If BFF is not available the UI apps will not function. 
    Mitigation: Have BFF in multiple availability zones.
* <b> Extra service  </b> : This will be an additional service to monitor and another oppurtunity for bugs in the system. 
* <b> Latency </b> : Latency due to an extra hop in the.
    Mitigation: Deploy BFF in same cluster as other microservices and comunicate to them within the cluster. This will add very little rount trip time.