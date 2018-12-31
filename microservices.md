# Microservices
Is an architectural style that structures an application as a collection of services.

## Antipatterns
* Start develop application with microservices architecture     
S: Start app with monolithic architecture and then extract microservices 
* Don't care about database schemas, use one schema for several microservices.   
S: Use independed microservices with they own database migrations, use one database per microservice if possible.
* Don't use semantic versioning for (APIs, Messages, Libraries)
S: Use API, Messages, Libraries versioning make deployment independed, it shouldn't crash full system.
* Don't mesure how much computer resources are you need to have stable sytem, don't recognize botlenecks    
S: Use measurement tools, use Message queues to normilize load during critical load between microservices. 
* Hardcode IPs and ports in independent microservice     
S: Use discovery services approach (Consul, etcd) it help you service to find correct url to dependent service and change them remotely.     
S2: Use centralized router system (use domain instead of IPs) router system responsible for IPs dependencies.
* Don't use health checks for microservices with retry
S: Use helthcheck with retry to give depentent microservice time for self recovering.
* Don't think about global logging and debugging process, have logging per microservice only.
S: Use ELK stack, mark operation with unique ID to make possible to investigate full flow of the operation.
* Don't think about way how to run microservice independent on developer environment.
S: Use mocks to run microservice independent, mock should be provided by team who created dependent microservice.
* Flying Blind or don't use graphs and statics about your system status, don't use notifications about errors. 
* Don't use same environment for each your microservice, use different deployment configurations for microservices    
S: Choose one environment and deploy strategy, use it for all microservices for example kubernetes with docker.
* Don't have enough automation for CI/CD
S: Automate everything as possible.
* Don't have single storage for all microservices configurations.
S: Store all configs in one place, make it possible to change concreate microservice configuration from one place.
* Don't have good documentation 

## Single microservice best practice
* Use Automation API schemas builders for example Swagger.
* One microservice one database or independent database scheme.
* Use versioning for APIs, Messages, libraries.
* Write integration, Unit Tests.
* Use health checks for dependent services.
