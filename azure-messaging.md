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
* 
## High availablility
* in case when one receiver down system will continue to process messages
