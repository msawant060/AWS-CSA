# S3 Bucket Versioning

 - Why do we need to version the bucket?
   - It helps to keep the object in the bucket from accedental deletion or overwrites
 
 - What is the stages of a bucket
    - Un-version (Default)
    - Version-Enables 
    - Version-Suspended 
  
 - Once the bucket version is Enables, the versioning can **ONLY BE SUSPENDED**, the bucket cannot be **UN-VERSIONED BACK**

- The versioning state applies to all of the objects in the bucket

- Once the versioning is enabled
   - all the subsequent added/modified objects are versioned and given unique version ID
   - Objects that are stored in un-versioned bucket have null as the version ID.
   
 - You have to make object of each version **PUBLIC**.
 
 - Even if the previous version was **PUBLIC**, the newley added one will not be **PUBLIC**
