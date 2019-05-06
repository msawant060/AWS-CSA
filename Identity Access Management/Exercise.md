1. Task #1: Create a user Bob and assign Indentity Based Policy (Here you need to use create AWS Managed and Customer Managed Policies)
    - Step 1: Create a user Bob with Cosole Access and Programatic Access
        - You need to give a custom password and allow user to change it in the first login
    - Step 2: Set Managed Policy:
        - Give EC2 full access
    - Step 3: Set Custom Managed Policy:      
        - Deny VPC and Running EC2, Create Tag, and Delete Tag 
              * when you create Custom Managed Policy You can choose Visual Editor instead of Jason.
                  1. Service: Select the Service VPC
                  2. Actions: See "Swith to deny permission" DO NOT Click it. Makt sure you have permission "denied"
                  3. See the Access Levels: (List, Read, Tagging, Write)
                  4. Select the Resources: All resources 
                  5. Review and Save the policy.
                  
        - Final policy needs to be like the following:    
        
        - ![Lab1.PNG](/Lab1.PNG)
        
     - Step 4: Attach the policy to user and your screen needs to look like the following:
              - ![Lab2.PNG](/Lab2.PNG)
  
#### NOTICE: Here you are over writing same policy and the see the outcome of it. Pretty cool huh! :) 


![IAM_lab1.PNG](/IAM_lab1.PNG)
