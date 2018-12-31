# Microservices
Is an architectural style that structures an application as a collection of services.

## Antipatterns
* Start application with microservices architecture     
S: Start app with monolithic architecture and then extract microservices 
* Don't care about database schemas, use one shema for several microservices.   
S: Use independed microservices with they own database migrations, use one database per microservice if possible.
* Don't use semantic versioning for (APIs, Messages, Libraries)
S: Use API, Messages, Libraries versioning make deployment independed, it should crash full system.
* Don't mesure how much computer resources are you need to have stable sytem, don't recognize botlenecks    
S: Use measurement tools, use Message queues to normilize load during critical load between microservices. 
* Hardcode IPs and ports in independent microservice     
S: Use discovery services approach (Consul, etcd) it help you service to find correct url to dependent service and change them remotely.
   Use centralized router system (use domain instead of IPs) router system responsible for IPs dependencies.
