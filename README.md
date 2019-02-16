# Serverless Computing Workshop
Intro to Serverless Computing workshop


## What is Serverless Computing?
Serverless computing is a cloud computing execution model where the cloud provider (ex. AWS) runs the server and dynamically manages the allocation of machine resources.


So *'Serverless'* still has servers, it's just the servers aren't managed by the developer.
Pricing is based on actual resources consumed, instead of pre-purchased units of capacity. 

You can think of Serverless computing as functions-as-a-service, since you are defining a function then paying for its number of executions and execution time.

### Advantages
#### Auto-Scaling
Let the service provider handle the scaling challenges. Serverless providers will automatically whatever load of requests come your way. 

#### Pay-Per-Use
Typical servers are an inefficient use of money since you pre-purchase a capacity which will likely idle to some percent. For example, that Node.js server you have always running on Heroku will cost money even if it never receives a single request.

#### Zero Administration
No need to go through all the hoops of provisioning a server, or managing your servers afterwards. Once you deploy, your code will live on and work forever (at least until your cloud provider dies). 
Spend more time coding and less time configuring your server.

### Disadvantages 

