Source URL: https://www.whizlabs.com/aws-solutions-architect-associate/

# Data Consistency Model

* What is it? This shows how the results would be after PUTS/GETS/DELETES are done on the S3 objects

* S3 is an **EVENTUALLY CONSISTENT** System.

* Difference between Consistent and Eventually Consistent?
    - Consistent : When Teva update an object Ob1's key from ABS.png to ABJ.png, while another user Tom is trying to view Ob1's key and it will appear as ABJ.png. The most **updated value**
    - Eventually Consistent: When Teva update an object Ob1's key from ABS.png to ABJ.png, while another user Tom is trying to view Ob1's key and it will appear as ABS.png for a bit and eventually after a dealy this value get updated to most updated one. 
      There is a **time delay** for getting **most updated value**
      
* When a NEW object is PUT to S3 bucket and Read it 
    - **Consistent model**
    
 * An Object is already there and user Overwrite PUT and Read it
    - **EVENTUALLY Consistent**
    
 * DELETE an object and try to Read it. 
    - **EVENTUALLY Consistent**.
 
 * HEAD or GET to the object key name before creating the object.
     - **EVENTUALLY Consistent**.
     
 ### Need to remeber
 
 * New PUT **Read After Write Consistent**
 
 * Overwrite PUT **EVENTUALLY Consistentt**
  
 * DELETES  **EVENTUALLY Consistentt**
