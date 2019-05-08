Source URL: https://www.whizlabs.com/aws-solutions-architect-associate/

# IAM Policy

* A policy is an entity in AWS that, when attached to an identity or resource defines their permissions. 
* A policy contains different **Permission** determines whether the request is **allowed or denied**
* Policies are stored in AWS JASON documents. 
* Policies are attached to either principals (Users, Groups, Roles) or to resources (e.g S3 bucket)

## Types of Policies 

### Identitiy Based Policies

* Policies that can be attached to a principal or identity such as IAM Users, Roles, Groups 
* This policies determines the following:
    - What actaions that identity can perform
    - Which resource 
    - Under which condition 
 * It can be further categoried in the following 2
    - Managed Policies
        - AWS Managed: Create and managed by AWS
        - Customer Managed:  Create and managed by AWS users. It provides more precise control over your policies than AWS managed policies. 
     - Inline Policies: Create and manage and that are embedeed directly in the single user or role. 
 *  Here the resource informtion can be attached to a principal
        
### Resource Based Policies

* Policies that can be attached to a resource, such as S3 bucket
* This policies determines the following:
    - What actaions that identity can perform    
    - Under which condition 
 * These are inline policies and there are no managed policies. 
 * Here the principla informtion can be attached to a resource
 
 ## Template of an IAM Policy
 
 Note: Image is from https://www.whizlabs.com
 
 ![policy.PNG](/policy.PNG)
 
 **If a policy include mutiple statements. AWS applies a "Logical OR" accross the statements at evaluation time**
 
 ## Conflicting Permissions
 
 * When IAM policy has contracdicting permissions what would happen?
 * One policy allow S# bucket access while the other policy is not? 
 * the problem would be resolved based on **Polcy Evaluation Logic**
 
 ### Policy Evaluation Logic 
 
 * If a polcy doesn't mention allow/deny is always deny (**Defauly Deny**)
 * If there is an explicit deny then **Always Deny** - Explict Deny
 * If there is an explicit allow then **Allow** - Explict Allow
 * If there is an explicit **Allow* and explict **Deny" then **Deny**
 
 * All requests are Denied by Default
 * An Explicit Allow over write the Defauly Deny 
 * But, Explict Deny over write the Explict Allow
 
 
