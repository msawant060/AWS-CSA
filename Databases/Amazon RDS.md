### Amazon Relational Database Service (Amazon RDS)

##### What is Amazon RDS?
- Amazon Relational Database Service is a distributed relational database service by Amazon Web Services. 
- It is a web service running "in the cloud" designed to simplify the setup, operation, and scaling of a relational database for use 
  in applications
- Currently RDS supports: MYSQL, MSSQL, Amazon Autora, MariaDB, Oracle, PostgreSQL

##### Why to use Amazon RDS? 
- East to adminster 
- High Scalable 
- Available and Durable 
- Fast
- Secure: Via VPC
- Inexpensive: You pay very low rates and only for the resources you actually consume. In addition, you benefit from the option of On-Demand pricing with no up-front or long-term commitments, 
                or even lower hourly rates via our Reserved Instance pricing.

#### Database Instance
 - A basic building block of Amazon RDS.
 - One database instane can have more than one databases
 - Each DB instance has a DB instance identifier
 - Status of DB instance shows the health staus of the DB instance 
 - DB instance for Amazon RDS for MySQL, MariDB, PostgrSQL, ORacle and MSSQL uses EBS volumes for database and log stores 
 - Billing bases on
    - DB instance hour, 
    - Storage
    - I/O request
    - Backup storage
    - Data transfer
    - Proviosned IOPS
 
 #### Backup
- Amazon RDS provides 2 ways of backups
  - Automated backups
  - Manual backup/ DB Sanpshots
- Automated Backups
     - Amazon RDS Created automated storage volumes snapshots of entire DB instance to point-in-time revovery 
     - Backups retained as per the **backup retiontion period**. Default 7 days, maximum 35 days.
     - IO suspension:
        - Backing up from a single AZ-DB instance results in a brief IO suspension.(Can be few seconds, or minutes depending on the size of DB)
        - Mutiple AZ instances are not affectd by this I/O suspension during the backup since the backup is taken on Standby
     - Backup Window. This is the duration taken while backing up the database. (By default 30 minutes)
        - If the backup duration is higer than backup window, still the back up will conitinue until it's done.
     - Backup are delted when you delete the DB instace. However, **RDS gives a chance to take a final backup beore deleting** the database      instance. Which can be useed later to restore the database 
     - **DescribeDBInstance** API retunrs that last restorables time for the DB instance, which is typically within the last 5 minutes. 
   
 - Manual backup/ DB Sanpshots 
    - Created manually
    - Incremental database backup. Teva, try to remember what this is?
    - These are NOT delted when you delete the dataase instance
    
 
