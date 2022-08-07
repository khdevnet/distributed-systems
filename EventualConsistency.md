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

 
Note:
- the complexity inside inventory boundary is abstracted from external boundaries (external boundary knows about event but it doesn't know that it sends from read model)
- changes notified to external boundary only after they heppend inside boundary
- by practices usually only aggregate in domain can send update event not read model.
- should be use for specific context.
- the everall time to update system time will increase
