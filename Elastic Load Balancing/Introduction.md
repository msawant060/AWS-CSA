# Amazon Elastic Load Balancer (ELB)

- Amazon ELB allows you to make your applications highly available by using:
  - Health checks
  - and distributing traffic across a number of instances.
  
#### Consider that you have a WordPress blog which is running on a single t2-micro EC2 instance.
  - Now you publish an article, it goes viral and your site gets hundreds of thousands of requests. Since you are using a single t2-micro, your website will probably crash.
 
 #### So, what can you do to avoid this?

- You may decide to launch a larger instance like an m5-large in place of t2-micro. This is called vertical scaling when you replace an instance with a more powerful instance.

 - But vertical scaling isn’t always economical.

 - Another approach can be to use a bunch of smaller instances like t2-micros and distribute the website traffic between them. 
 
 - And Elastic Load Balancer allows you to do just that.

 - It distributes incoming application or network traffic across multiple targets, such as Amazon EC2 instances, containers, 
   and IP addresses, in multiple Availability Zones.
   
 - It uses health checks to detect which instances are healthy and directs traffic only across those instances
 
 ## Types of Elastic Load Balancers (ELB)
 
  ### 1. Classic Load Balancer (CLB)
  
  -  This is the previous generation load balancer that was used for EC2-classic instances.
  -  It operates on both the request level and the connection level. 
  -  But it DOES NOT support features like host-based routing or path-based routing.
  -  Once configured, it distributes the load across all the registered instances regardless of what is present on the servers.
  -  Hence, it can only be used to distribute traffic to a single URL.
  
    ### 1. Application Load Balancer (ALB)
    
    - This load balancer is specially designed for web applications with HTTP and HTTPS traffic.
    - There is a networking model called the OSI Model (Open Systems Interconnection) that is used to explain how computer networks work. 
    - This model has 7 layers and the top layer is the Application Layer.
    - This load balancer works at this Application Layer, hence the name.
    - It also provides advanced routing features such as:
        - Host-based
        - Path-based routing 
        - Also, it works with containers and microservices.
        
    #### Host-based Routing
    
     - Suppose you have two websites medium.com and admin.medium.com. 
     - Each website is hosted on two EC2 instances for high availability and you want to distribute the incoming web traffic between them.
     - If you were using the CLB you would have to create TWO load balancers, one for each website.
     - But you can do the same thing using a single ALB!
     - Hence you will be saving money as you will only be paying for a single ALB instead of two CLBs.
     
     #### Path-based Routing
     
      - Suppose the website of your company is payzello.com and the company’s blog is hosted on payzello.com/blog. 
      - The operations team has decided to host the main website and the blog on different instances.
      - Using ALB you can route traffic based on the path of the requested URL.
      - So again a single ALB is enough to handle this for you.
     
     
  
    
