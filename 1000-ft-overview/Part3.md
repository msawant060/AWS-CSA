## Part 2. AWS Services Overview [Networking]

### Networking

It helps you to isoloate your cloud infrastructure.

1. Amazon Virtual Private Cloud (VPC)
   - Using the Amazon VPC you can isolate the cloud resource within your own private virtual network.
   - You can bring your own IP addresses, subnet masks, route table, network gateways.

2. Amazon Route 53
   - This is a Domain Name System Web service. (DNS)
   - Amazon Route 53 is IP4 and as well as IP6 compliant.  
   - It's highly avaiable, scalable, and its SLA is 100% uptime.
   
3. Elastic Load Balancing (ELB)
   - It allows to you automatically distribute the load across multiple Amazon EC2 instances. 
   - It supports load balancing of HTTP, HTTPS, and TCP traffice to Amazon EC2 instances. 
   - ELB can also do health checks so you can remove unhealthy/failing instances. 
   - ELB can support Amazon EC2 instances across different AZs within a region.
 
4. AWS Direct Connect
   - Using AWS Direct Connect, you can establish private, dedicated network connectivity from your data ceter to AWS. 
   - It provides 1 Gbps and 10 Gbps connections.
