### Cross Region Replication.

#### What is CRR? 


#### Why do we need it?


#### Requirements for CRR?
- **Versioning must have enabled** both Souce and Destination buckets
- Source and Destination buckets needs to be in different AWS regions
- S3 must hae permisson to replicate objects from source bucket to the destination bucket on your behalf.
- Source and Destination could be owned by different AWS acounts, 
  However, the IAM Role must have permissions to replicate objects in the destination bucket. 

#### What is Replictated?
 - Any new objects created afer you add a CRR.
 - 
