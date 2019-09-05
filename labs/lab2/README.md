# Lab 2 - AWS Elastic Load Balancer
In this Lab, you will be creating a small three instance auto-scaled cluster using the Linux AMI from your previous Lab.  You will then configure an Elastic Load Balancer and create load on instances to observe Cloud Elasticity at work.

#### Key Steps Are:
1. Create or Select a Launch Configuration
2. Create an Auto Scaling Group
3. Using a Load Balancer With an Auto Scaling Group

## Lab Notes
- Make sure to copy the index.html before you create the linux cmpe281 image

## My Notes
Your load balancer acts as a single point of contact for all incoming web traffic to your Auto Scaling group. When an instance is added to your Auto Scaling group, it needs to register with the load balancer or no traffic is routed to it. When an instance is removed from your Auto Scaling group, it must deregister from the load balancer or traffic continues to be routed to it.

### Elastic Load Balancing Types
Elastic Load Balancing provides three types of load balancers that can be used with your Auto Scaling group: Classic Load Balancers, Application Load Balancers, and Network Load Balancers. With Classic Load Balancers, instances are registered with the load balancer. With Application Load Balancers and Network Load Balancers, instances are registered as targets with a target group.

**Classic Load Balancer**
  Routes and load balances either at the transport layer (TCP/SSL), or at the application layer (HTTP/HTTPS). A Classic Load Balancer supports either EC2-Classic or a VPC.

**Application Load Balancer**
  Routes and load balances at the application layer (HTTP/HTTPS), and supports path-based routing. An Application Load Balancer can route requests to ports on one or more registered targets, such as EC2 instances, in your virtual private cloud (VPC).

  Note

  The Application Load Balancer target groups must have a target type of instance. For more information, see Target Type in the User Guide for Application Load Balancers.
