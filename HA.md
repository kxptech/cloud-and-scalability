# Highly Available Architectures

[Go back](README.md)

## Load Balancers Theory

A load balancer is a physical or virtual device that helps you to balance the network load of your application.

There are three types of load balancers:

- `Application Load Balancer (ALB)`: It is very intelligent and can route traffic to your servers using specific rules. (language, currency location, etc..)

- `Network Load Balancer (NLB)`: It is used for extreme performance of TCP requests, and when you need a fixed IP address for your ELB

- `Classic Load Balancer (CLB)`: It is the most cost-effective solution and do simple load balance (`round-robin`). Return 504 if your service is not available.

Instances monitored by ELBs are reported as InService/OutOfService

### X-Forwarded-For Header

If you want to discover you user's `public ip address` when your application is inside a load balancer you must get the `x-forwarded-for` header.

### Sticky Sessions

Sticky sessions bind a user's session to a specific EC2 instance. This feature can be enabled on CLBs and ALBs

### Cross Zone Load Balancing

It allows your ELB to route traffic to instances outsides its AZ.

### Path Patterns

Its very useful for micro-services because it enables your load balancer to route traffic to specific instances based on the request's path.

## Auto Scaling

Auto Scaling is composed by 3 components

### Groups

Groups are logical components where you're going to put your EC2 instance in. You can have a Application group, Database group ... etc.

### Configuration Templates

Groups use a launch template/configuration to launch your EC2 instances and you can specify everything related to the EC2 configuration in it.

### Scaling Options

There are several ways that you can scale your Auto Scaling groups.

- Maintain current instance levels at all times: Pretty self-explanatory, you can specify a number of instances to be running at all times. To maintain the current number of instances AWS performs periodic health checks.

- Scale manually: It is the most basic type of scaling, where you cna only specify the maximum, minimum or desired capacity, and AWS takes care of all the rest.

- Schedule based scaling: Self-explanatory too :). It's very useful if you know exactly when you need to increase/decrease the number of your instances.

- On demand: The most popular way of scaling because it let you use `scaling policies`, where you define parameters that control the scaling process.

- Predictive scaling : A relatively new form of scaling where you combine AWS Auto Scaling and EC2 Auto Scaling, proactive/reactive approach.

### How to design HA Architectures

> Netflix simian army [link](https://netflixtechblog.com/the-netflix-simian-army-16e57fbab116)

---

### Elastic Beanstalk

Elastic Beanstalk lets you deploy your applications without worrying about the infrastructure. You basically upload your code and it creates the provisioning, load balancing, scaling and health monitoring.

### Highly Available Bastions

You can make your bastions highly available taking two approaches

#### Expensive (Prod environment)

Two hosts in two separate AZs, and use a Network Load Balancer with static IP addresses to fail over. You can't use an Application Load Balancer, because it is layer 7, you need layer 4 to do SSH.

#### Cheap (Dev environment)

One host in one AZ behind an Auto Scaling group with health checks and a fixed elastic IP address, if one fails, the health check will fail and the Auto Scaling Group will provision another EC2 in a separate AZ.

### On Premise Strategy Services

- Database Migration Service (DMS)

- Server Migration Service (SMS)

- AWS Application Discovery Service

- VM Import/Export

- Download Amazon Linux 2 as an ISO

[Go back](README.md)
