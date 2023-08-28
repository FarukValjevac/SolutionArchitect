# AWS Serverless

## Elastic Beanstalk
Platform-as-a-service (PaaS)<br>
With AWS Elastic Beanstalk, you can quickly deploy and manage applications in the AWS Cloud without worrying about the infrastructure that runs those applications.

### Pro
- You simply upload your application, and AWS Elastic Beanstalk automatically handles the details of capacity provisioning, load balancing, scaling, and application health monitoring.
- CloudFormation in the background.
- Benefits of all CloudFormation features like creation of diagrams etc.
- CloudWatch included.
- S3 for backups included.
- Use AWS Elastic Beanstalk console.
- Deploy in multiple AZ possible.
- Manage multiple applications.

### Use Cases
- Quickly launch web applications.
- One region architecture.

---
<br>

## Lambda
With AWS Lambda, you can run code without provisioning or managing servers. You pay only for the compute time that you consume—there's no charge when your code isn't running. You can run code for virtually any type of application or backend service—all with zero administration. Just upload your code and Lambda takes care of everything required to run and scale your code with high availability.

### Pro
- Serverless functions.
- Edge functions.
- Cheap.
- Available for a lot od programming languages like Nodejs, Python, Java, C#, Go etc.
- Lambda runs your function in multiple Availability Zones to ensure that it is available to process events in case of a service interruption in a single zone.
- Recourses for functions up to 10GB of RAM.
- Will also improve CPU automatically.
- Use API Gateway in front of Lambda APIs to secure APIs.
- Use Lambda with multiple services.
- Lambda Container Images.

### Contra
- Don´t use Lambda when you API takes long time to process because you pay per request and execution time.

### Edge functions
Lambda@Edge is an extension of AWS Lambda that lets you deploy Python and Node.js functions at Amazon CloudFront edge locations.

### Pro
- Working with cache, much faster to bring content to end user.

![Lambda Edge](./draws/lambda-edge.png)

---
<br>

## AWS Amplify
Use AWS Amplify to develop and deploy cloud-powered mobile apps and web apps.

### Pro
- Connect your code from Github for example etc.
- Amplify is the Elastic Beanstalk for mobile and web apps.
- Host frontend with Amplify like React, Vuejs, Angular etc.

---
<br>

## Fargate
Fargate is a serverless compute engine for containers that allows you to run containers without managing the underlying infrastructure.

### Pro
- It's part of Amazon ECS (Elastic Container Service) and EKS (Elastic Kubernetes Service). Just upload the microservices and you dont need to manage Kubernetes yaml files.
- With Fargate, you define and deploy your containers, and AWS handles the provisioning and scaling of resources.
- It offers more control over container configurations compared to Elastic Beanstalk.

---
<br>

## Solution Architect Summary 😍

- <b>Elastic Beanstalk: </b>Quickly launch web applications with the whole infrastructure around for example backups, scaling, load balancing etc. everything is fully managed around your application. providing control over application environments and supporting multiple programming languages.

- <b>Lambda: </b>Use Lambda to run code without provisioning or managing servers. Lambda is also very cheap if you have fast APIs. Use Lambda Edge with CloudFront to deliver content very fast to the end user due to caching. Use Lambda for any functions like notification etc. be creative. 

- <b>Amplify: </b>Host frontend applications like Vuejs, Reac, Nextjs etc. fully managed like Beanstalk is doing with backend applications.

- <b>ECR: </b>Use Amazon Elastic Container Registry (ECR) when you need a fully managed Docker container image registry to store, manage, and deploy container images securely for your applications running on AWS.

- <b>Fargate: </b>Use Amazon Fargate when you want a serverless and fully managed compute engine for running containers without the need to manage underlying infrastructure, making it ideal for simplified container deployment and scaling.

- <b>AppRunner: </b>App Runner is a fully managed service for quick and easy deployment of web applications, abstracting complexities and providing automatic scaling.

- <b>EKS: </b>Amazon Elastic Kubernetes Service (Amazon EKS) is a managed service that makes it easy for you to run Kubernetes on AWS without needing to install and operate your own Kubernetes clusters.
