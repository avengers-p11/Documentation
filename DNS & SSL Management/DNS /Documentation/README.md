# DNS Documentation

  | Author        | Created on | Version | Last updated by | Last edited on |
  |-------------|---------|-------------|-------------|---------|
  | Raman Tripathi | 20-12-24 | version 1 | Raman Tripathi | 26-11-24 |
  
  ## Table of Content
- [Introduction](#introduction)
- [Why DNS ?](#why-dns)
- [What is DNS ?](#what-is-dns)
- [Types of records](#types-of-records)
- [How it is work ?](#how-it-is-work)
- [How to get domain ?](#how-to-get-domain)
- [Different DNS provider](#different-dns-provider)
- [Comparision between DNS providers](#comparision-between-dns-providers)
- [Contact information](#contact-information)
- [References](#references)



## Introduction
> The Domain Name System (DNS) is like the internet’s phone book. It helps you find websites by translating easy-to-remember names (like www.example.com) into the numerical IP addresses (like 192.0.2.1) that computers use to locate each other on the internet. Without DNS, you would have to remember long strings of numbers to visit your favorite websites. 

## Why DNS ?

> Without DNS, we’d have to remember long numbers (IP addresses) for every website, which would be hard and confusing. DNS makes the internet easy to use by letting us type website names instead of numbers.

## What is DNS ? 
> The Domain Name System (DNS) works like the internet's phonebook. When you type a web address like "google.com" or "nytimes.com" into a browser, DNS helps find the right IP address for that website. The browser then uses this IP address to connect to the website's server and load the page. DNS servers are the computers that respond to these requests, helping browsers find the right websites quickly.

## Types of records

 - **A (Address) Record:** Maps a domain name to an IPv4 address.

 - **AAAA (IPv6 Address) Record:** Maps a domain name to an IPv6 address

 - **CNAME (Canonical Name) Record:** Maps a domain name (alias) to another domain name.

 - **MX (Mail Exchange) Record:** Directs email to mail servers for a domain.

 - **TXT (Text) Record:** Provides arbitrary text data for a domain. 

 - **SOA (Start of Authority) Record:** Contains administrative information about the domain.


## How it is work ? 
![image](https://github.com/user-attachments/assets/be244f6e-f45c-4f5c-8697-bbaca2a5944b)

### DNS Recursor (or Resolver): 
> This is like a "helper" that looks up the website address for you. When you want to visit a website, it asks other servers to find the correct IP address that leads to the website.
### Root Nameservers: 
> These are the starting points of the DNS system. They help by pointing the resolver to the right type of server based on the website’s domain (like ".com", ".org", etc.).
### TLD Nameservers :
> These servers manage the domain extensions like ".com", ".org", and so on. They tell the resolver where to find the next server that knows the website’s exact IP address.
### Authoritative Nameservers:
> These are the "final answer" servers. They have the exact IP address for the website you're looking for. There are two types:

    Master (Primary): The main server that holds the original IP records.
    Slave (Secondary): A backup server that has a copy of the information in case the master server fails.

## How to get domain ?

>### Choose any domain provider right now i am using Hostinger.com then search any domain name that you want right now i am using otmservice.in.
![image](https://github.com/user-attachments/assets/b8272fab-de72-4d06-b61a-aa93e577eb21)

> ### After that you can see the price of that domain name then click on that then do payments .
![image](https://github.com/user-attachments/assets/65c4a860-8427-48ef-b934-308f3d09bb37)

> ### After doing the payments come to the home page of HOstinger click on username then click on my Product in that you can see your domain name with all the details . 
![image](https://github.com/user-attachments/assets/3099f70e-5843-4315-bb3f-a5a072af985f)


## Different DNS provider 


|    DNS providers          |     Description                     |
|:-----------------:|:-------------------------------------:|
| Cloudflare | Fast, secure, and free options.
| Amazon Route 53 | Good for complex setups, like apps on Amazon Web Services.
| Google Public DNS | Very fast, free, and trusted.
| GoDaddy | Popular for domain registration and DNS management, with additional services like website hosting and email.

## Comparision between DNS providers

|    DNS providers | Key Features| Speed | Security | Pricing   |
|-----------------|-------------------|------------------|---------|---------|
| Cloudflare|Fast performance and Free DNS | High | DDoS protection |Free and Premium plans available for advanced features.
| Google Public DNS | Fast,low-latency DNS | High | Basic (no advanced security features) | Free
|Amazon Route 53 | Scalable, integrates with AWS and Advanced routing policies |High| DDoS protection | Pay-as-you-go (pricing based on queries and services used) 
| GoDaddy | Domain registration | Medium | DDoS protection | Paid (pricing based on domain and hosting plan)


## Contact Information
| Name| Email Address      |
|-----|--------------------------|
| Raman Tripathi | raman.tripathi.snaatak@mygurukulam.co |

| GitHub | URL |
|----------|---------|
|  Raman-tripathi07  |  https://github.com/Raman-tripathi07 |

## References
|Description  |   Link |
|:------------------:|:-------------------:|
| Introducing of DNS | https://aws.amazon.com/route53/what-is-dns/
| Working of DNS | https://youtu.be/vhfRArT11jc?si=3cYjikGF-gLjLbrf
| DNS provider | https://www.godaddy.com/en-in
