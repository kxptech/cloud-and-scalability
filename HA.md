# Highly Available Architectures

[Go back](README.md)

## Load Balancers Theory

A load balancer is a physical or virtual device that helps you to balance the network load of your application.

There are three types of load balancers:

- `Application Load Balancer (ALB)`: It is very intelligent and can route traffic to your servers using specific rules. (language, currency location, etc..)

- `Network Load Balancer (NLB)`: It is used for extreme performance of TCP requests.

- `Classic Load Balancer (CLB)`: It is the most cost-effective solution and do simple load balance (`round-robin`). Return 504 if your service is not available.

### X-Forwarded-For Header

If you want to discover you user's `public ip address` when your application is inside a load balancer you must user the `x-forwarded-for` header.

---

[Go back](README.md)
