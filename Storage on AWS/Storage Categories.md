## Storage on AWS

### Storage Categories in AWS

1. Object Storage (Amazon S3)
   - An object is a piece of data, like document, image, or video that stored with some metadata in a flat file structure. 
   - API allows to access this data in applications.
   - Amazon S3 storage is used to hold this kind of data. 

2. Block Storage (EBS)
   - Data is presented to your instance as a disk volume.
   - Elasic Block Storage is popular, for example, for boot volume, and databases. 
   
3. File Storage (EFS)
   - Data is presented via file systems interface and with file system semantics to instances.
   - Amazon Elastic File System (EFS) provides shares access to ata via multiple Amazon EC2 instances, with low latencies.
