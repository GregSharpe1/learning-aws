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
