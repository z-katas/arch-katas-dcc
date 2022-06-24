# Green field projects - Build vs Buy 
Date: 2022-06-23

## Status
Accepted 

## Context
Greenfield projects are ambiguous and risky. Shorter **feedback loop** and less **go to market** time play a key role. So, it becomes essential to invest the engineering efforts in features/verticals which contribute to the core value proposition of the product. 

### Alternatives

* Build in house
* Buy from 3rd party vendors

Factors contribution to the decision :
* How close to the core value proposition is this functionality?
* Does it provide a competitive advantage?
* What option preserves simplicity?
* What’s the fastest go-live way?
* Does the team have core competency to build this?
* What’s the cost of building and buying? 


## Decision
* We plan to buy the services such as auth, document storage, chat, notifications (in-app, push, etc.) and focus on building core features of the platform.


## Tradeoffs - Mitigation Strategies

* Flexibility and customizability around the features we buy is going to be less. 
  * A mitigation strategy for the above is having a wrapper service that would serve the missing and needed functionality.


