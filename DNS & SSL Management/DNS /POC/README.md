
## Proof-of-Concept (POC) of Implementation of DNS 


## Table of Contents

- [How you can get DNS ?](#how-you-can-get-dns)
- [What is Hosted zone](#what-is-hosted-zone)
- [Routing policy](#routing-policy)
- [How to setup DNS for application ?](#how-to-setup-dns-for-application)
- [Conclusion](#conclusion)
- [Contact information](#contact-information)
- [References](#references)


## How you can get DNS

> ## In this POC i used GoDaddy as DNS provider.

>Choose any domain provider right now i am using GoDaddy.com then search any domain name that you want right now i am using TechWithpritam.click.

![Screenshot from 2024-11-13 22-48-30](https://github.com/user-attachments/assets/b2d2c3c5-2ef5-4afe-9f5e-0c6b5d79e6ab)

>After that you can see the price of that domain name then click on that then do payments .

![Screenshot from 2024-11-13 22-48-49](https://github.com/user-attachments/assets/a8f4c2b6-1949-47c1-bba1-8f59e7174d78)
![Screenshot from 2024-11-13 22-49-30](https://github.com/user-attachments/assets/cf527e62-2707-4b3f-8b7f-0ee0dd636c5f)


>After doing the payments come to the home page of GoDaddy click on username then click on my Product  in that you can see your domain name with all the details . 

![Screenshot from 2024-11-13 23-53-13](https://github.com/user-attachments/assets/b7fd8f4d-ad93-4bf6-bce2-efe4056a1cd2)

## What is Hosted zone
>A hosted zone in AWS Route 53 is a container that holds information about how you want to route traffic for a specific domain or a subdomain.
There are two types of hosted zones in Route 53:
-  **Public Hosted Zone:**
Used for domains accessible over the internet.
- **Private Hosted Zone:**
 Used for internal services in your AWS environment that aren't publicly accessible.

## Routing policy
>AWS Route 53, routing policies determine how DNS queries are handled and how traffic is directed to resources.
- **Simple Routing Policy:** Used for a single resource (e.g., a single web server or application).

- **Failover Routing Policy:**  It creates a primary and a secondary (backup) resource.

- **Geolocation Routing Policy:**  Redirect traffic based on the geographic location of the query.


- **Geoproximity Routing Policy:** To route traffic based on geographic location and proximity, with optional bias to prefer certain resources.

- **Latency Routing Policy:** To improve performance by directing users to the resource with the lowest latency.

- **Multivalue Answer Routing Policy:** For simple load balancing with DNS and health checks.

- **Weighted Routing Policy:** To distribute traffic among multiple resources proportionally based on weights.



## How to setup DNS for application


>Create ALB and attach target group to it then go to the  AWS ROUTE 53 service.

![Screenshot from 2024-11-14 17-36-45](https://github.com/user-attachments/assets/69669595-9dbd-4e6d-9581-575ef1074d4e)
![Screenshot from 2024-11-14 17-34-26](https://github.com/user-attachments/assets/f92401d9-ccea-43db-af12-e99485347857)

>Then click on create hosted zone in this poc i am creating public hosted zone put domain name and then create hosted zone.

![Screenshot from 2024-11-14 17-34-40](https://github.com/user-attachments/assets/27c7abdd-1d46-41af-942c-728510d0cbff)
![Screenshot from 2024-11-14 17-35-12](https://github.com/user-attachments/assets/b339c5bd-f81d-4354-a745-81330c119a4d)
![Screenshot from 2024-11-14 17-35-22](https://github.com/user-attachments/assets/2f44b337-9830-4fee-9e81-9005649be956)

> Copy the ns record go to the DNS provider (i.e,GoDaddy) change the ns record (put ns record without dot (.).)

![Screenshot from 2024-11-14 17-36-03](https://github.com/user-attachments/assets/ca91c0a2-1d69-47ca-ba17-b40e194284a0)

![Screenshot from 2024-11-14 17-36-20](https://github.com/user-attachments/assets/46c4d615-6212-4fe1-8f47-9d907f399d5d)

>Then go to AWS console search route 53 create A name record right now we are using ALB for that we need to create alias  then choose load balancer , select region , DNS of ALB and then create A name record and make sure give TTL . TTL means route 53 determines how long the DNS record is cached by DNS resolvers and then select routing policy right  now i am using simple routing policy then  wait for 5-10 minutes after that hit your domain name on any browser then you will be access your website.

![Screenshot from 2024-11-14 17-37-02](https://github.com/user-attachments/assets/3533791a-a905-44c9-9a69-b22f34f9a634)
![Screenshot from 2024-11-14 17-37-26](https://github.com/user-attachments/assets/65c60872-8583-4e9f-b445-95e258befd9f)
![Screenshot from 2024-11-14 17-37-39](https://github.com/user-attachments/assets/418b0f1a-b875-4c3c-8346-68f7182202e1)


## Conclusion
> This POC demonstrates the process of acquiring a domain and setting up DNS configurations using GoDaddy as the domain provider and AWS Route 53 for DNS management. It highlights the key steps, including registering a domain, configuring the NS (Name Server) records, creating a hosted zone in AWS, and linking the domain with an application using an Application Load Balancer (ALB).



## Contact information



## References

|Description  |   Link |
|:------------------:|:-------------------:|
| Introduction of DNS | https://aws.amazon.com/route53/what-is-dns/
|How to get DNS and setuping to application  | https://youtu.be/tXgOSt80Mtg?si=H-Z0w6xngox8pb63
| Documentation of DNS | https://github.com/MyGurukulam-p11/Documentation/blob/Pritam_scrum56/DNS/DNS%20Documentation/%20README.md
