## Quanta Identification

The team collaboratively performed an event storming + actor action exercise to identify the aggregates.

![Image](../images/aggregate-identification.jpg)

The aggregates were then grouped to identify services. Services with synchronous dependencies were identified to identify quanta.

![Image](../images/quanta-identification.jpg)


### Quanta - Services

* NPO-Candidate
  * NPO Service
  * Candidate Service
  * Assignment Service
  * Assignment Scheduler
  * Auth Service
* Chat
  * Chat Service
* Notification 
  * Notification service
  * Email Service
  * 3rd Party Notification systems (for push and in-app notifications)
  * SMS 
* Meeting
* NPO-Integration
* Recommendation
* Documents
* Chat