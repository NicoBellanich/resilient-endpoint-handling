# resilient-endpoint-handling

### Broken API

There is an app that not always works ok (as may happen in real production enviroment)
May respond: error status, with high response time, wrong internal data (like unexisting dates) , or some thimes ok status

### To-Do

Implement some resilient architecture for handling this API responses.
The idea is to focus on scalability and reliability and response time. 
Data reached do not need to be consistent with failing api at the moment.
In future may extend to other API clients (broken or not)

### Arhcitectre

- job that trigger searching in Broken-API
- handlear that manage providers
- publisher that publish over topic
- RabbitMQ
- consumer that hears topic and write on database
- API that hits database and looks for feteched data 
