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

#### NP(Non-Profit) - Service

##### Responsibilities
  1. Register Non-Profit organization to the platform
  2. Profile Creation/Completion of the Non-Profit organization
  3. Non-Profit program management
  4. Managing partnership with other Non-Profit organization
  5. Non-Profit assignment creation
  6. Platform Role based training is assigned to new Non-Profit

##### Architectural Characteristics
  1. Scalability 
        As the non-profit organization increses in number, the over-all performance of system should be consistance
  2. Availability  
        The system has to be highly available so that the onboarding process is smooth
  3. Testability

#### Candidate - Service

##### Responsibilities
  1. Register Candidate to the platform
  2. Profile Creation/Completion of the Candidate
  3. Uploading the road map of the candidate
  4. Assigment creation for the candidate
  5. Tracking candidate progress
  6. Invite to the community meetings (Should this be handle by eventing service)
  7. Program enrollment of the candidate 
  8. Taking feedback from the candidate.

##### Architectural Characteristics
  1. Interoperability  
        The service communicates with external system to track candidate progress and enroll the candidate to program 
  2. Scalability  
        With increase in the number of candidate ,the over-all performance of system should be consistance
  3. Testability  

#### Admin Services

##### Responsibilities
  1. New Non-Profit is invited to monthly community meetings
  2. Community leader assigment to the Non-profit organization
  3. Role based training is assigned to new Non-Profit
  4. Assignment of the mentor to the candidate
  5. Assigment creation for the candidate

##### Architectural Characteristics
  1. Testability


## Architectural Style

### Logical View

### Component View


## Design Principles
