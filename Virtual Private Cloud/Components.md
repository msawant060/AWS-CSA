#### Amazon VPC
  - VPC gives you your OWN Private space in cloud
  - The First Step of creating VPC is deciding the IP Range by providing a Classless Inter Domain Routing (CIDR) block
  - VPC now supports IP4 and IP6.
  - When you choose IP4
      - CIDR range is would be /16 (65, 536) to /28 (16 IP)
  - When you choose IP6
      - CIDR block is fixed /56.
  - Within a VPC, you have all the AZs that are part of the regions where the VPC blongs. 
  - **Once you create a VPC, you can't alter the IP addresses.** 
  - **Can a VPC SPAN MULTIPLE AZ?** **YES**
  
#### Subnet
  - It's short for subnetwork, which logical sub divison of IP network
  - Using subnets you can divide a network into multiple networks
  - Public subnet: this is used for the resources that needs internet access
  - Private subnet: this is used for the resources that DO NOT needs internet access
  - VPN-Only subnet: this is used when you want to connect your virtual private cloud with your coporate data center.
  - **Subnets are AZ specific. For mutiple AZs, create mutiple subnets** 
  - **YOU CAN'T HAVE (more than one subnet) subnets within a single AZ.**
 
#### Route Table
  - It's a table conscontains a set of rules known as routes, that determines where the traffic is directed. 
  - Every subnet should have a route table. 
  - More than one subnet can have a same route table. 
  - Whenever you create a subnet, it assosiated with the default route table, when you don't assosiated with the specific route table. 
    
#### Internet Gateway
   - This is a component of VPC that allows your VPC to communicate with the Internet. 
   - IG is **Horizontally scaled**, redundant,and highly available components in VPC. 
   - It supports IP4 and IP6 traffic
 
#### Network Address Transaltion
  - You have a database inside the private subnet. And noone from outside internet can access this instance. 
  - However, if you need to download the latest path for this private subnet database server, you need to access internet from server to    outside. In the meantime, outsiders should not access the database server. This functionality is done via NAT. 
  - ** NOTE: NAT devices can be used only for IP4 and IP6 doesn't support it **
  - There are 2 types of NAT devices available in AWS:
      - NAT Instances 
      - NAT GateWays
      
#### NAT Gateways
  - **NO NEED** to Disable Source/Destination Checks on the instance
  - Automatically assigned public IP / You must specify elastic IP address
  - Must update root tables and point them to NAT Gateway
  - Preferred by the enterprise
  - Scale automatically up to 10G
  - More Secure than NAT Instance
  - Having one NAT Gateway in one AZ is not good enough, must me redundant in multiple AZs
  - No need to patch OS
  - Not associated with security groups
  - This is for IPv4
  
#### NAT Instances (NOTE: Teva you didn't do this in demo)
  - When creating a NAT instance,**Need to** Disable Source/Destination Check on the instance.
  - NAT instances must be in a **public subnet**
  - There must be a route out of the private subnet to the NAT, in order for this to work.
  - The amount of traffic that NAT instances can support depends on the instance size. If you are bottlenecking, increase the instance       size.
  - localted **Behind a Security Group**
  - You can create high availability using Autoscaling Groups, multiple subnets in different AZs, and a script to automate failover.

#### Egress-Only Internet Gateway
   - Simalar to NAT Gateway, this is a component of your VPC allows Amazon VPC to communicate with the Internet for **IPv6 traffic**.  
   - NOTE: This is **outbound** ONLY. 
        - It prevents internet IPv6 connection to your instance. Only your instance can connect outside world.
   - The main difference between this and NAT Gateway is:
        - This one is for IPv6
                
#### Network Access Control Lists (NACL)
   - An NACL is a layer of security that acts as a firewall at the **SUBNET LEVEL** in VPC.
   - **NACL are stateless; 
      - if a port open for inbound traffic, the corresponding output traffic is not enables automatically.      
   - Your VPC automatically comes with a default NACL, and by default it allows all inbound and outbound and traffic.
   - By default, each custom NACL denies all inbound and outbound traffic until you add rules. 
   - Each subnet in your VPC must be associated with a network ACL. 
   - If you dont explicitly associate a subnet with a network ACL, the subnet is automatically associated with the default NACL.
   - You can associate a NACL with multiple subnets; 
   - However, A subnet can be associated with only ONE network ACL at a time. When you associate a NACL with a subnet, the previous association is removed.
   - NACLs contain a numbered list of rules that is evaluated in order, starting with the **lowest numbered rule**

#### Security Group
  - A Security Group is a layer of security that acts as a firewall at the **INSTANCE LEVEL** in  a VPC.
  - **Security Groups are stateful; 
      - if a port open for inbound traffic, the corresponding output traffic IS enables automatically.
      - ex: if you allow incoming traffic via SSH on port 22, the outgoing traffic via SSH on port 22 will be allowed.
  - You can attach upto 5 security group for an instance
  - By Default Security Group:
      - All Outbound traffic is ALLOWED
      - NO Inbound traffic is ALLOWED.
   - There are no deny rules in Security Groups. The ONLY way to deny something is NOT ALLOWING.
   
#### AMAZON VPC Peering
   - It helps to connect one virtual private cloud to another 
   - and route the traffic across the vitual private clouds using IPv4 or IPv6 addresses
   - Once the VPC Perring is estabilished the instance running on both VPCs communicate with each other as if they were in the same           network.
   - NOW **You CAN peer VPCs across regions.**
   - You CAN peer VPCs from different AWS accounts 
   - VPC peering connection is a one to one relationship between two VPCs. 
   - You can create multiple VPC peering connections for each VPC that you own. However, **Transitive Peering is NOT SUPPORTED**
      - What is Transitive Peering
      - EX: 
            - Instance A - VPCA connected with Intance B - VPCB
            - Instance A - VPCA connected with Intance C - VPCC
            - NW, Instance B and Instance C can't connec based on the existing connection. You need to create a VPC between B, and C to              make a communication.
      
#### Amazon VPC EndPoint
   - There are many services of AWS that run outside VPC. 
   - For example, S3 is regional service that doesn't run inside the VPC. 
   - Now, if you want to connect to S3 using the VPC either via Internet or your corporate network!!!
        - Here is where we need **VPC End POINT*
   - VPC Endpoint gives you the ability to connect to VPC to S3 directly using private connection.
   - Currently VPC Endpoint supports **S3 and DynamoDB**
   - It's a virtual device scale horizontally and it redundant, providing high availability. 
        
 
#### Difference between Security Group and NACL?
  
  | Security Group | NACL|
  |-------------|-------|
  | Instance Level  |  Subnet Level|
  | Stateful | Stateless |
  | Supports ONLY ALLOW rules| Supports ALLOW and DENY Rules|
  
  
   2. What is the difference between NAT Instance and NAT Gateway?
   
#### Elastic Network Interface (ENI)
  - It allows user to create one or more Network interface and attach to an EC2 instance. 
  - As name suggested you can attach and detach anytime
  - EIN has the following features:
    1. A MAC address
    2. One Public IPv4 address
    3. One Public IPv6 address
    4. One Primary PRivate IP4 address
    5. One or more secondary private IP4
    6. One elastic IP address (IPv4) per private IPv4 address
    7. One or more Security Group
    8. A source/destination check flag and description
  - You **CAN NOT** change the default network interface of an instance, which is also known as a primary network interface (eth0)
  - Adding EIN doesn't make any differenece in the network instance bandwidth 

   
