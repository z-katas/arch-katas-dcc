# Title
Document storage system

## Status
proposed 

## Context
Spotlight platform has a variety of use-cases involving files and documents. For example
 * NP admin wants to engage with his/her community with the help of a post involving an image. 
 * NP helps a candidate with resume review. 
 * Feed items with posts having images in them.
 Hence, document storage and retrievals has become a regular use-case for the platform.

### Alternatives
* Storing files on our file system
* Using a 3rd party cloud file system provider like AWS S3

### PrOACT

| Criteria      | Own file server | S3 | 
| ----------- | ----------- | ----------- |
| Time to build/integrate      | Very high       |low|
| Cost involved  | Build + maintain        | pay as you go | 
| Security implications | High | Low(taken care of by provider)
| Maintenance and monitoring overhead | high   | no overhead| 
| Flexibility | high        | medium | low| 


## Decision
3rd party service provider for MVP saving cost and time. 

## Tradeoffs - Mitigations

* Latency 
    A file server/access point for every availability zone is not needed as performance is not a critical aspect. 

A possible mitigation strategy for the above is to have CDNs or a caching mechanism that would cache frequently used media. This would solve use cases like
* A popular post with an image does not need to fetch the image from S3 and can instead be served from cache. 
* In the future, if we want to support a low latency system, a file can be stored in a region and can be served to other regions through CDN.
