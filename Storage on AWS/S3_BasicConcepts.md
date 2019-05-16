# Basic Concepts

### Overview of S3

  1. S3 provides developers and IT teams with secure, highly-scalable object storage 
  2. Store and retrieve **any amount of data from anywhere** on the web.
  3. It is **Object-based storage** - allows you to upload files (Pictures/Videos/MP3)
  4. Files can be from **0 Bytes to 5 TB**
  5. There is unlimited storage 
  6. Files are stored in Buckets 
  8. S3 is a **Universal namespace**. This is, **name must be unique globally**. 
  9. When you upload a file to S3, you will receive a **HTTP 200 code if the upload was successful**
  10. S3 Storage Classes/Tires:
       - Amazon S3 Standard  : Durable, immediately available, frequent accessed 
       - Amazon S3 Standard Infrequent Access (IA) : Durable,  immediately available, infrequent accessed 
       - Amazon S3 One Zone Infrequent Access - IA (one_Zone IA): Even cheaper than IA, but only in one availability zone 
       - Glacier - Archived data, where you can wait 3 - 5 hours before accessing 
  11. S3 Chrages depends on
        - Storage
        - Request
        - Data Transfer Price 
        - Storage Management PRicing
        - Transfer Acceleration
 12.Amazon S3 Transfer Acceleration
    * It enables:
        - Fast, 
        - Easy, and 
        - Secure transfers of files over long distances between your end users and an S3 bucket
    * Transfer Acceleration takes advantage of Amazon CloudFront’s globally distributed edge locations. 
    * AS the data arrives at an edge location, data is routed to Amazon S3 over an optimized network path

### Benifits of S3

  1. Hight Durability: Amazon Guarantee 99.99999...% (11 9s) durability of objects over a given year.
  
  2. High Availability: Amazon Guarantee 99.9% availablity. Objects from S3 automatically distributed to minimum 3 AZs from the same region. When one AZ's data is not availbale still user can access the data via one of the other 2 AZs.
  
  3. High Scalability: S3 is managed by AWS and automatically sclaes up and down based on the load. 
  
  4. High Reliability 
  
  5. Fast: The Multipart upload option enables you to upload large objects in parts.
  
  6. Low Price
      - Amazon S3 One Zone Infrequent Access
      - Amazon S3 Standard Infrequent Access
      - Amazon S3 Standard 
      
   7. Secure: 
   
   8. Flexible Storage and Management 
   
   9. East Interface for Data Transfer 
   
   10. East Integration
   
### Use cases of S3 

  1. Backup and Recovery
  
  2. Data Archiving (Glacier)
  
  3. Data Lake for Big Data Analytics 
  
  4. Hybrid Cloud Storage 
  
  5. Cloud-Native Application Data
  
  6. Disaster Recovery 
  
 Source: https://www.whizlabs.com/aws-solutions-architect-associate/ and https://acloud.guru/
