# Title
Backend for frontend (BFF) with Graphql

## Status
proposed 

## Context
Following the [API standard decision](./adr-api-standard.md) the Spotlight apps would require to consume graphql APIs, but external consumer services would prefer Rest APIs to integrate with the platform. It is an infrastructure overhead for all the microservices to supports both the standards initially. A Backend for frontend is a service catered for frontend needs and can follow a different API standard (Graphql) from rest of the system. 

<b>Advantages of BFF pattern with Graphql</b>

* Solves problems of over fetching and underfetching. 
* Solve functional requirements which are different for UI from backend.
* The frontend client would only need to hit a single service to fetch aggregated data from multiple services, thus reducing the overall network overhead.
* If the frontend uses typescript, this service can be managed by the frontend developers. This gives them greater flexibility to complete the UI sooner without having to rely on the delivery of the underlying application APIs.

## Decision
Have a BFF service with Graphql API standard to make use of the above advantages.

## Tradeoffs - Mitigations

* **Single point of failure** : If BFF is not available the UI apps will not function.
    * Mitigation: Deploy BFF in multiple availability zones.
* **Extra service** : This will be an additional service to monitor and another oppurtunity for bugs in the system. 
* **Latency** : Increased latency due to an extra hop to fetch simple (non-aggregated) data.
  * Mitigation: Deploy BFF in same cluster as other microservices and comunicate to them within the cluster. This will add very little rount trip time. Also, BFF pattern is most effective when a page / widget on the app needs aggregated data from multiple services. 

## References
https://www.infoq.com/presentations/graphql-bff/
https://www.mobilelive.ca/blog/why-backend-for-frontend-application-architecture#:~:text=Backend%20For%20Frontend%20(BFF)%20architecture,%2C%20and%20native%2Dmobile%20apps.
