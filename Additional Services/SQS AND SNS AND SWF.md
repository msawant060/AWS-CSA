### Simple Queue Service

* What is SQS?
  - It is a fully managed message **queuing service** that enables you to **decouple and scale**
      - microservices, 
      - distributed systems, 
      - and serverless applications. 
* Using SQS, you can send, store, and receive messages between software components at any volume, 
  without losing messages or requiring other services to be available
* Amazon SQS offers two queue types for different application requirements:
  - Standard Queues
  - FIFO Queues

| Standard Queues | FIFO Queues |
|-----------------|-------------|
| Unlimited Throughput: it supports nearly unlimited number of transactions per second (TPS) per API action. | High Throughput: By default, FIFO queues support up to 300 messages per second (300 send, receive, or delete operations per second). When you batch 10 messages per operation (maximum), FIFO queues can support up to 3,000 messages per second |
| At-Least-Once Delivery: A message is delivered at least once, but occasionally more than one copy of a message is delivered | Exactly-Once Processing: A message is delivered once and remains available until a consumer processes and deletes it. **Duplicates aren't introduced into the queue.**| 
| Best-Effort Ordering: Occasionally, messages might be delivered in an order different from which they were sent.| First-In-First-Out Delivery: The order in which messages are sent and received is strictly preserved (i.e. First-In-First-Out).| 

- SQS is pull-based, not pushed based
- Messages are 256Kb in size
- Messages can be kept in the queue from 1 minute to 14 days
- Default retention period is 4 days

### Simple Notification Service

* What is SNS? 
  - It is a highly available, durable, secure, fully managed **publisher/subscriber messaging service** that enables you to **decouple**
      - microservices, 
      - distributed systems, 
      - and serverless applications. 
 * Amazon SNS provides topics for high-throughput, push-based, many-to-many messaging. 
 * Using Amazon SNS topics, your publisher systems can fan out messages to a large number of subscriber endpoints for **parallel              processing**, including:
      - Amazon SQS queues, 
      - AWS Lambda functions, 
      - and HTTP/S webhooks. 
  * Additionally, SNS can be used to fan out notifications to end users using mobile push, SMS, and email. 
  
  ### Simple Workflow Service
  
  * What is SFS?
    - It helps developers build, run, and scale background jobs that have parallel or sequential steps.
    - If your app's steps take more than 500 milliseconds to complete, you need to track the state of processing, 
      and you need to recover or retry if a task fails, Amazon SWF can help you.
  
  
  
