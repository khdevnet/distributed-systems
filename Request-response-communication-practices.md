# Request response integrations
## Handling External events
Note: events what send to your systems from other systems
Integration with external systems
External system events handling (Webhook implementation), it possible to expose stream outside of you application but it could lead to security isues and additional configurations.

## Autonomusly generated events
metrics or mesurments of the system
You can send analytic metrics (60s of video watched) from client using synchronus request, this data not critical, yuo can transform it to event on server side. 

## Reactively generated events 
when you need only to know that system accepted your request (202 status code), and it will handle your request. 
For example fire and forget, send an email http request.
Payment system could return transaction id, what could be use to track status of operation


# Patterns
## Transform http request to event and send it
API services received synchronus http request and then transform it to event, this event could be route to proper stream
## Transform event to http request
Service consumes an event then send http request to external system, process response and send event with result 
Note: 
* external system should properly process retries (result could be different from what you expect when send it originally)
* If have many unprocessed messages and want them to process, external system could start to throttle them 

## Read data from materialized view or readonly datasource
service could have readonly cache what updated eventually, client get read data from this cache using http request

# Resources
* book-building-event-driven-microservices, 13. Integrating Event-Driven and Request-Response Microservices.pdf
