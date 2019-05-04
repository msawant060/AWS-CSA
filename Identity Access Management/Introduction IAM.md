# IAM - Identity Access Management

## What is IAM?
- It's a web service that enables you to manage the access to AWS services and resource **securely**
- It helps you to control who is authenticated and authorized to use these services and resources.
- Service usage is **FREE**
- Allow you to manage users and their level of access management to the AWS console. 
- IAM is **globally available and NOT specified to region**
- IAM is universal 

## What can you do with IAM?

- Centralized control of your AWS account
- Shared Access to your AWS account
- Granular permissions
- Identity Federation
- Access to 3rd party service, Active Directory, Facebook, Linkedin
- Multifactor Authentication (MFA)
- Provide temporary access for users/devices and services where necessary
- Set up and manage password rotation
- Integrates with many different AWS services
- Supports PCI, DSS compliance

## Terminologies

 - Users : End users such as people, employees of an organization.
 - Groups: A collection of users. Each user in the group will inherit the permissions of the group
 - Policies: Policies are made up of documents, called policy documents. These documents are in a format called JSON and they give permissions as to what a User/Group/Role is able to do
 - Roles: You create roles and then assign them to AWS resource 

## Important Points

 - The “root account” is simply the account created when you first setup your AWS account. 
 - It has complete Admin access.
 - New Users have NO permissions when first created 
 - New users are assign Access Key ID & Secret Access Keys when first created. (Note these are not the same as a password. You only get to view these once) 

