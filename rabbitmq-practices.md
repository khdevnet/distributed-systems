### Terms
* ***producer*** is a user application that sends messages.      
* ***queue*** is a buffer that stores messages.      
* ***consumer*** is a user application that receives messages.      
* ***Message broker*** it accepts and forwards messages.     
* ***Exchange*** the producer can only send messages to an exchange. An exchange is a very simple thing. On one side it receives messages from producers and the other side it pushes them to queues. (direct, topic, headers and fanout)


### Best practice
* Manual message acknowledgments are turned on by default. 
Set autoAck ("automatic acknowledgement mode") parameter to false you will new manually aprove if message processed successfully. 
```
channel.BasicConsume(queue: "task_queue", autoAck: false, consumer: consumer);'
```

* Message durability
Two things are required to make sure that messages aren't lost: we need to mark both the queue and messages as durable.
We need to mark Producer and Consumer.
```
channel.QueueDeclare(queue: "hello",
```

Now we need to mark our messages as persistent - by setting IBasicProperties.SetPersistent to true
var properties = channel.CreateBasicProperties();
```
properties.Persistent = true;
```
The persistence guarantees aren't strong, but it's enough for simple task queue. 
If you need a stronger guarantee then you can use [publisher confirms](https://www.rabbitmq.com/confirms.html).

* Fair dispatch
For example in a situation with two workers, when all odd messages are heavy and even messages are light, one worker will be constantly busy and the other one will do hardly any work. 
Well, RabbitMQ doesn't know anything about that and will still dispatch messages evenly.
In order to change this behavior we can use the BasicQos method with the prefetchCount = 1 setting.
This tells RabbitMQ not to give more than one message to a worker at a time. 

```
channel.BasicQos(0, 1, false);
```

### Install RabbitMQ

* Install RabbitMQ via docker

```
docker run -d --hostname sw-rabbit-host --name sw-rabbit -p 8080:15672 -p 5672:5672 rabbitmq:3-management
```

* Enter Managment Admin
   http://localhost:8080
   username/passsword: guest/guest

### Resources
[RabbitMQ Tutorial](https://www.rabbitmq.com/tutorials/tutorial-two-dotnet.html)
