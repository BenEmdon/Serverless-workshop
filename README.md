# Serverless Computing Workshop
Intro to Serverless Computing workshop


## What is Serverless Computing?
Serverless computing is a cloud computing execution model where the cloud provider (ex. AWS) runs the server and dynamically manages the allocation of machine resources.

So *'Serverless'* still has servers, it's just the servers aren't managed by the developer.
Pricing is based on actual resources consumed, instead of pre-purchased units of capacity. 

You can think of Serverless computing as functions-as-a-service, since you are defining a function then paying for its number of executions and execution time.

### Advantages
#### Auto-Scaling
Let the service provider handle all of your scaling challenges. Serverless cloud providers will automatically handle any load of requests come your way. 

#### Pay-Per-Use
Typical servers are an inefficient use of money since you pre-purchase a capacity which will likely idle to some percent. For example, that Node.js server you have always running on Heroku will cost money even if it never receives a single request. On the other hand, a serverless solution will only cost money if receives a request.

#### Zero Administration
No need to go through all the hoops of provisioning a server, or managing your servers afterwards. Once you deploy, your code will live on and work forever (at least until your cloud provider dies). 
The result of this is that you will spend more time coding and less time configuring your server.

### Disadvantages 
#### Long running tasks
Serverless functions, while asynchronous are traditionally designed for short-running tasks. For example, default timeouts for AWS Lambda functions are only 60 seconds. Even when you extend the execution time, costs can be prohibitively high due to the cost per execution, over cost per hour of a dedicated instance.

This means by default long running tasks aren't well suited for serverless work, unless the individual steps of a workflow are separated into smaller, shorter running functions. This is also why serverless functions lend themselves well to state machines, which execute a number of individual tasks through a workflow depending on the result of previous states.

#### Testing
Traditionally tests are implemented at the integration and unit levels. Most test suites dockerize applications into a sanitized local testing sandbox. This is much more difficult with serverless functions since they can't be executed until they're deployed.

Potential solutions to this problem is mocking out the serverless environment using plugins like `serverless-offline` to emulate a local unit testing sandbox. For integration tests serverless functions can simply be deployed to an internal facing staging environment, similarly to how serverless functions would be deployed to production.
