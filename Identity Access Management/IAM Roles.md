Source URL: https://www.whizlabs.com/aws-solutions-architect-associate/

* What is IAM Role?
  - A set of permissions that grant access to actions and resources in AWS. These permissions are attached to the **ROLE** NOT to an **IAM Group**
  - You can assign a Role to EC2 or User or Mobile Application to access resources 
  - Role does NOT have a statndard long term credentials. (such as user name and password or access key)
  - However, when you assign a Role to a user a **Temporary Security Credential** will assign to user to provide more secure granular access
  - NOTE: When a user assumes a role, **temporary security credentials** are created dynamically and provided to the user - making it a more secure to grant access.

* What is Delegation?
  - The granting of permission to someone to allow access to resources that you control.
  
* Who can use the IAM Rol? 
  - Role can delegate access to:
    - Users
    - Applications
    - Services 
    - That doesn't have access to AWS resources 
    - Thanks for https://www.whizlabs.com for the following image:     
    - ![Roles.PNG](/Roles.PNG)
 
* Why use IAM Role?
  - **it allows you to delgate access with defined permissions to trusted entities without having to share long-term access keys.**
  - When EC2 accessess AWS resources such as S3 via IAM User, the user's security credentials get stored on that EC2 instance, **THIS SHOULD BE AVOIDED. 
  - When EC2 assumes a role, its credentials are not stored - **Making a secure way of accessing resources**
   
* When to use it?
  - Provide access for services offered by AWS to AWS resource
  - Provide access for an IAM user on one AWS account that you own to access resources in another account that you own.
  - Provide access for external authenticated users (Indetity federation (Facebook, LinkedIN)
  - Provide access to IAM users in AWS account owned by 3rd parties. 
  - The following picture shows all the cases:
  
  ![Roles2.PNG](/Roles2.PNG)

* AWS Service Role:

* AWS Service Role for an EC2 instance:

* AWS Service-lined-role:

* Role Chaining:

* Trust Policy: A document in JASON format in which you define **WHO is allowed to assume the role**. 

* Permission Policy: A permission document in JASON format in which you define **WHAT ACTIONS and RESOURCES the role can use.** 

# Important points related to ROLES

* You can only assosiate one IAM role with EC2 instance at this time. You **CAN NOT** assosiate more than one IAM role with an EC2 instance. **This limit one role per instance CAN NOT be increased**

* You can consume an IAM role by:
  - Calling AWS Security Token Service (STS)
  - AssumeRole APIs (Assume Role, Assume Role with Web Indentity, Assume Role with SAML)
  
* If you delte an IAM Role that is assosiated with a running EC2 instance, any application running on the instance that is using the role will be **DENIED ACCESS IMMIDIATELY**

* Role can be assigned to EC2 instances in the following scenarios:
  - When you launch an instance 
  - Already running instance 
  
 * You CAN NOT add an IAM role to an **IAM GROUP**
 
 * IAM roles CAN NOT make direct requests to AWS services
   - They are meant to be assumed by authorized entities (IAM USers, Applications or AWS Services such as EC2)
   
  * IAM Roles are free to charge. 
 
  
