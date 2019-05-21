### Storage Classes

- Amazon S3 Standard
  - Default Storage
  - Used for frequently accessed data
  - Durability 99.99... (11times)%
  - Availability 99.99%
  - 3 Availability zones
  
- Amazon S3 Standard Infrequent Access (IA)
  - Often used for storing data and access it less frequently 
  - Durability 99.99... (11times)%
  - Availability 99.9%
 
- Amazon S3 Reduced Redundancy Storage (RRS)
  - this is used to store noncritical, non production data. 
  - Durability 99.99%
  - Availability 99.9%
  - Here you store data that can be easily reproduce
  
- Amazon S3 One-Zone Infrequent Access
  - Use case: less frequent, but require rapid access data
  - 1 Availability zone
  - Coast 20% less than S3 standard IA

- Amazon Glacier
  - Storage class and mainly for archieving
  - Durability 99.99... (11times)%
  - It's much cheaper than all other classes 
  - Three main options for retrieving data with varying cost and time
      - Expedited - Very quick data retrievals in the range of 1 to 5 min.
      - Standard - 3 - 5 minutes
      - Bulk - PEtabytes of data in a day (5 to 12 hours)
