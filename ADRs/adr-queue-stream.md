# Choosing Message queue vs Event stream

## Status
Accepted 

## Context
Spotlight platform being an event driven system, queue/stream becomes a vital component of the architecture. Platform would need a long term reliable solution to scale for its use cases and build an event sourcing system.

### Alternatives
* Message queue
* Event streams


### PrOACT 

| Criteria      | Message queue | Event stream | 
| ----------- | ----------- | ----------- | ----------- 
| Reliability      | low       |High, order is preserved
| Delivery count | once | every consumer have their offset  
| Retention | no retention of messages       | retained for a certain period | 
| Cost | low        | high | 
Maintenance overhead | high | less|

## Decision
**Event stream**
considering use cases of spotlight platform with use cases of event to be delivered to multiple services (one such example is event candidate_ assignment_updated would be subscribed by candidate service and store the event for analytics ) which would not be offered by a message queue. 
