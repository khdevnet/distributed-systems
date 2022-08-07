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

<img src="https://user-images.githubusercontent.com/14298158/183285747-c68b8e28-2a30-49c5-b5a8-c33eeb3993e3.png" width="250">

Note:
- by practices usually only aggregate in domain can send update event not read model.
- should be use for specific context.
- the everall time to update system time will increase
