<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Build a Virtual Private Cloud

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-vpc)

**Author:** mgardner  
**Email:** cliches_tinfoil.4r@icloud.com

---

## Build a Virtual Private Cloud (VPC)

![Image](http://learn.nextwork.org/lively_olive_quiet_oriental_melon/uploads/aws-networks-vpc_2facf927)

---

## Introducing Today's Project!

In this project, I will demonstrate how to create an amazon VPC (virtual private cloud), how to create a subnet, and how to create an internet gateway.  I'm doing this project to learn strengthen my knowledge about networking within AWS.

### What is Amazon VPC?

Amazon VPC (Virtual Private Cloud) is a service from Amazon Web Services that lets you create a private, isolated network inside the cloud where you can launch and manage resources like servers, and it is useful because it gives you full control over your network, improves security by isolating your resources, and allows you to scale and manage your infrastructure easily without needing physical hardware.


In today's project, I used Amazon VPC to build an isolated, secure network from scratch by defining a custom CIDR block and creating a public subnet, which I linked to an Internet Gateway via custom Route Tables to allow controlled internet access for my EC2 instances.

### Personal reflection

This project took me about an hour across the course of 2 days.

One thing I didn't expect in this project was the number of dependencies a VPC can have especially when it comes to deleting resources. The vpc cannot be deleted until those dependencies are removed first.  This highlights the interconnected nature of AWS networking and the importance of a thorough clean up process.

---

## Virtual Private Clouds (VPCs)

### What I did in this step

In this step, I will create the vpc (virtual private cloud). 

### How VPCs work

VPCs are your own private "city" inside of an AWS region.  It allows you to control and manage what goes on inside (resources) and who's able to connect to it.  

### Why there is a default VPC in AWS accounts

There was already a default VPC in my account ever since my AWS account was created. This is because there are certain resources in AWS that require a VPC to launch such as EC2 instances and without the default VPC, you would need to learn how to set up that VPC first before ever getting started.

![Image](http://learn.nextwork.org/lively_olive_quiet_oriental_melon/uploads/aws-networks-vpc_2facf927)

### Defining IPv4 CIDR blocks

To set up my VPC, I had to define an IPv4 CIDR block, which is internet protocol version 4, classless inter-domain routing block.  IPv4 is the most common way to write an ip address and a CIDR block is a way to assign a whole block of ip addresses kind like creating a zone in a city.

---

## Subnets

### What I did in this step

In this step, I will launch a subnet inside of the vpc.  This subnet will allow for the division or subdivision of the large space (ip network) to allow for more efficient planning of where resources will live and operate.

### Creating and configuring subnets

Subnets are used to group resources with similar access rules and restrictions.  There are already subnets existing in my account, one for every availability zone within that chosen region.

### Public vs private subnets

The difference between public and private subnets is one is connected to or has access to the internet while the other is not.   For a subnet to be considered public, it has to have a connection to an internet gateway.

![Image](http://learn.nextwork.org/lively_olive_quiet_oriental_melon/uploads/aws-networks-vpc_157c4219)

### Auto-assigning public IPv4 addresses

Once I created my subnet, I enabled auto-assign public IPv4 address. This setting makes sure any EC2 instance launched in that subnet will instantly get a public IP address, so that you won't have to create one manually.

---

## Internet gateways

### What I did in this step

In this step, I will create an internet gateway because in order for the vpc to connect to the internet it needs a "bridge" and this internet gateway is that bridge connecting the private (vpc) with the public (internet).

### Setting up internet gateways

Internet gateways are key to making applications available on the internet. By attaching an internet gateway, your instances can access the internet and be accessible to external users.

Attaching an internet gateway to a VPC allows resources in the VPC to access the internet. Without this step, even EC2 instances with public IP addresses would not be reachable, and any applications hosted on them would be inaccessible.


![Image](http://learn.nextwork.org/lively_olive_quiet_oriental_melon/uploads/aws-networks-vpc_4ae90410)

---

## Using the AWS CLI

### What I'm doing in this extension

In this project extension, I will use AWS CloudShell and the AWS CLI to create and configure VPC resources, including a VPC, subnet, and internet gateway, and evaluate whether this method is faster and more efficient than other approaches.

### Exploring CloudShell and CLI

VPC resources could also be created with CloudShell, which is shell in the AWS console that allows you to run code  CLI is command line interface is software that lets you to create, delete, and update resources in AWS with commands instead of clicking through the console.

### Debugging my setup

To set up a VPC or a subnet, you can use the command,  aws ec2 create- Make sure to avoid errors by including --cidr-block when creating the subnet as it will not know which ip addresses to allocate for it without this.

![Image](http://learn.nextwork.org/lively_olive_quiet_oriental_melon/uploads/aws-networks-vpc_9b2465411)

### Comparing CloudShell vs AWS Console

Compared to using the AWS Console, an advantage of using commands is speed.  An advantage of using the Console is efficiency. Overall, I preferred using the command line just based on pure control and efficiency.

---

---
