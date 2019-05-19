#### Demo1: Create a VPC with 4 subnets. (2 public subnets, 2 private subnets)

1. Create a VPC called Teva_VPC
  1.1 Region: virginia
  1.2 IP:10.0.0.0/16 
  
  ![Step1.PNG](/Step1.PNG)
  
  2. Create 4 subnets 
  2.1 Public Subnet - Public_A
    2.1.1 IP Range: 10.0.0.0/28
    2.1.2 AZ: East a
  2.2 Public Subnet - Public_B
    2.2.1 IP Range: 10.0.0.16/28
    2.2.2 AZ: East b
  2.3 Private Subnet - Private_A
    2.3.1 IP Range: 10.0.0.32/28
    2.3.2 AZ: East a
  2.4 Private Subnet - Private_B
    2.3.1 IP Range: 10.0.0.48/28
    2.3.2 AZ: East b

3. Create an Internet Gateway. 

4. Create a NAT Gateway. (NOTE: **Here YOU NEED TO CHOOSE PUBLIC IP)

5. Check the Route Table Routes. When you create a VPC, a route table will be created
  By default the above 4 subnets were assosiated with them.
  5.1 Change the default route table name as Teva_VPC_Default_Public
  5.2 Assosiate the default subnets
  5.3 Edit Routes
  
  5.4 Create second private route table 
  5.5 Edit the subnet assosiated with the private route table
  5.6 Edit the route table to make a connection to NAT Gateway
  
  
   
