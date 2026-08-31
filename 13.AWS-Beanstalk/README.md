## AWS Beanstalk: 

AWS **Elastic Beanstalk** (EB) is a fully managed Platform as a Service (PaaS) from AWS that makes it easier to deploy, manage, and scale web applications without manually managing all the underlying AWS infrastructure.

You upload your application code, and Elastic Beanstalk automatically handles much of the infrastructure setup, including **EC2**, **Auto Scaling**, **Load Balancer**, **CloudWatch monitoring**, and **deployment configuration**.




### Why use Elastic Beanstalk?

_Normally, deploying a web application on AWS might require you to configure:_
```
VPC
 ├── Subnets
 ├── Route Tables
 ├── Internet Gateway
 ├── Security Groups
 ├── EC2
 ├── Auto Scaling
 ├── Load Balancer
 └── CloudWatch
```


_With Elastic Beanstalk:_
```
Your Application
       │
       ▼
Elastic Beanstalk
       │
       ├── EC2
       ├── Auto Scaling
       ├── Load Balancer
       ├── Security Groups
       ├── CloudWatch
       └── Deployment
```



### Elastic Beanstalk vs EC2:

| Feature                | EC2                    | Elastic Beanstalk      |
| ---------------------- | ---------------------- | ---------------------- |
| VM management          | You manage             | Beanstalk helps manage |
| OS configuration       | Manual                 | Mostly automated       |
| Application deployment | Manual/your tooling    | Built-in               |
| Auto Scaling           | Configure yourself     | Easy configuration     |
| Load Balancer          | Configure yourself     | Can be managed         |
| Monitoring             | Configure              | Integrated             |
| Infrastructure control | Very high              | Medium                 |
| Ease of deployment     | More work              | Easier                 |
| Best for               | Infrastructure control | Application deployment |




### Core Concepts: 

Elastic Beanstalk organizes application deployments using three distinct logical abstractions:

- **Application**: A logical container for your entire project, including environments and deployable code versions.
- **Environment**: A collection of active AWS resources running a specific application version (available as Web Server or Worker tiers). 
- **Platform**: A pre-configured combination of an operating system, language runtime, and web server.



### Elastic Beanstalk supports two environment tier:

- **Web Server Environment**: 
    - Run a website, web application, or web API that serves HTTP requests.
    - Processes HTTP requests from users and is commonly used for web applications.

- **Worker Environment**: 
    - Run a worker application that processes long-running workloads on demand or performs tasks on a schedule.
    - Processes background tasks asynchronously using Amazon SQS queues.




### Supported Platforms:

Elastic Beanstalk supports several application platforms, including:

- Java
- .NET (Linux and Windows)
- Node.js
- PHP
- Python
- Ruby
- Go
- Docker
- Tomcat 



---
---


