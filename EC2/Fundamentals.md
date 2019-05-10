Source: https://www.whizlabs.com/aws-solutions-architect-associate

#### 1. What is EC2?
   - Amazon Elastic Compute Cloud (Amazon EC2) provides scalable computing capacity in the Amazon Web Services (AWS) cloud
   - VMs hosted on AWS infrastructure 
   
#### 2. What is an AMI?
   - An Amazon Machine Image (AMI) provides the information required to launch an instance. 
   - You must specify an AMI when you launch an instance.
   - A template required to launch an EC2
   - Includes:
        - Template for the root volume (OS, software package)
        - Launch permissins
        - Volume information
        
#### 3. Before you can launch an instance, you must select an AMI to use. 
   - As you select an AMI, consider the following requirements you might have for the instances that you'll launch:
        - The Region
        - The operating system
        - The architecture: 32-bit (i386) or 64-bit (x86_64)
        - The root device type (Storge for root device): Amazon EBS or instance store
        - The provider (for example, Amazon Web Services)
        - Additional software (for example, SQL server)
         
#### 4. You can launch EC2 instances from:
   - AWS Market place
   - Community Repository
   - Your Own
  
#### 5. AWS Supports the following 2 types of Virtualization
   - HVM - Hardware Assisted Virtual Machine (**for best performance use this)
   - Paravirtualization 
            
#### 6. Amazon EC2 Instance Types ( 5 major types)
 
 | Speciality | Family | 
 |------------|--------|
 | General Purpose | A, T , M | 
 | Compute Optimized | C |
 | Memory Optimized | R, X, Z |
 | Accelerated Computing OR GPU | G, P, F |
 | Storage Optimized | H, I, D |
 
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
          
#### 8. AWS Storage Volume Types: 3 Tpes
   1. General Purpose SSD (SSD: Solid State Drive)
   2. Provisioned IPOS SSD (SSD: Solid State Drive)
   3. Magnetic HDD (HDD: Hard Disk Drive)
 
##### Difference between Solid State Drive and Hard Disk Drive

| Solid State Drive | Hard Disk Drive |
|-------------------|-----------------|
| Most suitable for applications that require frequent read/write operation with small I/O | Most suitable whe the througput(MiB/s) more critical than IOPS |
| Cost high | Compare to SSD less cost |
    
* General purpose SSD
    - It can be used as **root volume of EC2 instance**
    - Baseline performance of 3 IPOS per GiB (Gibibytes = Gib = 1.074 Gigabytes)
    - Minimum IOPS is 100 and Maximum is 10,000
    - It is most suited for general purpose where it balance cost and performance   
    - Most used or Low-Latency interactive applications and Development and test environment
    
* Provisioned Throughput SSD
    - It can be used as **root volume of EC2 instance**
    - Baseline performance of 50 IPOS per GiB (Gibibytes = Gib = 1.074 Gigabytes)
    - Minimum IOPS is 100 and Maximum is 32,000
    - Suited for applications that require sustained IOPS performance, more than 10, 000 IOPS, or 160 MiB/s of throughput per volume
    - Use for appliations that needs Database workload is high
    
 * Magnetic HDD
    - It can be used as **root volume of EC2 instance**
    - Older generation volumes are backend by magnetic drives
    - Suited for applications where low-cost storage for small volume size is important
    - Baseline performance approximately 100 IOPS
    - Avarage and max throughput is 90 MiB/second
  
 * Throughput Optimized HDD
    - It can NOT be used as **root volume of EC2 instance**
    - For application that have frequenty accesses, throughput-intensive workloads
    - Low cost HDD
    - Max throughput per volume is 500 Megabits/S
    
 * Cold HDD
    - It can NOT be used as **root volume of EC2 instance**
    - For application that have lessfrequently accesses, non-intensive workloads
    - Lowest cost HDD
    - Max throughput per volume is 250 Megabits/S
   
#### 9. Encryption of Volume
   - When you encrypt the EBS volume that following type of data are encrypted:
        - Data at rest inside the volume
        - All data moving between the volume and the instance
        - All snapshots created from the volume
        - All volumes created from those snapshots
    
#### 10. Security Group
   - Protects the **instance** by applying a security wall of rules (like firwall)
   - Controls the traffic coming IN and going OUT of the instance
   - Following are some rules you can set for the security group
         - Types of request : TCP, UDP, HTTP, HTPS, Custom
         - Protocol: TCP, UDP, ICMP
         - Port Number or Range
         - Source of the traffic and the description
         
   
    
