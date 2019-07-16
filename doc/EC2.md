# Elastic Compute Cloud

## EC2 101

Amazon EC2 is a web service that provides resizable compute capacity in the cloud (basically a VM in the cloud). Amazon EC2 reduces the time required to obtain and boot new server instances to minutes, allowing you to quickly scale capacity. Changed the economics of computing by allowing you to pay only for capacity that you actually use.

## EC2 options

* On demand - allows you to pay a fixed rate by the hour
* Reserved - provides you with a capacity reservation and offer a significant discount on the hourly charge for an instance. Based on a 1 year or 3 terms
* Spot - enables you to bid whatever price you want for instance capacity, providing for even greater savings if you applications have flexible start and end times
* Dedicated Hosts - Physical EC2 server dedicated for your use. Dedicated Hosts can help you reduce costs by allowing you to use your existing server-bound software licenses. (VMware)

## Use cases for each EC2 option

### On demand

* Perfect for users that want the low cost and flexibility of Amazon EC2 without any up-front payment or long-term commitment
* Applications with short term, spiky, or unpredictable workloads that cannot be interrupted.
* Applications being developed or tested on Amazon EC2 for the first time

### Reserved Instances

* Applications with steady state or predictable usage
* Applications the require reserved capacity
* Users can make up-front payments to reduce their total computing costs even further
  * Standard RIs
  * Convertible RIs - can change the EC2 type as long as you stay within the costings. Eg, needed more of a CPU intensive instance
  * Scheduled RIs - launching instances within a certain time frame (week days for testing, on a sale ends at month)

### Spot instances

* Applications that have flexible start and end times
* Applications that are only feasible at very low compute prices
* Users with an urgent need for large amounts of additional computing capacity

### Dedicated Hosts

* Useful for regulatory requirements that may not support multi-tenant virtualisation
* Great for licensing which does not support multi-tenancy or cloud deployments
* Can be purchased on-demand (hourly)
* Purchased as a reservation for up to 70% off the on-demand price⁄plex

### Different types of Virtualisation

* PV - Paravirtualisation
* HVM - Hardware virtual machine

### Different types of Volume types

* General purpose (GP2)
* Disk intensive (IO1) - Improved IOPS
* Magnetic

### Encrypting a root partition

By default, the root partition is NOT encrypted. To encrypt a root partition you must first create an instance then create an AMI from that instance, during the AMI creation process you then must select to encrypt the root volume.

### EC2 Security Groups Basics

What is a security group? A security group is like a virtual firewall. It's the first line of defense when protecting incoming and outbound traffic

* All inbound traffic is blocked by default
* All outbound traffic is Allowed by default
* Changes to security groups take effect immediately
* You can have any number of EC2 Instances within a security group
* You can have multiple security groups attached to EC2 instances
* Security groups are stateful
  * If you create an inbound rule allowing traffic in, that traffic is automatically allowed back out again.
* You cannot block specific IP addresses using Security Groups, instead use NACL
* You can specify allow rules, but not deny rules. You can allow an IP over SSH but can't deny that same IP

### EBS Volumes

Elastic Block Storage - think of it as a virtual hard disk in the cloud, that can run Operating systems

* EBS Volume has to be in the same availability zone as the instance
* With the 4 differnt types of EBS volume all can be modified on the fly APART from standard type
* Moving a volume to another availability zone
  * Create a snapshot
  * Then via the wizard you can create another volume based of the snapshot and moving it to another availability zone

### Loadbalancers in AWS

Three types of Loadbalancer within AWS

* Application Loadbalancer - best suited for load balancing of HTTP and HTTPS traffic. Operate at layer 7 and are application aware.
* Network load balancer - Best suited for load balancing of TCP traffic where extreme performance is required. Operates at layer 4 and are capable of handling millions of requests per second, while maintaining ultra-low latencies.
* Classic Load balancer / elastic load balancer - Legacy load balancers, can balancer HTTTP/HTTPS traffic, can use layer 7 specific features and you can also load balancer layer 4. 

### Load balancer errors

* Classic Load Balancer - if your application (behind the LB) stops responding, the ELB will respond with a timeout error (504). Could be an issue with either the web server layer or the database layer.
* X-Forwarded-For Header - because there is a load balancer infront of the ec2 instance the instance has no idea where the original IP address is. With X-Forwarded-For header the source public IP address is passed through to the EC2 instance. ELB allows the EC2 instance to grab the public IP[

### Gathering EC2 metadata

* From inside of the EC2 instance, curl http://169.254.169.254/latest/meta-data/ 
* All metadata for that specific instance is within that endpoint

### Placement Groups

* Clustered placement group - group of instances within a SINGLE availability zone, placement groups are recommended for applications that need low network latency, high network throughput, or both. Only certain instances can be launched into a clustered Placement group. Defaulted to Cluster placement group within the exam.
* Spread placement group - For ensuring that instances are spread across different hardware within different availability zones.

#### Exam tips for placement groups

* A *clustered* placement group, cannot span multiple availability zones.
* A spread placement group can span across multiple regions/availability zones.
* The name you specify for a placement group must be unique within your AWS account
* Only certain types of instances can be launched in a placement group
* It is advised that the instances used within these groups are homogenous, meaning that they should be the same size and type.
* You can't merge placement groups.
* You can't merge an existing ec2 instance into a placement group, you have to create an AMI from the running image.

### EFS Lab

* What is EFS? Amazon Elastic File storage is a file storage service for AWS EC2 instances. EFS is an easy to use and provides a simple interface that allows you to create and configure file systems. EFS storage capacity is elastic, growing and shrinking automatically as you add and remove files, so your applications have storage when they need it.
* Supports the NFS version 4 protocol
* Charged $0.30 per gb used of storage (no pre-provisioning required)
* Can scale up to the petabytes
* Can support thousands of concurrent NFS connections
* Data is stored within multiple AZ's within a region
* Read after write consistency (like S3)
* Block based storage, not Object based storage

### Notes/Exam tips

* Termination protection is turned off by default
* EBS-backed instance default action is to be deleted when the instance is terminated
* Two types of underlying Hypervisor technologies used by EC2 are Xen and Nitro
