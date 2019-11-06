---
layout: post
title: WebTerminology
date: 2019-01-30 03:15:00
categories: WebApplication
desc: Web Terminology
---

**DNS – Domain Name System**  
It is the basic concept that one should know before entering into web related stuff.  
It is something like alphbet or number...choose which subject you love.(bad joke) i know :grimacing:   

>Domain–github.io  
>Subdomain–`iamprakashkumar`.github.io
`iamprakashkumar` is the subdomain of `github.io`  
`www`.github.io – Here `www` is a subdomain of github  
github.io will contain some content and www.github.io will contain some other content

**URL vs URI**  
```console
URL – It defines how to fetch a resource from specific place(http,ftp....)  
URI – Standard for identifying documents (URN, URL are all types of URI)  
URN – Identify resource by specific name (urn:isbn:0451450523)  
```

**FQDN** – Fully Qualified Domain Name  
A proper FQDN ends with a dot at the end.(**github.com`.`**)  
trailing dot is required to conform to ICANN standards.  

**Name Server** – These are present inside the DNS. It only do most of  the work  
 

**Records** – Records are present inside the zone file.  
It will do a single mapping.  
1.It mapps domain name to IP address.  
2.It defines Name server  
3.It defines mail server of the domain.  


**Zone file** – It maps domain name and ip address(dns translates domain to ip)  
It resides inside the Name server. It defines what resources are available under a specific domain.  
The more zone files that a name server has, the more requests it will be able to answer authoritatively.(Recursive Nameserver)   
The zone's $ORIGIN is a parameter equal to the zone's highest level of authority by default.  
Zone file will contain many record types, some of them are liste below:  

**SOA**
The Start of Authority, or SOA, record is a mandatory record in all zone files. It must be the first real record in a file (although $ORIGIN or $TTL specifications may appear above).

![SOA Record](https://user-images.githubusercontent.com/17383454/51947072-93a83e00-2449-11e9-8478-a1072f93bb90.png)

github.io. - describes root of the zone  
862  
IN - represents Internet  
SOA - Indicator that this is the start of authority  
ns-1622.awsdns-10.co.uk. - Master Primary name server  
awsdns-hostmaster.amazon.com. - Email address of the admin for this zone(@ is replaced with dot)  
1 - Serial number of the zone file.  
7200 - Refresh interval of the zone.  
900 - Retry interval of the zone.  
1209600 - Expiry period  
86400 - amount of time that the name server will cache a name error if it cannot find the requested name in this file.

[](https://www.digitalocean.com/community/tutorials/an-introduction-to-dns-terminology-components-and-concepts)





















