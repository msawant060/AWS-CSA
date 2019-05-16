Source URL: https://www.whizlabs.com/aws-solutions-architect-associate

## Logging

### Server Access Logging
  - Logging happens at the Server Level
  - When you enable this to an S3 bucket, this provides the detailed records for the requests that are made to a bucket. (Source bucket)
  - Security and Autiting are the use of this service
  - By default, this is NOT enabled
  - Target bucket
      - Where the logs will be deliverd 
  - Source and Target bucket could be the SAME (YOu may select a prefix to identify the logs)
  - Source and Target bucket SHOULD BE IN THE SAME REGION.
  - You need to grant the Amazon S3 Log Delivery group write permission on the target bucket. 
  - Server Access Log provides the following:
      - Name of the bucket which was accessed
      - Requester
      - Request time
      - Request action
      - Request status 
      - Error code
   - You can dump the logs of **mutiple source buckets in a single target bucket**
   - Server access log records are deliverd on a "best effort basis"
      - Most records are delivered within a few hours of the time that they are recorded but timeliness of server logging is not guranteed. 
   
### Object level Logging
   - Logging happens at the Object Level
   - When you enable this to an S3 bucket, and when a user or application tried to access an object in this bucket, if a CloudTrail trail      is setup for this S3 bucket Data Event, the logs will be created in the target bucket.
   -  ![ObjectLevelLoggins.PNG](/ObjectLevelLoggins.PNG)
