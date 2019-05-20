### What is Object Lifecycle Management?
-  A lifecycle configuration is a set of rules that define actions that Amazon S3 applies to a group of objects. T

- There are two types of actions:
   1. Transition actions
       - Define when objects transition to another storage class. 
       - For example, you might choose to transition objects to the STANDARD_IA storage class **30 days after you created** them, 
       - or archive objects to the GLACIER storage class one year after creating them.
       
    2. Expiration actions
        - Define when objects expire. Amazon S3 deletes expired objects on your behalf.
 
### Why to use it?
- To manage your objects so that they are stored cost effectively throughout their lifecycle, configure their lifecycle. 

### Important Points to Remeber
  - You can transfer the objects ONLY after **30 days**
  - You can delte the objects within 1 da of transition
  - You can transition the curent or previous version
  - It has eventual consisteny 
    - when you add a lifecycle configuration to a bucket, 
      there is ususally some lag before a new or updated lifecycle confguration is fully propagated to all the Amazon S3 system.
  - When you add a liftcycle configuraion to a bucket, the configuration rules apply to both existing objects and objects that you add later.
