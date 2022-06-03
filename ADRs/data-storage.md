# Title

Data Storage

## Status

proposed

## Context

With the growth of Microservices, Cloud, Distributed Applications, Global Scaling, and Semi-Structured Data, it is more vital than ever to select a database since it affects the entire performance and cost of the system.

### Alternatives

- RDBMS
- NoSQL

### PrOACT

| Criteria                       | RDBMS  | NoSQL |
| ------------------------------ | ------ | ----- |
| Schema Flexibility             | Low    | High  |
| Scalability                    | Medium | High  |
| Availability                   | Medium | High  |
| Data Consistency               | High   | Low   |
| Write Performance Requirements | Low    | High  |
| Cost                           | High   | Low   |

## Decision

- We choose NoSQL over RDBMS since we can achieve great scalability and schema flexibility with it.
- When compared to RDBMS, NoSQL has a lower cost.

![Image](../diagrams/cap-theorem.jpg)

## Tradeoffs - Mitigations

- The data consistency can be an issue with NoSQL

## Reference

- https://datawarehouseview.wordpress.com/tag/cap-theorem/
