### Permissions Access Control List and Bucket Policy

- Bucket Policy and Access Control List both are **Resource Based Policy**
- Teva, do you remeber what **Resource Based Policy** is? You attach this policy **to the resource** not the **IAM User**


#### What is ACL in S3? 
- It primarly used to grant basic read/write permission to other AWS accounts. 
- Only specific permisions are granted: Read, Read Only, Write, Write Only, Full Control
- The ACL is the **only way to manage the access to the objects not owned by the buket owner.**
- Enable you to manage access to buckets and objects
- Each bucket and object has ACL attach to it as as sub-resource. 
- It defines which AWS Account or groups are granted access and the type of access.

#### What is Bucket policy in S3? 
- you specify who has the access to that perticular bucket
- You should use bucket policy when you want to manage cross-account permissions for all Amazon S3 permissions. 
- Grants other AWS accounts or IAM users access permissions for the bucket and the objects in it. 
- Objectt permissions apply only to the objects that the bicket owner creates. 


