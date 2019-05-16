# CloudWatch

### Amazon CloudWatch helps to monitor and reporting

### Why CloudWatch is Required? or Usage of CloudWatch
  * Monitoring Compute Layers - EC2, ELB, EBS
      - CPU Utilization
      - Memory Utilization
      - Disk Utilization
  * Monitoring S3 bucket
      - Bucket Storage Size
      - Total Objects Stored
      - Request Metrics
  * Monotoring AWS Billing
      - Notfy when the autual usage reaches estimated usage
  * Get a unified view of health check
      
### How Amazon CloudWatch works?
   - Step 1: Collect: It collects the information in the following formats:
        - Logs
        - Metrics
        - Events
   - Step 2: Monitor: It provides the following ways to monitor the data:
        - Dashboard
        - Alarms
   - Step 3: Act: It acts in the following forms
        - Alarms
        - Events
   - Step 4: Analyze: 
       - Finally it helps to Analze the data

### Step 1: Collect - Metrics (Default & Custom)
  - Default Metrics: EC2 Metrics
      - CPU
          - CPU Utilization
      - Disk
          - Disk ReadOps
          - Disk WriteOps
          - Disk ReadBytes
          - Disk WriteBytes
      - Network
          - NetworkIn
          - NetworkOut
          - NetworkPacketsIn
          - NetworkPacketsOut
      - Status
          - StatusCheckFailed
          - StatusCheckFailed_Instane
          - StatusCheckFailed_System
          
 - Custom Metrics: EC2 Metrics
      - Memory
          - Memory utilization
          - Memory used
          - Memory available
      - Disk
          - Disk space used
          - Disk space avail
          - Disk space util
       - Swap
          - Swap used
          - Swap util
   - EBS Metrics 
        - EBS ReadOPS, EBS WriteOps, EBS ReadBytes, EBS WriteBytes, EBSIOBalance%, EBSBytesBalance%
        
### Step 1: Monitoring 
    - Basic Monitoring
        - 5 minutes period
        - Free of charge
        - Enable by Default
    - Detailed Monitoring
        - 1 minute period
        - Must be Enable at the **Instance level
        - Not Free
        
        
      
