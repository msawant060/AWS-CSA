#### Demo1: Create a VPC with 4 subnets. (2 public subnets, 2 private subnets)

- 1. Create a VPC called Teva_VPC
      - 1.1 Region: virginia
      - 1.2 IP:10.0.0.0/16   
  
  ![Step1.PNG](/Step1.PNG)
  
- 2. Create 4 subnets 
    - 2.1 Public Subnet - Public_A
       - 2.1.1 IP Range: 10.0.0.0/28
       - 2.1.2 AZ: East a 
       
       ![Subnet1.PNG](/Subnet1.PNG)
       
    - 2.2 Public Subnet - Public_B
        - 2.2.1 IP Range: 10.0.0.16/28
        - 2.2.2 AZ: East b
        
         ![Subnet2.PNG](/Subnet2.PNG)
        
    -  2.3 Private Subnet - Private_A
       - 2.3.1 IP Range: 10.0.0.32/28
       - 2.3.2 AZ: East a
       
       ![Subnet3.PNG](/Subnet3.PNG)
       
    - 2.4 Private Subnet - Private_B
       - 2.4.1 IP Range: 10.0.0.48/28
       - 2.4.2 AZ: East b
       
       ![Subnet3.PNG](/Subnet3.PNG)

- 3. Create an Internet Gateway. 
    - 3.1 Step 1 
     ![IG.PNG](/IG.PNG)
     
    - 3.2 Step 2 - Attach GateWay to VPC
      ![NAT%20Gateway.PNG](/NAT%20Gateway.PNG)    

 - 4. Create a NAT Gateway. (NOTE: **Here YOU NEED TO CHOOSE PUBLIC SUBNET)
   ![NAT%20Gateway.PNG](/NAT%20Gateway.PNG) 
 
 - 5. Check the Route Table Routes. When you create a VPC, a route table will be created By default the above 4 subnets were assosiated with them. Change the default route table name as Teva_VPC_Default_Public
  
     - 5.1 Assosiate the default subnets
     ![subnet_Assosiation.PNG](/subnet_Assosiation.PNG)
  
     - 5.2 Edit Routes from Route Table to create public subnets 
        - 5.3.1 Add the Intenet Gateway to Route Table.  Now, the subnets assosiatd with this route table becomes public subets 
        ![Routes2.PNG](/Routes2.PNG)
  
     - 5.3 Create second route table to create private subnets 
     ![PrivateRT.PNG](/PrivateRT.PNG)
     
     - 5.4 Edit the subnet assosiated with the private route table
     ![PrivateSubnetAssosiation.PNG](/PrivateSubnetAssosiation.PNG)
     
      - 5.5 Edit the route table to make a connection to NAT Gateway
      ![AddNAtGateWayPAth.PNG](/AddNAtGateWayPAth.PNG)
  
   
