### What is Route53?

Route53 is Amazon Web Services' answer to all things DNS, within the Route53 service you are able to purchase and managed both domains and DNS records attached to them domains. Some of the most common DNS record types are as follows:
* A record - Address record, this simply points a DNS name (example.com) at an IPv4 address
* AAAA record - Same definition as above, but are used within the IPv6 address space
* CNAME - Canonical Name records, these are used to match a DNS record (example.com) to another DNS name (www.example.com) record so they are pointed at the same end location.
* MX record - Mail Exchanges record, is used when specifying a domain name at Mail servers.
* SOA records - Start of Authority records, stores "meta data" about your domain name, including primate Name Server, email of the domain adminstrator (GDPR?)
* NS records - Name Server records, if the domain you are looking for is not cached anywhere when attempting to resolve, the NS specifies where you request should look in order to find information about the domain name.

Typically, all host zones within Route53 are created with SOA and NS records.

#### Routing policies available on AWS

* Simple routing
* Weighted Routing
* Latency-based routing
* Failover routing
* Geolocation routing
* Multi-value answer routing

#### Simple routing policies

* Simple in name, a user will hit "gregsharpe.co.uk" to be returned to a AWS service (via an alias) or IP address.
* Can specify more than one address but route53 will randomly choose one

#### Weighted Routing

* Has the ability to set the amount of traffic across two records 50% to IP_A and 50% of traffic going to IP_B

#### Latency Based routing

* Latency based routing allows you to route your traffic based on the lowest network latency for your end user. To use latency-based routing, you create a latency resource record set for the Amazon EC2 (or ELB) resource in each region that hosts your site. When a request is made to route53, route53 selects the latency resource with the lowest latency for your end user.

#### Failover routing

* Failover routing policies are used when you want to create an active/passive set up. For example, you may want your primary site to be in EU-WEST-2 and your secondary DR site in AP-SOUTHEAST-2.
* Route53 will monitor the health of your primary site using a health check (maybe from the LB for example)

* Have to create HealthCheck, this can be used to check if the endpoint is live.
* May take some time to re-route to the "passive" setup

#### Geolocation routing

* Gelocation routing lets you choose where your traffic will be sent based on the geographic location of your users. For example, you may want your european users to hit a fleet of EC2 servers running in Europe which will have a certain language pack running on them.

#### Multi-value Answer routing

* Each endpoint needs it's own health check
* The A record will have multiple IP address associated with it, if the health check shows the endpoint is not active. It will take that IP address out of the multi-value array
