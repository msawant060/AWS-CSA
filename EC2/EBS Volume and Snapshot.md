Resource: https://www.whizlabs.com/aws-solutions-architect-associate

# EBS Volume and Snapshot

#### What is EBS Volume?
  - **Durable** block-level storage device that you can atach to a single EC2 instance (Like a physical hard drive)
  - Flexible: You can dynamically increase, modify provisioned IOPS capacity, and change the volume type on **live production**
  - Mostly used as primary storage for data that requires frequent updates, such as system drive instance. 
  - Types of EBS:
      - Root Volume: General purpose SSD, Provisioned IOPS SSD, Magenetic HDD
      - Others: Throughput Optimized HDD, Cold HDD
  - One EC2 instance may ccontain more than one EBS. However, more than one EC2 instance can't share an EBS volume.
  

#### What is Snapshot?
  - **A point-in-time** backup of the data that is stored on the EBS Volume
  
