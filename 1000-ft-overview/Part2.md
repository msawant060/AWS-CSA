## Part 2. AWS Services Overview [Compute]

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
  
6. Amazon Lightsail
   - This is the simplest way to get started with AWS for small businesses, developers, students, and others who need a simple virtual private server (VPS) solution.
   - It provides:
    - Storage, networking capacity, compute capabilities 
   - It includes:
    - Virtualized computer server, DNS management, SSD-based storage, static IP address, and data transfer cpabilities. 
    - Preditable monthly price

7. AWS Batch
   - It enables users to efficently run hundreds of thousands of batch computing jobs on AWS. 
  

