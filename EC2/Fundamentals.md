* What is EC2?
   - Amazon Elastic Compute Cloud (Amazon EC2) provides scalable computing capacity in the Amazon Web Services (AWS) cloud
   - VMs hosted on AWS infrastructure 
   
* What is an AMI?
    - An Amazon Machine Image (AMI) provides the information required to launch an instance. 
    - You must specify an AMI when you launch an instance.
    - A template required to launch an EC2
    - Includes:
        - Template for the root volume (OS, software package)
        - Launch permissins
        - Volume information
        
* Before you can launch an instance, you must select an AMI to use. 
    - As you select an AMI, consider the following requirements you might have for the instances that you'll launch:
         - The Region
         - The operating system
         - The architecture: 32-bit (i386) or 64-bit (x86_64)
         - The root device type (Storge for root device): Amazon EBS or instance store
         - The provider (for example, Amazon Web Services)
         - Additional software (for example, SQL server)
 
      
* You can launch EC2 instances from:
      - AWS Market place
      - Community Repository
      - Your Own
  
* AWS Supports the following 2 types of Virtualization
      - HVM - Hardware Assisted Virtual Machine (**for best performance use this)
      - Paravirtualization 
            
 * Amazon EC2 Instance Types ( 5 major types)
 
 | Speciality | Family | 
 |------------|--------|
 | General Purpose | A, T , M | 
 | Compute Optimized | C |
 | Memory Optimized | R, X, Z |
 | Accelerated Computing OR GPU | G, P, F |
 | Storage Optimized | H, I, D |
 
 Full details: https://aws.amazon.com/ec2/instance-types/
 
 * Amazon EC2 Purchasing Options 
    1. On-Demand Instances – Pay, by the second, for the instances that you launch.
    2. Reserved Instances – Purchase, at a significant discount, instances that are always available, for a term from one to three years.'
    3. Scheduled Instances – Purchase instances that are always available on the specified recurring schedule, for a one-year term.
    4. Spot Instances – Request unused EC2 instances, which can lower your Amazon EC2 costs significantly.
    5. Dedicated Hosts – Pay for a physical host that is fully dedicated to running your instances, and bring your existing per-socket, per-core, or per-VM software licenses to reduce costs.
    6. Dedicated Instances – Pay, by the hour, for instances that run on single-tenant hardware.
    7. Capacity Reservations – Reserve capacity for your EC2 instances in a specific Availability Zone for any duration.
            
 
 
