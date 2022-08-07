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
in example "availableSizes" already contains information what producer can use, producer doesn't need to make request to consumer to get latest information 
