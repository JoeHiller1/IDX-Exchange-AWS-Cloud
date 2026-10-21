# AWS storage and database decision guide

| Service | Use this when… |
|---|---|---|
| **Amazon S3** | You need to store objects in a durable and scalable manner that can be accessed via an API. |
| **Amazon EBS** | You need persistent storage for your software connected to an EC2 instance where the latency is low. |
| **Amazon EFS** | Multiple linux instances need access to the same data within a file system, and you prioritize automatic elasticity and high availability |
| **Amazon RDS** | You need to run a traditional, structured SQL database in the cloud where management of the database server by you is not necessary. |
| **Amazon DynamoDB** | You need to store a NoSQL database, and you need a highly scalable low-latency application that has predictable key-value access patterns. |
