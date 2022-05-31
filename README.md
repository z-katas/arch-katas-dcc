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

#### 1. NP(Non-Profit) - Service

##### Responsibilities
  1. Register Non-Profit organization to the platform
  2. Profile Creation/Completion of the Non-Profit organization
  3. Non-Profit program management
  4. Managing partnership with other Non-Profit organization

##### Architectural Characteristics
  1. Scalability 
        As the non-profit organization increses in number, the over-all performance of system should be consistance
  2. Availability  
        The system has to be highly available with no to low downtime
  3. Testability

#### 2. Candidate - Service

##### Responsibilities
  1. Register Candidate to the platform
  2. Profile Creation/Completion of the Candidate
  3. Uploading the road map of the candidate
  4. Tracking candidate progress
  5. Program enrollment of the candidate 
  6. Taking feedback from the candidate.
  7. Take feeback on the candidate
  8. Pull data from linkedIn

##### Architectural Characteristics
  1. Interoperability  
        The service communicates with external system to track candidate progress and enroll the candidate to program 
  2. Scalability  
        With increase in the number of candidate ,the over-all performance of system should be consistance
  3. Testability  

#### 3. Assignment Services

##### Responsibilities
  1. Role based training is assigned to new Non-Profit
  2. Create assigment for the Non-profit organization
  3. Create assigment for the candidate
  4. Assigning mentor to the candidate 
  5. Assigning community leader to the Non-profit organization

##### Architectural Characteristics
  1. Testability
  2. Availability
  3. Workflow


## Architectural Style

### Logical View

### Component View


## Design Principles
