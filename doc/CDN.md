# Content Delivery Networks (CloudFront) 101

## What is a CDN?

A content delivery network (CDN) is a system of distributed servers (network) that deliver webpages and other web content to a user based on their geographical location, the origin of the webpage and the content delivery server.

## CloudFront Key terms

* Edge location - The is the location where the content will be cached.
* Origin - This is the origin of all the files that the CDN will distribute. This can be S3, EC2 and Elastic Load Balancer or Route 53.
* Distribution - The is the name given the CDN which of a collection of Edge locations.
* Web distribution - Typically used for websites
* RTMP - Used for Media streaming

# What is CloudFront?

Amazon CloudFront can be used to deliver your entire website, including dynamic, static, streaming, and interactive content using a global network of edge locations. Requests for your content are automatically routed to the nearest edge location, so content is delivered with the best performance possible. CloudFront is optimised to work with other AWS, like S3, EC2, ELBs and Route53. But also works seamlessly with any non-AWS origin server, which stores the original, definitive versions of your files.
