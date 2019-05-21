### Application Load Balancer (ALB)

##### What is it?
  - This load balancer is specially designed for web applications with HTTP and HTTPS traffic. 
  - Distributes the traffic to the registerd targets such as EC2 instances, containers, IP addresses 
  - such that none of them gets overloaded 
  - An Application Load Balancer functions at the application layer, the seventh layer of the Open Systems Interconnection (OSI) model
  
##### Why to use an Application Load Balancer?
  - Hight Availability and Fault Tollerance 
  - Health Check 
  - Supports SSL Certificate 
  - Cross-Zone Load Balacing is **ALWAYS Enable**  

### How does this work?
  picture credit goes to: http://www.whizlabs.com/aws-solutions-architect-associate
  ![ALB.PNG](/ALB.PNG)
  
  After the ALB receives a request, it:
    1. Evaluates the listeners rules in priority order to determine which **rule** to apply.
    2. Monitors the health of the registed targets
    3. Select a healthy target from the target group for forwarding the request
    
### Components

  - Listeners:
  
      - It's a process that checks for connection requests, using the protocol and port that you configure. 
        - Protocol: HTTP and HTTPS
        - Ports : 1 to 65535
        
      - You define the **rules** in the listeners to determine:
          - How the load balancer routes request to targets
       
       - Each listener has a defult rules. It **CAN NOT BE DELETED**
       
       - You can add additional Rules
          
   - Rules:
      
      - It determines where the traffic will be forwarded to
      
      - It has following properties:
          - Priority (1, 2, 3: Lowest number gets higher priority)
          - Actions (one/more)
          - Conditions
                - Host Based (Optinal)
                - Past Based (Optional)                   
   - Health Checks:
    
      - Monitor the health of the registerd targets, so that LB can send the request to health targets
 
  - Target and Target Group:
    
      - Target: Resource to which the requests get forwarded by ALB
      
      - Target Types: EC2, a Container, an IP address
      
      - Target Group: it is used to route requests to one or more registed targets 
      
     
#### NOTE:
   - SSL OFfload: To use the HTTPS you must deploy SSL certificate on ALB itself.    
    
