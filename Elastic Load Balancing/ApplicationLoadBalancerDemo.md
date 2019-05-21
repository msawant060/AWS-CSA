### Create an Application Load Balancer and Configure Path based rule

1. Create 2 Target Groups with 2 EC2 instances in each
2. Target Group 1: Image Target Group
3. Instances EC2a and EC2b from these target group display a message that "We are from Image Server"
4. Target Group 2: Video Target Group
5. Instances EC2c and EC2d from these target group display a message that "We are from Vode Server"
6. Create an Application Load Balancer and configure that
 if the URL has /pictures* redirect the target group 1
 if the URL has /videos* redirect the target group 2
 else redirect an EC2 instance out of both target groups saying that "I'm not from any target groups!"
 
 
 
