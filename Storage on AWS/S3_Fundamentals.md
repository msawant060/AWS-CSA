Source and all credit goes to: https://www.whizlabs.com/aws-solutions-architect-associate/
# S3 Fundamentals
 * Bucket
    - A Container that stores the objects that are uploaded to S3
    - They are **PRIVATE** by default
 * Object
   - Fundamental entities stored in Amazon S3. (Pictures, Audio, Video)
   - Object has the following 2 memebers 
      - Object Data
      - Meta Data
   - S3 doesn't care about **Object Data**
   - S3 Can **NEVER sees the contents inside your objects**
   - S3 has access to the Metadata
      - This is the name-value pair describe the object
 * Endpoints
   - URL that is the entry point for a web service 
   - Most Amazon Web Services offer a regional endpoint to make your requests to reduce data latency in your application
 * Key
  - This is a name or unique identifier of the object 
  - Every object in bucket has exactly one key 
 * Every object in Amazon S3 can be uniquely identified via the combination of:
     - Endpoint
     - Bucket 
     - Key
     - Optionally version
  * Example: https://s3.us-east-2.amazonaws.com/mywhizlasbbucket/whizlab/aws/course/abc.png
     - Here the key is: whizlab/aws/course/abc.png
     - Bucket name: mywhizlasbbucket
     - Endpoint: https://s3.us-east-2.amazonaws.com 
  
 * Region.
  - You can access bucket from any region.
  - Objects stored in a region **NEVER leave the region, unless you explicilty transfer them to another region**
