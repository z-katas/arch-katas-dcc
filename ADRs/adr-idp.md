# Title
Identity Provider (IdP)

## Status
proposed 

## Context
Identity and access control is a critical piece of the spotlight app since it will be part of every usecase for the user, However building a robust identity management system comes with its own challenges around security,compliance, management and monitoring.

### Alternatives
* Building an identity service in-house.
* Using an open source self hosted identity platforms like Keycloak, Apache LDAP
* Using a fully managed 3rd party identity platform like Auth0, Okta.



### PrOACT 

| Criteria      | Self built identity service | Self hosted,pre-built identity platform | 3rd party platform | 
| ----------- | ----------- | ----------- | ----------- 
| Time to build/integrate      | Very high       |low| low
| Cost involved  | Build + maintain | maintain | pay as you go| 
| Maintainance and monitoring overhead | high        | high | no overhead| 
| Flexibility | high        | medium | low| 


## Decision
**Leverage 3rd party fully managed identity solutions**
Building or managing an identity service is expensive and adds overhead of security and compliance. Using a 3rd party vendor will enable a faster go-to market and allows engineering teams to focus on the key valye proposition of the product. The pay as you go plans which are available with most of the vendors will save the cost and overhead of developing, monitoring and maintaining other options.

## Tradeoffs - Mitigations
Choosing a 3rd party vendor will limit us to build for capabilities it does not offer. 

Possible mitigation is to have a wrapper service around this vendor that would 
* behave as an identity facade for the rest of the system
* Build capabilities that identity provider does not support 
