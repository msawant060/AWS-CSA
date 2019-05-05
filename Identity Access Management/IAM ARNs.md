# Amazon Resource Name

## arn:partition:service:region:account:resource

* where:
  - partition: Identifies the partition that resource is in
      - For statdard AWS regions, the partiotion is aws. 
      - If you have resources in other patitions, the partition is aws-partitionaname. For example, the partion in China (Beijing) is aws-cn
  - service idenfies that AWS product. For IAM resources, this is always iam
  - region is the region the resource resides in. For AIM resource, this is awlays left **blank**
  - account is the aws account ID with no hyphens. (for eample 12345678012)
  - resource is the portion that identifies the specific resource by name
 
 * The AWS account - the root account itself
     - arn:aws:iam::123456789012:root
     
 * An IAM in the account
     - arn:aws:iam::123456789012:user/Bob
     
 * Another user with a path reflecting an organization chart:
     - arn:aws:iam::123456789012:user/division_abc/sub_division/Bob
 
  * An IAM in the account
     - arn:aws:iam::912489811600:user/Teva
  
  
