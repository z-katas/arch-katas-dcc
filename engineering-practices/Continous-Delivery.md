# Continuous Delivery
Continuous delivery is an extension of continuous integration since it automatically deploys all code changes to a testing and/or production environment after the build stage. 


## Continuous Delivery Practices

* Features are smoke tested(automation tests) in lower environments before promoting to higher environments.
* Code is built only once and deployed to many environments ensuring the same build is shipped, reducing disparity in environments.
* Feature flags are present to hide features that are not intended to be released in an environment.


## References
https://www.atlassian.com/continuous-delivery/principles/continuous-integration-vs-delivery-vs-deployment