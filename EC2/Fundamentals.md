Source: https://www.whizlabs.com/aws-solutions-architect-associate
# Amazon Elastic Compute Cloud (Amazon EC2)

#### 1. What is EC2?
   1. Amazon Elastic Compute Cloud (Amazon EC2) provides scalable computing capacity in the Amazon Web Services (AWS) cloud
   
#### 2. What is an AMI?
   1. An Amazon Machine Image (AMI) provides the information required to launch an instance. (like a template required to launch an EC2)
   2. You must specify an AMI when you launch an instance.   
        
#### 3. Before you can launch an instance, what you must select from an AMI to use. (6 point to remember)
   1. The Region
   2. The Operating System
   3. The architecture: 32-bit (i386) or 64-bit (x86_64)
   4. Root device type (EBS, Instance store)
   5. The provider (for example, Amazon Web Services)
   6. Additional software (for example, SQL server)
         
#### 4. You can launch EC2 instances from:
   1. AWS Market place
   2. Community Repository
   3. Your Own
  
#### 5. AWS Supports the following 2 types of Virtualization
   1. HVM - Hardware Assisted Virtual Machine (**for best performance use this)
   2. Paravirtualization 
            
#### 6. Amazon EC2 Instance Types ( 5 major types)
 
 | Speciality | Family | Example Cases |
 |------------|--------|---------------|
 | General Purpose | A, T , M | Web Server, Develoment Environment, code Repo, Micro Services, Test and Stage Env | 
 | Compute Optimized | C | Media Trancoding, Application with large number of concurrent users, long running batch jobs, Game Server |
 | Memory Optimized | R, X, Z | Oracle database in memory, MongoDB, Cassandra, Big data processing |
 | Accelerated Computing OR GPU | G, P, F | GPU |
 | Storage Optimized | H, I, D | Data Ware house , MapReduce, Hadoop, RDBMS | 
 
 Full details: https://aws.amazon.com/ec2/instance-types/
 
#### 7. Amazon EC2 Purchasing Options: 

   1. On-Demand Instances  
         - Pay, by the second, for the instances that you launch.
         - Pay-as-you-go
         - You purchase the instance as and when needed
         - This is the costliest option
         - this is suitable for:
               - You're not sure about the capacity needed beforehand
               - Eg: Your application has sudded spike of traffic, short projects, R&D etc.    
               
   2. Reserved Instances 
         - Purchase, at a significant discount, instances that are always available, for a term from one to three years.
         - this is suitable for:
               - You aware about the capacity needed
               - Eg: Minimum number of VMs needed to run your application smoothly           
               
   3. Scheduled Instances  
         - Purchase instances that are always available on the specified recurring schedule, for a one-year term.   
         
   4. Spot Instances  
         - Request unused EC2 instances, which can lower your Amazon EC2 costs significantly.
         - You bid for the unused EC2 instance cpacity of AWS
         - If the actual price of EC2 instance class becomes equal or less than the bid price, the instance get assigned to you at YOUR             BID PRICE
         - However, if the actual price increases than your bid price, your instances may get terminated with a half an hour's notice. 
         -  This could be a little risky option
         - You will **not** charge for the partial hour in which the instance was terminated. 
         * Spot Instance Pool: A set of unused EC2 instances with the same istance type, OS, AZ. Your instance will be one of these
         * Spot Price: Current houlry price of the spot instance
         * Spot Instance Request: Your bid or the price that you are willing to pay for Spot Instance
         * Spot Fleet: Basically, you specify the criteria of the instance and then the pot fleet selects the Spot Instance pool that               meet your needs and launch Spot Instances.
         * Spot Instance Interruption: Amazon EC2 terminates, stops, or hibrenates your Spot Instance when the Spot price exceeds the              maximum price for your request or capacity is no longer available 
         
   5. Dedicated Hosts
        - Pay for a physical host that is fully dedicated to running your instances, 
        - and bring your existing per-socket, per-core, or per-VM software licenses to reduce costs.
          
   6. Dedicated Instances 
        - Pay, by the hour, for instances that run on single-tenant hardware.
    
   Soure: https://www.whizlabs.com/aws-solutions-architect-associate    
     
   ![DedicatedHost.PNG](/DedicatedHost.PNG)
 
   7. Capacity Reservations 
        - Reserve capacity for your EC2 instances in a specific Availability Zone for any duration.
          
#### 8. Elastic Block Storage (EBS) AWS Storage Volume Types: 3 Tpes
   - Amazon EBS allows you to create storage volumes and attach them Amazon EC2 instances. 
   - Once attached:
      - You can create a file system on top of theses volumes
      - Run a database 
      - Use them in any other way you would use a block device.
      
   - The following are the main 3 types
      - 1. General Purpose SSD (SSD: Solid State Drive)
      - 2. Provisioned IPOS SSD (SSD: Solid State Drive)
      - 3. Magnetic HDD (HDD: Hard Disk Drive)
 
##### Difference between Storage IOPS and Storage Throughput (Source: https://storageservers.wordpress.com/2015/11/10/difference-between-storage-iops-and-storage-throughput)

 - Throughput:
      - Data transfer speed in megabytes per second is often termed as throughput. 
      - Earlier, it was measured in Kilobytes. But now the standard has become megabytes.
 - IOPS:
      - The time taken for a storage system to perform an Input/Output operation per second from start to finish constitutes IOPS.

##### Difference between Solid State Drive and Hard Disk Drive

| Solid State Drive (SSD) | Hard Disk Drive (HDD) |
|-------------------|-----------------|
| Most suitable for applications that require frequent read/write operation with small I/O | Most suitable whe the througput(MiB/s) more critical than IOPS |
| High Cost | Less Cost |
| GP2, IO1 | Standard, ST1, SC1 |
    
* General purpose SSD (GP2)
    - Used for: general purpose where it balance cost and performance   
    - It can be used as **root volume of EC2 instance**
    - Baseline performance of 3 IPOS per GiB (Gibibytes = Gib = 1.074 Gigabytes)
    - Minimum IOPS is 100 and Maximum is 10,000   
    - Most used or Low-Latency interactive applications and Development and test environment
    
* Provisioned Throughput SSD (IO1)
    - Used for: I/O intensive applications such as large relational or NoSQL databases.
    - It can be used as **root volume of EC2 instance**
    - Baseline performance of 50 IPOS per GiB (Gibibytes = Gib = 1.074 Gigabytes)
    - Minimum IOPS is 100 and Maximum is 32,000
    - Suited for applications that require sustained IOPS performance, more than 10, 000 IOPS, or 160 MiB/s of throughput per volume
    - Use for appliations that needs Database workload is high
    
 * Magnetic HDD (Standard)
    - Used for: Where data is accessed infrequently, and applications where the lowest storage cost is importan.
    - It can be used as **root volume of EC2 instance**
    - Older generation volumes are backend by magnetic drives
    - Baseline performance approximately 100 IOPS
    - Avarage and max throughput is 90 MiB/second
  
 * Throughput Optimized HDD (ST1)
    - Used for: Big Data, Data warehouse, Log Processing.
    - It can NOT be used as **root volume of EC2 instance**
    - For application that have frequenty accesses, throughput-intensive workloads    
    - Max throughput per volume is 500 Megabits/S
    
 * Cold HDD (SC1)
    - Used for: File Server.
    - It can NOT be used as **root volume of EC2 instance**
    - For application that have lessfrequently accesses, non-intensive workloads
    - Lowest cost HDD
    - Max throughput per volume is 250 Megabits/S
    
#### 9. Difference between EBS and Instance Store (source: https://aws.amazon.com/premiumsupport/knowledge-center/instance-store-vs-ebs/)

   | EBS | Instance Store |
   |-----|----------------|
   | Data Persists when the instance STOP and RE-STARTED | Data DOES NOT PERSISTS When the instance STOP and RE-STARTED|
   | Instance Termination, based on the user choise during the instance creation data can be persists | Instance Termination, data will be lost| 
   | We can attach EBS volume to all instance types | This supported by selected instance only |
   | Size of EBS volume can be decided as per our needs and can be modified if required | Size is dtermined by the instance type you selected, such as c1.medium |
   | This is for **All Important data** | This is for **Temporary data storage** | 

#### 10. Encryption of Volume
   - When you encrypt the EBS volume that following type of data are encrypted:
        1. Data at rest inside the volume
        2. All data moving between the volume and the instance
        3. All snapshots created from the volume
        4. All volumes created from those snapshots
    
#### 11. Security Group (totally 8 points)
   1. Protects the **instance** by applying a security wall of rules (like firwall)
   2. Controls the traffic coming IN and going OUT of the instance
   3. Following are some rules you can set for the security group
       - Types of request : TCP, UDP, HTTP, HTPS, Custom
       - Protocol: TCP, UDP, ICMP
       - Port Number or Range
       - Source of the traffic and the description
   4. All **incoming traffic is denied by security group**
   5. You can **only define allow rules**. You CAN NOT specify any **"DENY RULE"**
   6. **Stateful** : If you ALLOW traffic of a perticular type from a source into your instance, the outgoing traffic is ALLOWED            automatically
   7. It works on Instance level and you can have multiple security group under one security group
   8. You cannot block specific IP addresses using Security Groups, use Network Access Control Lists.
   
  #### 12. AWS EC2 Key-pair
   - Amazon EC2 uses Public-key cryptography to encrypt and decrypt the login information
   - Public-key cryptography encrypt the password using public key, then the recipient or the user uses the private key to decrypt the        data.
   
   
