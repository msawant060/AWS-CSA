* Amazon VPC
  - VPC gives you your OWN Private space in cloud
  - The First Step of creating VPC is deciding the IP Range by providing a Classless Inter Domain Routing (CIDR) block
  - VPC now supports IP4 and IP6.
  - When you choose IP4
      - CIDR range is would be /16 (65, 536) to /28 (16 IP)
  - When you choose IP6
      - CIDR block is fixed /56.
  - Within a VPC, you have all the AZs that are part of the regions where the VPC blongs. 
  - **Once you create a VPC, you can't alreat the IP addresses.** 
  - **VPC is limited to a region. You CAN NOT HAVE A VPC SPANNING REGIONS.**
  
* Subnet
  - It's short for subnetwork, which logical sub divison of IP network
  - Using subnets you can divide a network into multiple networks
  - Public subnet: this is used for the resources that needs internet access
  - Private subnet: this is used for the resources that DO NOT needs internet access
  - VPN-Only subnet: this is used when you want to connect your virtual private cloud with your coporate data center.
  - **Subnets are AZ specific. For mutiple AZs, create mutiple subnets** 
  - **Of course, YOU CAN'T HAVE (more than one subnet) subnets within a single AZ.**
  - **VPC are region specific. For mutiple regions,, create different VPCs.**

* Route Table
  - It's a table consisting of certain rules known as routes, that determines where the traffic is directed. 
  - Every subnet should have a route table. 
  - More than one subnet can have a same route table. 
  - Whenever you create a subnet, it assosiated with a main route table, when you don't assosiated with the specific route table. 
  - Route table has 2 columns. (Destination and Target)
     - Target: this is where the traffic is direted to
     - Destination: It specify the IP range that can be directed to target. 
     
  | Destination | Target|
  |-------------|-------|
  | 10.0.0.0/0  |  nat-gateway-112a01|
  
* Internet Gateway
   - This is a component of VPC that allows your VPC to communicate with the Internet. 
   - IG is horizontally scaled, redundant,and highly available components in VPC. 
   - It supports IP4 and IP6 traffic
 
* Network Address Transaltion
  - You have a database inside the private subnet. And noone from outside internet can access this instance. 
  - However, if you need to download the latest path for this private subnet database server, you need to access internet from server to outside. However, outsiders can't access the private subnet. This functionality is done via NAT. 
  - ** NOTE: NAT devices can be used only for IP4 and IP6 doesn't support it **
  - There are 2 types of NAT devices available in AWS:
      - NAT Instances 
      - NAT GateWays
    
* NAT Instances
  - When creating a NAT instance,**Need to** Disable Source/Destination Check on the instance.
  - NAT instances must be in a public subnet
  - There must be a route out of the private subnet to the NAT, in order for this to work.
  - The amount of traffic that NAT instances can support depends on the instance size. If you are bottlenecking, increase the instance size.
  - Behind a Security Group.
  - You can create high availability using Autoscaling Groups, multiple subnets in different AZs, and a script to automate failover.

* NAT Gateways
  - **NO NEED** to Disable Source/Destination Checks on the instance
  - Automatically assigned public IP / You must specify elastic IP address
  - Must update root tables and point them to NAT Gateway
  - Preferred by the enterprise
  - Scale automatically up to 10G
  - More Secure than NAT Instance
  - Having one NAT Gateway in one AZ is not good enough, must me redundant in multiple AZs
  - No need to patch OS
  - Not associated with security groups
 
 * Network Access Control Lists (NACL)
   - An NACL is a layer of security that acts as a firewall at the **SUBNET LEVEL**.
   - **NACL are stateless; 
      - if a port open for inbound traffic, the corresponding output traffic is not enables automatically.      
   - Your VPC automatically comes with a default NACL, and by default it allows all inbound and outbound and traffic.
   - By default, each custom NACL denies all inbound and outbound traffic until you add rules. 
   - Each subnet in your VPC must be associated with a network ACL. 
   - If you dont explicitly associate a subnet with a network ACL, the subnet is automatically associated with the default NACL.
   - You can associate a NACL with multiple subnets; 
   - However, A subnet can be associated with only ONE network ACL at a time. When you associate a NACL with a subnet, the previous association is removed.
   - NACLs contain a numbered list of rules that is evaluated in order, starting with the lowest numbered rule
   
   
   
   
   
   * Questions 
   1. What is the difference between Security Group and NACL?
   
   2. What is the difference between NAT Instance and NAT Gateway?
   
   
