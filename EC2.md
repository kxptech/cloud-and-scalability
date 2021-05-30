# EC2

[Go back](README.md)

EC2 is AWS service that lets you manage servers on the cloud. It basically changed how we develop software.

## Pricing Models

- On Demand: Allows you to pay by the hour or second, at a fixed rate. With no commitment. It's useful for applications with unpredictable workloads that cannot be interrupted.

- Reserved: Provides you with a capacity reservation, and offer significant discount on the hourly charge. But, you have to sign a contract of 1 or 3 years. It's useful for applications that require reserved capacity and have a predictable usage.The reserved pricing model includes 3 pricing types: Standard, Convertible, and Scheduled.

- Spot: Enables you to bid whatever price you want for the instance capacity, proving for even grater savings. But your application must have flexible start and end times because it uses AWS spare resource capacity.

- Dedicated Hosts: You can allocate a physical EC2 server dedicated for your use. You can save some money if you need a server bound software license.

## EBS (Elastic Block Store)

It is basically your hard drive on the cloud. Providing you block storage volumes for use with EC2. Your EBS volume is `always` created in the same AZ as your EC2 .

### 5 different types od EBS Storage

- General Purpose (SSD): It is suitable for most workloads

- Provisioned IOPS (SSD): Created for databases and mission-critical applications

- Throughput Optimized HDD: Big data applications and Data warehouses

- Cold HDD: `Lowest` cost HDD volume designed for less frequently accessed workloads. eg. File Servers.

- EBS Magnetic: Previous generation of HDD where data is infrequently accessed.

---

[Go back](README.md)
