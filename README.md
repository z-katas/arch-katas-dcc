# Spotlight Platform

## Prelude

## Golden Path

### Candidate Flow

### Non-Profit Flow

## Requirement Analysis



## Assumptions

## Identifying Architectural Quanta

### Event Storming

### Quantum - Responsibilities and Architectural Characteristics

#### Auth Service

##### Responsibilities
  1. Identity and access control 
  2. Manage user profiles. 
  3. Integration with a 3rd party identity provider. 

##### Driving Architectural Characteristics
  1. Feasibility 
        Given the usecase we would want this service to be feasible with respect to cost and time. 
  2. Fault tolerance  
        This service will be the front gate for the system as it takes care of user sessions, we would want this service to be up at all times
  3. Scalability
        Service has to be scalable to growing requests 

#### Documents - Service

##### Responsibilities
1. Compress the files and store files efficiently in the file system.
  2. Serve files like pdfs, images for all the system's capabilities to a 3rd party file system.
  3. Cache the frequently used files using CDNs.


##### Driving Architectural Characteristics
  1. Recoverability  
        In case of disasters we would not want the service to loose the storage and be up and running eventually
  2. Responsiveness  
        Respond to document requests as quickly as possible
  3. Scalability
        Scale for the growing amount of users and traffic of the system. 

#### Matching Services

##### Responsibilities
  1. Recommends communities and NPO's to the candidates based on offerings and testimonials.
  2. Recommends Programs that candidate can enroll into
  3. The service learns based on the feedback of previous recommendations and continues to improve as the system grows. 

##### Driving Architectural Characteristics
  1. Adaptability
      The system continues to adapt to growing requirements and varieties of users/communities it onboards. 
  2. Data integrity
      The accuracy of matches is really crucial increasing the user engagement and value proposition of the platform
  3. Scalability
      Scale the matching algorithm and workflow to ever growing platform users.

#### Notifications Service

 ##### Responsibilities
  1. Send in-app and push notifications to users, this will increase the usability of the app.
  2. Saves user's preferences about type and frequency of notifications they would like to be subscribed to.
  3. Notify users via emails.
  4. Integrate with 3rd party notification and email providers. 
  4. Enable users to send and notify user(s) through emails and notifications


##### Driving Architectural Characteristics
  1. Concurrency
      The system need to be concurrent enough to notify users and user groups about different subjects at same time.   
  2. Data integrity
      Correctness or emails and notifications is highly important as they would be misleading otherwise. 
  3. Availability
      Service should be highly available so that users do not miss on anything. 
##### Characteristics which we do not need as we offloaded to 3rd party vendors
  1. Security 
      Security around emailing service will be a responsibility of the emailing vendor.
  2. Scalability and Availability  
      The notification provider should be highly scalable and available at the same time


## Architectural Style

### Logical View

### Component View


## Design Principles