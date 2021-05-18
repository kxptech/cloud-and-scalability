# Highly Available Architectures

[Go back](README.md)

## Load Balancers Theory

A load balancer is a physical or virtual device that helps you to balance the network load of your application.

There are three types of load balancers:

- `Application Load Balancer (ALB)`: It is very intelligent and can route traffic to your servers using specific rules. (language, currency location, etc..)

- `Network Load Balancer (NLB)`: It is used for extreme performance of TCP requests, and when you need a fixed IP address for your ELB

- `Classic Load Balancer (CLB)`: It is the most cost-effective solution and do simple load balance (`round-robin`). Return 504 if your service is not available.

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

---

[Go back](README.md)
