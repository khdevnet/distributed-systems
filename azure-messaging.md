# Azure message systems
## Azure service bus
Durable brokered messaging Point-to-point messaging 
Publish subscribe messaging
Enterprise messaging functionality
Cost-efficient

## Event hub
Large-scale telemetry ingestion
Buffered storage
Massively scalable

## Event grid
HTTP event routing and delivery
Near real-time notifications
Supported by many Azure services

## Relay Service
Securely exposes on-premises services
Endpoint “in the cloud”
Relays request and response calls

## Storage Queues
Simple point-to-point messaging
Very cost-effective
Limited functionality


# Asynchronus scenarious
## Connectivity Challenges – Asynchronous Processing
* process highly variable load and do not disturb web application
* process messages during not stable connections

## Load leveling
* play role of the buffer between sender and receiver
* process requests when receiving application can process less load then system generate

## Load balancing
* split processing between several receivers

## High availablility
* in case when one receiver down system will continue to process messages

## Temporal decoupling
* messages can be send in one time and process later in time
* receiver can work only couple hours per day and process messages

# Service bus broker

* Publish-subscribe: Messages can be broadcast to multiple receivers based on routing rules in the messaging entities.
* Dead-lettering: Invalid or poison messages can be moved to a dead-letter queue.
* Message Sessions: Related messages can be grouped together in sessions and processed together.
* Request-response Correlation: Response messages can be correlated with the appropriate request messages to allow for asynchronous two-way communication.
* Message Deferral Messages: can be preserved on a messaging entity and retrieved later for processing.
* Scheduled Enqueue Time Messages: can be sent to a messaging entity and then enqueued at a specified time.
* Duplicate Detection Duplicate messages: can be ignored by a messaging entity.
* Message Expiration Messages: can be configured to expire after a specified duration.
