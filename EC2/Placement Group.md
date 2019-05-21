### Placement Group

  - When you launch a new EC2 instance, the Placement Group determines how the EC2 instances are placed on the underlying hardware/hypervisor. 
  
  - Types of Placement Groups
     - Cluster - Instances on a Single Hypervisor in a single AZ
     - Spread - Each instance on a **Seperate Hypervisor in a Seperate AZs**.

  - Difference between cluster and Spread Placement Group
  
  - 1. Cluster Placement Group
    - Instances on a Single Hypervisor in a single AZ
    - Recommended to launch Same type of instances, all at the same time
    - If you try to add more instances to an existing placement group, or try to launch more than one instance type in the placement group
      you might get **insufficent capacity error**
  
  - 2. Spread Placement Group 
    - Each instance on a **Seperate Hypervisor in a Seperate AZs**.
    - It allows you to launch different types and different time
    - Max 7 running instances oer AZ per group
    - Not supported for Dedicated instances and Dedicated Host. 
  
