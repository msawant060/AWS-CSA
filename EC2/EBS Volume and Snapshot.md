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
  - You can encrypt EBS volumes using Amazon EBS encryption feature
  - AWS uses the Data Encryption with 256-bit Advanced Encryption Standard Algorithms (AES-256).
  - Amazon EBS encryption uses AWS Key Management Service (AWS KMS) master keys when creating the encrypted volumes and any snapshots         created from those. 
  - Volumes and instance needs to be in the same AZ.

#### What is Snapshot?
  - **A point-in-time** backup of the data that is stored on the EBS Volume
  - Data on EBS volume can be backed via snapshots (Stored on S3 for redundancy)
  - Data can be backed up even when volume is attached to running instance 
  - **snapshots are incremental backups**
  - What is Lazy Loading?
  - snapshots is constrained to the region where it was created. The volume can be created **same region only**
  - It supports cross-region copy.
