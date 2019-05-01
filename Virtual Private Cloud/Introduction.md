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
