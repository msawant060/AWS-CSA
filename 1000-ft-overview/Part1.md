# Regions, Availability Zones (AZ), Edge Locations

### Region

1. AWS Region is a physical, geographical area or location. Each Region is completely independent. 
2. This achieves the greatest possible fault tolerance and stability.
3. Each Region has multiple (2 or more), isolated locations known as Availability Zones (AZ).
4. Each Availability Zone is isolated, but the Availability Zones in a Region are connected through low-latency links.

### Available Region

1. Your AWS account determines the Regions that are available to you
   - An AWS account provides multiple Regions so that you can launch Amazon EC2 instances in locations that meet your requirements. 
   - Ex: You might want to launch instances in Europe to be closer to your European customers or to meet legal requirements.
2. An AWS GovCloud (US-West) account provides access to the AWS GovCloud (US-West) Region only
3. An Amazon AWS (China) account provides access to the Beijing and Ningxia Regions only.

### Availability Zones (AZ)

1. AWS Availability Zones are one or more discrete data centers.
2. Each with redundant power, networking and connectivity housed in separate facilities. 
3. Deploying your application across multiple Availability Zones is useful for redundancy, low latency and fault tolerance.

### Edge Locations
1. AWS Edge Locations are locations around the world meant for caching content, enhancing the user experience, reducing latency. 
2. Edge locations are specifically used by AWS Cloudfront and AWS CDN. 
3. Every Region is has its own set Availability Zone's and Edge Locations.
