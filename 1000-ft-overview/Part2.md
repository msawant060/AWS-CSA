## Part 2. AWS Services Overview

### Compute
A variety of products and services that provide scalable computing capacity in cloud. 
1. Amazon Elastic Compute Cloud (EC2)
   - This includes the virtual servers, called instances, in the cloud
   - Cutomers can choose more than 30 varities of instances 
   - CPU Intensive, Memory Intensive, Accelerated Computing Optimized as in GPU, Storage intensive. 

2. Amazon EC2 Auto Scaling
   - This helps in automatically scaling Amazon EC2 instances up and down as per the policies you define (various matric and health check). 
   - It ensures that you're always running with the desired number of instances 
   - Comnine Amazon EC2 and EC2 Auto Scaling, you can create a high available architecture. 
   
3. AWS Lambda
  - AWS lambda allows you to run code without provisioning or managing any servers or infrastructure.
  - This code can be a back-end service, trigger this function in event triggers, and so on.
 
4. Amazon EC2 Container Service (ECS)
  - It allows you to run Docker containers on Amazon EC2 instances.
  - Amazon ECS integrates with ELB, and Amazon EBS.

5. Amazon Elastic Beanstalk
  - It lets you run and manage web applications without worriying about the underlining infrastructure 
  - You can use Amazon ECS to deploy web applications with Java, .NET, PHP, Node.js, Python, Ruby, Go, and Docker on servers such as Apache, Nginx, and so on..
  

1. AWS Region is a physical, geographical area or location. Each Region is completely independent. 
2. This achieves the greatest possible fault tolerance and stability.
3. Each Region has multiple (2 or more), isolated locations known as Availability Zones (AZ).
4. Each Availability Zone is isolated, but the Availability Zones in a Region are connected through low-latency links.

### Available Region

1. Your AWS account determines the Regions that are available to you
   - An AWS account provides multiple Regions so that you can launch Amazon EC2 instances in locations that meet your requirements. 
   - Ex: You might want to launch instances in Europe to be closer to your European customers or to meet legal requirements.
2. An AWS GovCloud (US-West) account provides access to the AWS GovCloud (US-West) Region only
3. An Amazon AWS (China) account provides access to the Beijing and Ningxia Regions only.

### Availability Zones (AZ)

1. AWS Availability Zones are one or more discrete data centers.
2. Each with redundant power, networking and connectivity housed in separate facilities. 
3. Deploying your application across multiple Availability Zones is useful for redundancy, low latency and fault tolerance.

### Edge Locations
1. AWS Edge Locations are locations around the world meant for caching content, enhancing the user experience, reducing latency. 
2. Edge locations are specifically used by AWS Cloudfront and AWS CDN. 
3. Every Region is has its own set Availability Zone's and Edge Locations.
