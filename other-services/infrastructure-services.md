## Infrastructure Components

Components falling under this group are
* API Gateway
* Sidecar logger
* Metrics collector
* Monitoring and Alerting systems

These services handle the infrastructure and operational needs of the platform. 



### API Gateway Responsibilities
1. Route the traffics to respective microservices in the systems.
2. Authenticate the incoming requests.
3. Add a request-id header to incoming requests for traceability.

### Sidecar Logger Responsibilities
1. Collects logs from the pods and push them to a central log repository

### Metrics collector Responsibilities
1. Collect metrics for the entire platform, these metrics include 
    * No. of API requests
    * Success and failure rates
    * Response times
2. Store the metrics in a time-series database

### Monitoring and Alerting systems

1. Dashboards for monitoring the services.
2. Alerting mechanisms in case of service downtime/failures


### References
https://medium.datadriveninvestor.com/simple-way-to-stream-kubernetes-logs-with-sidecar-pattern-5240ee88e8f0

