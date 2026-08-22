<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# VPC Traffic Flow and Security

**Project Link:** [View Project](http://nextwork.ai/projects/aws-networks-security)

**Author:** Immad Khan  
**Email:** immadkhanr73@gmail.com

---

## VPC Traffic Flow and Security

![Image](http://nextwork.ai/authentic_red_gentle_walrus/uploads/aws-networks-security_92b0b0b4)

---

## Introducing Today's Project!

### What is Amazon VPC?

An Amazon VPC is a secure, isolated virtual network on AWS. It is useful because it gives you complete control over your network environment, including IP ranges, subnets, route tables, and gateways, keeping your cloud resources safe.

### How I used Amazon VPC in this project

I used VPC to manage traffic flow and security. I mapped route tables to direct public subnet traffic, configured security groups for instance firewalls, and built custom Network ACLs for stateless subnet-level packet filtering.

### One thing I didn't expect in this project was...

I didn't expect the contrast between stateful security groups and stateless Network ACLs. Managing security at both the instance and subnet levels gave me a true understanding of multi-layered cloud defense.

### This project took me...

This project took me approximately 2.5 hours. This time was spent carefully designing custom routing rules, implementing stateful security groups alongside stateless Network ACLs, and deploying global network assets using the AWS CLI.

---

## Route tables

Route tables are sets of rules, called routes, that determine where network traffic from subnets or gateways is directed. They act as a network directory or GPS to ensure data packets reach their intended destinations.

A subnet needs a route table with a route directing internet-bound traffic (0.0.0.0/0) to an Internet Gateway. Without this route, resources in the subnet cannot send or receive traffic outside the private VPC network.

![Image](http://nextwork.ai/authentic_red_gentle_walrus/uploads/aws-networks-security_0a07b191)

---

## Route destination and target

Destination is the IP address range (CIDR block) that the traffic is trying to reach. Target is the gateway, network interface, or connection through which that traffic must pass to reach its destination.

The new route has a destination of 0.0.0.0/0 (representing all IPv4 internet traffic) and a target of my Internet Gateway (NextWork IG, igw-0bf3d476198229860), directing external traffic out to the public internet.

![Image](http://nextwork.ai/authentic_red_gentle_walrus/uploads/aws-networks-security_0a07b191)

---

## Security groups

Security groups are resource-level, stateful virtual firewalls in AWS. They regulate traffic flow to and from specific resources, like EC2 instances, by evaluating custom inbound and outbound security rules.

### Inbound vs Outbound rules

Inbound rules control traffic allowed to enter associated resources. For this security group, I configured an inbound rule allowing HTTP traffic on port 80 from Anywhere-IPv4 (0.0.0.0/0) to let public users access my web server.

Outbound rules determine what traffic can leave your AWS resources. For this project, we kept the default security group configuration, which automatically allows all outbound traffic (0.0.0.0/0) on all ports to the public internet.


![Image](http://nextwork.ai/authentic_red_gentle_walrus/uploads/aws-networks-security_92b0b0b4)

---

## Network ACLs

A Network ACL (NACL) is a stateless virtual firewall at the subnet level that regulates inbound and outbound traffic. It evaluates traffic sequentially using numbered rules to decide whether to allow or deny data packets entering the subnet.

### Security groups vs. network ACLs

Security groups act as stateful firewalls at the resource level (e.g., EC2), while Network ACLs act as stateless firewalls at the subnet boundary. Security groups support allow rules only, whereas NACLs support both allow and deny rules.

---

## Default vs Custom Network ACLs

### Similar to security groups, network ACLs use inbound and outbound rules

A default Network ACL automatically permits all inbound and outbound traffic to and from the subnet (using Rule 100 for 0.0.0.0/0). This differs from custom NACLs, which automatically start by denying all traffic.


A custom Network ACL starts with a strict 'Default Deny' posture, blocking all inbound and outbound traffic. We must manually create rules (such as Rule 100 for All Traffic 0.0.0.0/0) to define what is explicitly permitted.


![Image](http://nextwork.ai/authentic_red_gentle_walrus/uploads/aws-networks-security_4faeb056)

---

## Tracking VPC Resources

Using the AWS CLI, I programmatically deployed three key resources in my secondary region: an Amazon VPC, a public subnet, and an Internet Gateway, creating a multi-region network baseline.

EC2 Global View provides a unified dashboard to monitor resources across all AWS regions. You can find and track VPCs, subnets, security groups, Internet Gateways, EC2 instances, volumes, and network interfaces globally.

I would use EC2 Global View again when auditing resources across multiple regions to prevent cost leaks from orphaned VPCs, subnets, or instances. It is highly valuable for fast disaster recovery planning and security compliance reviews.


![Image](http://nextwork.ai/authentic_red_gentle_walrus/uploads/aws-networks-security_b03ea6162)

---

---
