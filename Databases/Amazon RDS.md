### Amazon Relational Database Service (Amazon RDS)

##### What is Amazon RDS?
- Amazon Relational Database Service is a distributed relational database service by Amazon Web Services. 
- It is a web service running "in the cloud" designed to simplify the setup, operation, and scaling of a relational database for use 
  in applications
- Currently RDS supports: MYSQL, MSSQL, Amazon Aurora, MariaDB, Oracle, PostgreSQL

##### Why to use Amazon RDS? 
- Managed by AWS 
- High Scalable 
- Available
- Durable 
- Fast
- Secure: Via VPC, IAM
- Inexpensive: You pay very low rates and only for the resources you actually consume. In addition, you benefit from the option of On-Demand pricing with no up-front or long-term commitments, 
                or even lower hourly rates via our Reserved Instance pricing.

#### Database Instance
 - A basic building block of Amazon RDS.
 - One database instane can have more than one databases
 - Each DB instance has a **DB instance identifier**
 - Status of DB instance shows the health staus of the DB instance 
 - DB instance for Amazon RDS for MySQL, MariDB, PostgrSQL, ORacle and MSSQL uses **EBS volumes** for database and log stores 
 - Billing bases on
    - DB instance hour, 
    - Storage
    - I/O request
    - Backup storage
    - Data transfer
    - Proviosned IOPS
 - Instance class should be chosen based on processing power and memory optimized requirements of the applicatins. db.m4, db.m5, db.x1,    db.x1e
 - You can create MySQL, MariaDB, SQLSErver, PostgreSQL, Oracle RDS DB instances upto 16TiB. (1TiB = 1024GiB)
 
 #### Database Parameter Group and Database Option Group
 - Parameter Group
    - A container that contains configuration values that are applied to one or more DB instances
    - You CAN NOT modify the parameter settings of a default DB paramters group. You need to create your own DB Paramter group
    - Default values of Parameter Group are based on Engine, Compute Class, Allocated Stoarge of the instance
    
 - Option Group
   - Use for enabling and configuring additional features that makes it eay to manange data and database and provisioned security groups 
   - A DB instance, restored from a snapshot has the Option Group settings 
  
  
 #### Backup
- Amazon RDS provides 2 ways of backups
  - Automated backups
  - Manual backup/ DB Sanpshots
- Automated Backups
     - Amazon RDS Created automated storage volumes snapshots of entire DB instance to point-in-time revovery 
     - Backups retained as per the **backup retiontion period**. Default 7 days, maximum 35 days.
     - IO suspension:
        - Backing up from a single AZ-DB instance results in a brief IO suspension.(Can be few seconds, or minutes depending on the size          of DB)
        - Mutiple AZ instances are not affectd by this I/O suspension during the backup since the backup is taken on Standby
     - Backup Window. This is the duration taken while backing up the database. (By default 30 minutes)
        - If the backup duration is higer than backup window, still the back up will conitinue until it's done.
     - Backup are delted when you delete the DB instace. However, **RDS gives a chance to take a final backup beore deleting** the database      instance. Which can be useed later to restore the database 
     - **DescribeDBInstance** API retunrs that last restorables time for the DB instance, which is typically within the last 5 minutes. 
   
 - Manual backup/ DB Sanpshots 
    - Created manually
    - Incremental database backup. Teva, try to remember what this is?
    - These are NOT deleted when you delete the dataase instance
    
 #### Log exporting related to RDS. 
  - USer can create Error Log, General Log, Show query Log and to publish to Amazon CloudWatch Logs
      - **User needs to have RDS Service Linked Role** to do that.
   
