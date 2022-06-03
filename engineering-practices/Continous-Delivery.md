# Continous Delivery
It is an extension of continous integration since it automatically deploys all code changes to a higher branch.


## Continous Delivery Practices

* Code is smoke tested(automation tests) in lower environments and then promoted to higher environment.
* Code is built only once and deployed to many environments ensuring same build is shipped reducing parity in enviroments.
* Feature flags are present to hide features which are not intended to be released in an environment


## References
https://www.atlassian.com/continuous-delivery/principles/continuous-integration-vs-delivery-vs-deployment