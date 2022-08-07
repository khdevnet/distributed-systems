## how to solve the challenge of fetching stale data from eventually consistent read model 
### Design event schema with consumer needs in mind
Best practice for event to be small and well grained, but for real word application it could be benefitial to have event schema with additional fields,
which will contain calculated data for consumer base on producer data.
```json
{
  "productId": 1,
  "qty": 1,
  "size": "xs",
  "availableSizes": {
    "xs": 2,
    "xxl": 1
  }
}
```
in example "availableSizes" already contains information what producer can use, producer doesn't need to make request to consumer to get latest information.
## Change order of events, consumer consume an event only after read model was updated

<img src="https://user-images.githubusercontent.com/14298158/183286006-d926913d-cb77-41c9-be9e-9babd44a8dc9.png" width="250">

- the complexity inside inventory boundary is abstracted from external boundaries (external boundary knows about event but it doesn't know that it sends from read model)
- changes notified to external boundary only after they heppend inside boundary
- by practices usually only aggregate in domain can send update event not read model.
- should be use for specific context.
- the everall time to update system time will increase

## Handling eventual consistency delays using event versioning 
- if the version of event were higher then the version of the API, the service would need to retry the request. THis means the service didn't reflect the changes in the event on the read model yet.
- when a request fetches stale data, it can react to it with a retry (retry should be an exception and not a usual situation)
- the implementation should have a circuit breaker and a backoff strategy.
- retrying is the symptom of the lack of a more sustainable approach; we should use it wisely and sparingly 

## Saving state in microservice to avoid synchronous calls
- should be use wisely, becuase several copies of data could spread throughout the architecture and wil be hard to maintain 

## Bufering state in memory of the service
- could be use for request intensive applications
- could read all events from topic at start, and then continue consume events from the topic
- can be use for small amount of data
- load data on service start



