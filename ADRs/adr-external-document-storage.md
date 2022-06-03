# Title
Document storage system

## Status
proposed 

## Context
Spotlight platform has variety of usecases involving files and documents. For example
 * NP admin wants to engage with his/her community with help of a post involving an image. 
 * NP helps a candidate with resume review. 
 * Feed items with posts having images in them.
 Hence document storage and retrievals becomes a regular usecase for the platform.

### Alternatives
* Storing files on our file system
* Using a 3rd party cloud file system provider like AWS S3

### PrOACT

| Criteria      | Own file server | S3 | 
| ----------- | ----------- | ----------- |
| Time to build/integrate      | Very high       |low|
| Cost involved  | Build + maintain        | pay as you go | 
| Security implications | High | Low(taken care by provider)
| Maintainance and monitoring overhead | high   | no overhead| 
| Flexibility | high        | medium | low| 


## Decision
3rd party service provider for MVP saving cost and time. 

## Tradeoffs - Mitigations

* Latency 
    A file server/access point for every availability zone is not needed as performance is not a critical aspect. 

A possible mitigation strategy for  the above is to have CDNs or a caching mechanism that would cache frequently used media. This would solve use cases like
* A post receiving lot of traction which has a image need not fetch image from s3 and  can be served from cache. 
* In future if we want to support a low latency system, a file can be stored in region and can be served to other region through cdns.
