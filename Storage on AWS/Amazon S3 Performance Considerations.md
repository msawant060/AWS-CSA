### Amazon S3 Performance Considerations
  - When do you need to follow the partioning guidelines to avoid the bottle neck?
    - When Amazon S3 bucket is going exceed 100 PUT/LIST/DELETE request per second or 300 GET per second
  - Amazon S3 supports very high request rate. 
    - To do so, S3 internally partionied all of your bucket
  - Many cases, the best statergy would be Adding a **Hex Hash Prefix to Key Name**. 
