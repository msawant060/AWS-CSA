Source from: https://www.whizlabs.com/aws-solutions-architect-associate/
# DynamoDB

* What is DynamoDB?
   - It is Fully managed, mutil-master NoSQL database service
   - It provides 
      - Fast Predictable Performance
      - Consistent single-digit millisecond latency 
      - Seamless scalability / High Scalability 
 * Why use DynamoDB?
   - Fully Managed by AWS
   - Performance at Scale: Delivers consistent, single-digit millisecond responsivess at any scale 
   - Distributed: Scales Horizontally by expanding a single table over mutiple server
   - In-memory cache: Reduces responsive time from milliseconds to microseconds, wihtout any app changes.
   - Fast Access: Provides fast access to local data by replicating tables across mutiple AWS Regions. 
   - Security 
    
  * Components 
    - Table
         - Collection of Data
         - Each table contains 0 or more Items
    - Item
         - Collection of attributes that is uniquely identifiable among all of the other items.
         - Each item composed of one or more attributes 
     - Attribute
         - A fundamental data element, something that does not need to be broken down any further.
     - Allowed data types
         - String, Number, Binary
         - No restrictions of other data types
           
    ![Items.PNG](/Items.PNG)
    
    ![Attributes.PNG](/Attributes.PNG)
    
Source URL: http://www.whizlabs.com/learn/course/aws-csaa-practice-tests/
