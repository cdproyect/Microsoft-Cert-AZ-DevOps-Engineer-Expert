# Azure Functions

## Serverless compute

Serverless compute can be thought of as a function as a service (FaaS), or a microservice that is hosted on a cloud platform. Your business logic runs as functions and you don't have to manually provision or scale infrastructure. The cloud provider manages infrastructure. Your app is automatically scaled out or down depending on load. Azure has several ways to build this sort of architecture. The two most common approaches are Azure Logic Apps and Azure Functions, which we'll focus on in this module.

### Drawbacks of a serverless compute solution

- Execution time, default 5 minutes, configurable up to 10 minutes max. Additional if your service is initiated through an HTTP request and you expect that value as an HTTP response, the timeout is further restricted to 2.5 minutes.
- Execution frequency, if you expect your function to be executed continuously by multiple clients, it would be prudent to estimate the usage and calculate the cost of using functions accordingly.

## Function app

Functions are hosted in an execution context called a function app. You define function apps to logically group and structure your functions and a compute resource in Azure.

### Choose a service plan

Function apps may use one of two types of service plans:

- Consumption plan
- Azure App Service plan

When using the Azure serverless application platform, choose the Consumption plan. This plan provides automatic scaling and bills you only when your functions are running. The Consumption plan comes with a configurable timeout period for executing a function. By default, it's five (5) minutes, but may be configured to have a timeout as long as 10 minutes.

The Azure App Service plan enables you to avoid timeout periods by having your function run continuously on a VM that you define. When using an App Service plan, you are responsible for managing the app resources the function runs on, so this is technically not a serverless plan. However, it may be a better choice if your functions are used continuously, or if your functions require more processing power or longer execution time than the Consumption plan can provide.

Functions require a storage account for store internal operations, such as logging function executions and managing execution triggers. On the Consumption plan, this is also where the function code and configuration file are stored.

### Triggers

Functions are event driven, which means they run in response to an event. The type of event that starts a function is called a trigger.

Azure supports triggers for the following services.

| **Service** | **Trigger description** |
| - | - |
| Blob Storage | Starts a function when a new or updated blob is detected.
| Azure Cosmos DB | Start a function when inserts and updates are detected.
| Event Grid | Starts a function when an event is received from Event Grid.
| HTTP | Starts a function with an HTTP request.
| Microsoft Graph Events | Starts a function in response to an incoming webhook from the Microsoft Graph. Each instance of this trigger can react to one Microsoft Graph resource type.
| Queue Storage | Starts a function when a new item is received on a queue. The queue message is provided as input to the function.
| Service Bus | Starts a function in response to messages from a Service Bus queue.
| Timer | Starts a function on a schedule.

### Bindings

A binding is a declarative way to connect data and services to your function. Bindings interact with various data sources, which means you don't have to write the code in your function to connect to data sources and manage connections--the platform takes care of that complexity for you as part of the binding code. Each binding has a direction--your code reads data from input bindings, and writes data to output bindings. Each function can have zero or more bindings to manage the input and output data processed by the function.

A trigger is a type of input binding that has the ability to initiate execution of some code.

Azure provides a [large number of bindings](https://docs.microsoft.com/en-us/azure/azure-functions/functions-triggers-bindings#supported-bindings) to connect to different storage and messaging services.

Here is an example:

```json
{
  "bindings": [
    {
      "name": "order",
      "type": "queueTrigger",
      "direction": "in",
      "queueName": "myqueue-items",
      "connection": "MY_STORAGE_ACCT_APP_SETTING"
    },
    {
      "name": "$return",
      "type": "table",
      "direction": "out",
      "tableName": "outTable",
      "connection": "MY_TABLE_STORAGE_ACCT_APP_SETTING"
    }
  ]
}
```

## Function Templates

When you create a function from a template, several files are created, including a configuration file, function.json, and a source code file, index.js.
