* Amazon VPC
  - VPC gives you your OWN Private space in cloud
  - The First Step of creating VPC is deciding the IP Range by providing a Classless Inter Domain Routing (CIDR) block
  - VPC now supports IP4 and IP6.
  - When you choose IP4
      - CIDR range is would be /16 (65, 536) to /28 (16 IP)
  - When you choose IP6
      - CIDR block is fixed /56.
  - Within a VPC, you have a ll the AZs that are part of the regions where the VPC blongs. 
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
| Destination | | Target|
| 10.0.0.0/0  |  | nat-gateway-112a01|
  
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
  - When creating a NAT instance, Disable Source/Destination Check on the instance.
  - NAT instances must be in a public subnet
  - There must be a route out of the private subnet to the NAT, in order for this to work.
  - The amount of traffic that NAT instances can support depends on the instance size. If you are bottlenecking, increase the instance size.
  - Behind a Security Group.
  - You can create high availability using Autoscaling Groups, multiple subnets in different AZs, and a script to automate failover.
* 
