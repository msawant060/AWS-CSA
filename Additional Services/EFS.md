## Amazon Elastic File System

### What Is Amazon Elastic File System?
  - Amazon Elastic File System (Amazon EFS) provides simple, scalable file storage for use with Amazon EC2
  - With Amazon EFS, storage capacity is elastic, growing and shrinking automatically as you add and remove files, 
    so your applications have the storage they need, when they need it
  - Amazon EFS supports the Network File System version 4 (NFSv4.1 and NFSv4.0) protocol
  - With Amazon EFS, you pay only for the storage used by your file system and there is no minimum fee or setup cost.
  - This link has pricig calculation: https://aws.amazon.com/efs/pricing/
  - Amazon EFS oﬀers two storage classes
    - 1. Standard: used to store frequently accessed files
    - 2. Infrequent Access: lower-cost storage class that's designed for storing long-lived, infrequently accessed ﬁles cost-eﬀectively
  - The service is designed to be highly scalable, highly available, and highly durable
  - Amazon EFS file systems store data and metadata across **multiple Availability Zones in an AWS Region**
  - EFS file systems can grow to petabyte scale, drive high levels of throughput, 
  - It allows massively parallel access from Amazon EC2 instances to your data.
  - Amazon EFS supports two forms of encryption for file systems
      - Encryption in transit:
            - You can enable encryption in transit when you mount the file system.
      - Encryption at rest: 
            - You can enable encryption at rest **ONLY when creating an Amazon EFS file system** 
            - If you do, all your data and metadata is encrypted
  - With Amazon EFS, you can choose from two performance modes and two throughput modes:
  - Performance Modes
      - 1. General purpose performance mode
            - ideal for latency-sensitive use cases, 
              - like web serving environments, 
              - content management systems, 
              - home directories, and 
              - general file serving
     - 2. Max I/O  performance mode
          - scale to higher levels of aggregate throughput and operations per second 
          - with a tradeoff of slightly higher latencies for file operations
            - Highly parallelized applications and workloads: such as big data analysis, media processing, and genomics analysis,
  - Amazon recommendation for determining which performance mode to use is as follows:
      - 1. Create a new file system using the default General Purpose performance mode.
      - 2. Run your application (or a use case similar to your application) for a period of time to test its performance.
      - 3. Monitor the PercentIOLimit Amazon CloudWatch metric for Amazon EFS during the performance test.
      - 4. If the PercentIOLimit percentage returned was at or near 100 percent for a significant amount of time during the test, 
            - your application should use the Max I/O performance mode. Otherwise, it should use the default General Purpose mode.
 - Throughput Modes
    - 1. Bursting Throughput mode
          - With Bursting Throughput mode, throughput on Amazon EFS scales as a file system stored in the standard storage class grows.
          - File-based workloads are typically spiky, driving high levels of throughput for short periods of time, 
            and low levels of throughput the rest of the time. 
          - To accommodate this, Amazon EFS is designed to burst to high throughput levels for periods of time.
    - 2. Provisioned Throughput 
        - Provisioned Throughput mode is available for applications with high throughput to storage (MiB/s per TiB) ratios
 - Amazon recommendation for determining which performance mode to use is as follows:
   - 1. By default, we recommend that you to run your application in the Bursting Throughput mode
   - 2. If you experience performance issues, check the BurstCreditBalance CloudWatch metric
   - 3. If the value of the BurstCreditBalance metric is either zero or steadily decreasing, 
        Provisioned Throughput is right for your application.
