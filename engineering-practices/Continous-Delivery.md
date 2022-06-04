# Continuous Delivery
It is an extension of continuous integration since it automatically deploys all code changes to a higher branch.


## Continuous Delivery Practices

* Code is smoke tested(automation tests) in lower environments and then promoted to higher environments.
* Code is built only once and deployed to many environments ensuring the same build is shipped, reducing parity in environments.
* Feature flags are present to hide features that are not intended to be released in an environment


## References
https://www.atlassian.com/continuous-delivery/principles/continuous-integration-vs-delivery-vs-deployment