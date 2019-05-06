* What is IAM Role?
  - You can assign a Role to EC2 or User or Mobile Application to access resources 
  - Role does NOT have a statndard long term credentials. (such as user name and password or access key)
  - However, when you assign a Role to a user a **Temporary Security Credential** will assign to user to provide more secure granular access
  - NOTE: When a user assumes a role, **temporary security credentials** are created dynamically and provided to the user - making it a more secure to grant access.

* Who can use the role? 
  - You can delegate access to:
    - Users
    - Applications
    - Services 
    - That doesn't have access to AWS resources 
 
* why to use Role?
  - **it allows you to delgate access with defined permissions to trusted entities without having to share long-term access keys.**
  - When EC2 accessess AWS resources such as S3 via IAM User, the user's security credentials get stored on that EC2 instance, **THIS SHOULD BE AVOIDED. 
  - When EC2 assumes a role, its credentials are not stored - **Making a secure way of accessing resources**
   
* When to use it?
  - Provide access for services offered by AWS to AWS resource
  - Provide access for an IAM user on one AWS account that you own to access resources in another account that you own.
  - Provide access for external authenticated users (Indetity federation (Facebook, LinkedIN)
  - Provide access to IAM users in AWS account owned by 3rd parties. 
