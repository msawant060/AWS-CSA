# Virtual Private Cloud [VPC]

* Amazon VPC lets you create your own private cloud. In other words, it allows you to logically isolate a section of the cloud. 

* You can provision any resource in this logically isolated region, and you have COMPLETE CONTROL over the network.

* You have complete control over you virtual network environment including:
  - Selection of your own IP address range
  - Creation of Subnets 
  - Configuration of Route Tables 
  - Network Gateways.

* You can easily customize the network config for your VPC. 
  - For example, you can create a public facing subnet of your webservers that has access to the internet, 
  - and place your backend systems such as databases or application servers in a private-facing subnet with no internet access.
 
 * You can leverage multiple layers of security,
   - including security groups and network access control lists, to help control access to EC2 instances on each subnet.
 
#### NOTE: Private and public subnets within a VPC can only have ONE subnet per AZ

* How to calculate the available Total IP address based on CIDR block
----------------------------------------------------------------------
 - How many total IP addresses for the the following CIDR block: 10.0.0.0/26  
    - 2 ^ (32 - 26) = 2 ^ 6 = 64 IP addresses
    - First IP: 10.0.0.0
    - Last IP:   10.0.0.63
 
 * How to divide the above 64 IP address in 4 blocks.
 
 - Block 1: 10.0.0.0/28  (2 ^ (32 - 28) = 2 ^ 4 = Total 16 IPs)
   - IP Address Range: 10.0.0.0 to 10.0.0.16
 - Block 2: 10.0.0.16/28 (2 ^ (32 - 28) = 2 ^ 4 =  Total 16 IPs)
   - IP Address Range: 10.0.0.16 to 10.0.0.31 
 - Block 3: 10.0.0.32/28 (2 ^ (32 - 28) = 2 ^ 4 = 16 IPs)
   - IP Address Range: 10.0.0.32 to 10.0.0.47 
 - Block 4: 10.0.0.48/28 (2 ^ (32 - 28) = 2 ^ 4 = 16 IPs)
   - IP Address Range: 10.0.0.48 to 10.0.0.63 
  
  ### NOTE: In AWS Each Subnet mask will take 5 IP address for private usage. (First 4 and the last one will be gone) 
  
  * So, basically, Each Block will have 11 IP address available to use
