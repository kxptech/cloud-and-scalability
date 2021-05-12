## VPC

VPC stands for `Virtual Private Cloud` and it is a logical data center inside your AWS infrastructure.

It is composed by Internet Gateways, Virtual Private Gateways, Route Tables, ACLs, Subnets and Security Groups

### Important Notes on VPC

- You can only have 1 Internet Gateway per VPC.

- Security Groups do not span VPCs

- A default VPC doesn't create any subnet nor Internet Gateway

- You're not allowed to do transitive peering between VPCs, so you cannot communicate A->B->C, just A->C.(hub-and-spoke)

### Subnets

### Access Control Lists (ACLs)

#### Remember

- ACLs are stateless, you can have an ACL with multiple subnets, but a subnet can only be associated with one ACL at a time.

- ACLs are composed by a set of rules that are evaluated in a numbered order. And these rules are separated in inbound/outbound rules.

- Network ACLs are stateless, this means that all your allowed responses to inbound traffic are subject to the rules of outbound traffic.

### Security Groups

#### Remember

- Security Groups are stateful

### NAT instances and NAT Gateways

#### Remember

- NAT instances are always behind a security group and must be in a public subnet. The amount of traffic that a NAT instance can handle depends on the instance size. If it is becoming a bottleneck you can increase the instance size and use Auto Scaling groups to provide high availability. NAT instances are not recommended for a real world architecture, because they can be a `single point of failure`. If your NAT instance fails, all your other instances lost connection to the web.

- NAT Gateways are more preferable because they are scaled by AWS and support to 45 Gbps of traffic. They're automatically assigned public IPs and don't need to be patched.

- Although, if you have multiple resources available trough multiple zones and they share the same NAT Gateway, if your NAT gateway availability zone is down all your other resources can loose internet connection. To mitigate this, you have to establish one NAT Gateway per AZ.

### VPC Flow Logs

#### Remember

- After you create a flow log you can't change its configuration

- You can't enable flow logs for VPCs that are peered with your VPC unless the peer VPC is in your account

- `Not all IP traffic is monitored`

### Bastion Hosts/ Jump Boxes

A Bastion Host/ Jump Box is used to administer your EC2 instances (using SSh or RDP) that are in a private subnet

### Direct Connect

It's used to directly connect your data center to AWS, and it's very useful if you have `high throughput` workloads or if you just need a very secure and stable connection.

### Global Accelerator

Is a service that creates accelerators to improve the `availability and performance` of your applications for both local and global users traversing AWS's own global network. It provides you with two `static` IP addresses, but you can bring your own. you can control traffic using the `traffic dials` and put `weights` on individual endpoints.

### VPC Endpoints

### Private Link

### VPN Hub

### Transit Gateway

### VPC Costs
