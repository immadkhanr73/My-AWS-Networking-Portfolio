<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Build a Virtual Private Cloud

**Project Link:** [View Project](http://nextwork.ai/projects/aws-networks-vpc)

**Author:** Immad Khan  
**Email:** immadkhanr73@gmail.com

---

## Build a Virtual Private Cloud (VPC)

![Image](http://nextwork.ai/authentic_red_gentle_walrus/uploads/aws-networks-vpc_2facf927)

---

## Introducing Today's Project!

I am here to build a custom Amazon VPC from scratch to understand the foundations of cloud networking on AWS. I will configure private network spaces using custom CIDR blocks, segment a public subnet, and attach an internet gateway to enable secure communication with the public internet. I am completing this project to gain hands-on experience with core AWS networking components.

### What is Amazon VPC?

### Personal reflection

---

## Virtual Private Clouds (VPCs)

### What I did in this step

I will access the VPC console in AWS to create a custom Amazon VPC with a defined CIDR block. I am doing this because a custom VPC is the absolute foundation of my cloud infrastructure, carving out a private, isolated network segment where I can safely deploy and control my cloud resources.

### How VPCs work

An Amazon VPC (Virtual Private Cloud) is a logically isolated, software-defined network provisioned within the AWS cloud infrastructure. It provides complete administrative control over the virtual networking environment, enabling the customization of private IP address ranges, the segmentation of public and private subnets, and the configuration of custom route tables and network gateways.
This helps organizations by establishing a secure boundary for cloud resources, implementing strict network-level isolation for sensitive workloads (such as databases), and providing the infrastructure framework needed to deploy compliant, scalable, and resilient application architectures.

### Why there is a default VPC in AWS accounts

AWS provisions a default VPC in every region so that users can immediately deploy and connect network-dependent resources (like EC2) without needing to configure a custom network first, accelerating early deployment.

![Image](http://nextwork.ai/authentic_red_gentle_walrus/uploads/aws-networks-vpc_2facf927)

### Defining IPv4 CIDR blocks

An IPv4 CIDR block is a range of IP addresses allocated to a network. The slash prefix (like /16) dictates how many bits are fixed, defining the overall size of the private network and the IP range available for subnets.

---

## Subnets

### What I did in this step

In this step, I will segment my custom VPC by creating a public subnet and enabling auto-assign public IP settings. I am doing this to define a dedicated network boundary for resources that require direct internet connectivity.

### Creating and configuring subnets

A subnet (sub-network) is a logically designated partition of an Amazon VPC IP address space. By dividing a broad network into smaller, isolated subnets, engineers can deploy resources in a structured environment tailored to specific security, compliance, and connectivity requirements.

### Public vs private subnets

The difference between public and private subnets is internet access. For a subnet to be considered public, it has to have a route in its route table pointing to an internet gateway to allow external traffic flow.

![Image](http://nextwork.ai/authentic_red_gentle_walrus/uploads/aws-networks-vpc_157c4219)

### Auto-assigning public IPv4 addresses

When you enable auto-assign public IPv4 address for a subnet, any EC2 instance launched in that subnet will instantly get a public IP address so you won't have to create one manually - a huge time saver!

---

## Internet gateways

### What I did in this step

In this step, I will create an Internet Gateway and attach it to my custom VPC. I am doing this to establish a bidirectional communication path between my isolated network resources and the public internet.

### Setting up internet gateways

An internet gateway connects your city (VPC) and the outside world (internet).
Internet gateways are key to making applications available on the internet. By attaching an internet gateway, your instances can access the internet and be accessible to external users.

Attaching an internet gateway means resources in your VPC can now access the internet. The EC2 instances with public IP addresses also become accessible to users, so your applications hosted on those servers become public too.

![Image](http://nextwork.ai/authentic_red_gentle_walrus/uploads/aws-networks-vpc_4ae90410)

---

## Using the AWS CLI

### What I'm doing in this extension

I am using the AWS CLI (Command Line Interface) within AWS CloudShell to programmatically provision my custom cloud network. By executing commands to launch my VPC, public subnet, and internet gateway, I am transitioning from manual console configuration to command-line automation. This demonstrates foundational skills in scripting and automated resource management, which are core prerequisites for Infrastructure as Code (IaC) workflows.

### Exploring CloudShell and CLI

AWS CloudShell:

A secure, pre-configured, browser-based terminal environment provisioned by AWS. Using CloudShell allowed me to run commands instantly on a temporary Amazon Linux compute instance without needing to manage local environment variables, credentials, or tool installations on my physical machine.

AWS CLI (Command Line Interface):

A unified, command-line tool designed to manage AWS services programmatically. By making direct API calls through the CLI shell, I executed the precise sequence of commands needed to provision, tag, and configure my resources.

### Debugging my setup

I ran into an error because the template command contained placeholders (VPC-ID and ADD-CIDR-BLOCK-HERE) rather than my actual AWS resources. The AWS CLI requires valid, existing IDs and properly formatted CIDR blocks to execute.

![Image](http://nextwork.ai/authentic_red_gentle_walrus/uploads/aws-networks-vpc_9b2465411)

### Comparing CloudShell vs AWS Console

Speed & Efficiency: 

Manual configuration in the AWS Console requires navigating multiple UI wizard screens and tabs. The AWS CLI bypasses the interface entirely, executing immediate programmatic resource deployment via direct API calls.

Reliability & Drift: 

Manual operations (ClickOps) are highly prone to human input errors, naming mismatches, and missed checkboxes. Command-line execution ensures identical, repeatable deployments every time, eliminating configuration drift.

Modern Workflow: 

Deploying network resources programmatically through AWS CloudShell leverages secure, temporary sessions with implicit credential inheritance. This serves as the direct conceptual bridge to advanced Infrastructure as Code (IaC) automation tools.


---

---
