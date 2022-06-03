# Observability and Monitoring

Each service of the system should produce appropriate data to support detection and alerting. Each service should be an observable. 

It is the responsibility of each service to

* Perform health checks
* Generate Metrics
* Log entries
* Request tracing 



To achieve the above it is recommended to follow the [sidecar pattern](./sidecar-pattern.md)


## References
https://cloud.ibm.com/docs/java?topic=cloud-native-observability-cn