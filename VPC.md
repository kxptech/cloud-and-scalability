## VPC

VPC stands for `Virtual Private Cloud` and it is a logical data center inside your AWS infrastructure.

It is composed by Internet Gateways, Virtual Private Gateways, Route Tables, ACLs, Subnets and Security Groups

#### Important Notes on VPC

- You can only have 1 Internet Gateway per VPC.

- Security Groups do not span VPCs

- A default VPC doesn't create any subnet nor Internet Gateway

### Access Control Lists (ACLs)

ACLs are stateless, you can have an ACL with multiple subnets, but a subnet can only be associated with one ACL at a time.

ACLs are composed by a set of rules that are evaluated in a numbered order. And these rules are separated in inbound/outbound rules.

### Security Groups

Security Groups are stateful

### Hub-and-spoke

You're not allowed to do transitive peering, so you cannot communicate A->B->C, just A->C.

### Subnets

### NAT instances and NAT Gateways

NAT instances are always behind a security group and must be in a public subnet. The amount of traffic that a NAT instance can handle depends on the instance size. If it is becoming a bottleneck you can increase the instance size and use Auto Scaling groups to provide high availability. NAT instances are not recommended for a real world architecture, because they can be a `single point of failure`. If your NAT instance fails, all your other instances lost connection to the web.

NAT Gateways are more preferable because they are scaled by AWS and support to 45 Gbps of traffic. They're automatically assigned public IPs and don't need to be patched.

Although, if you have multiple resources available trough multiple zones and they share the same NAT Gateway, if your NAT gateway availability zone is down all your other resources can loose internet connection. To mitigate this, you have to establish one NAT Gateway per AZ.

### Access Control List (ACL)

### VPC Flow Logs

### Direct Connect

### Global Accelerator

### VPC End Points

### Private Link

### VPN Hub

### Transit Gateway

### VPC Costs
