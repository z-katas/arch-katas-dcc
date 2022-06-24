# Upload to 3rd party cloud storage directly from the web or mobile application
2022-06-23

## Status
Accepted 

## Context
The [document quanta](../quanta/document.md) is responsible for storing and retrieving documents in the spotlight platform. Question arises 

### Alternatives
* Uploading to cloud storage via document service 
* Uploading directly to 3rd party cloud storage provider from frontend

### PrOACT

| Criteria      | via Document Service | Directly to cloud storage | 
| ----------- | ----------- | ----------- |
| Time to build/integrate      | Very high       |minimal|
| Cost involved  | Build + maintain        | pay as you go | 
| Reliability | Low - because service memory will bloat un predictably based on size of document uploaded | High|
| Maintenance and monitoring overhead | high   | no overhead| 
| Latency | high        | medium / low |
| Security | high - because authN and authZ would be there  on document service  | low |


## Decision
Uploading directly to 3rd party cloud storage provider from frontend

## Tradeoffs - Mitigation Strategies
* Uploading directly to 3rd party cloud storage provider from frontend may pose security risk of users uploading malicious files (too large, invalid formats, etc.) and retrieving files without sufficient authorizations.
  * Mitigation - Use presigned or short-lived URLs to upload/retrieve files to/from 3rd party cloud storage provider. One can specify the file size, format, validity, etc. in the URL. 


## References
* https://aws.amazon.com/blogs/compute/uploading-to-amazon-s3-directly-from-a-web-or-mobile-application/
