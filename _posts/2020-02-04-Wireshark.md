---
layout: post
title: Wireshark
date: 2020-02-04 23:33:00
desc: Handson wireshark
---
### Wireshark

Wireshark is a packet sniffer and analysis tool.  
It captures network traffic on the local network and stores that data for offline analysis.  
Wireshark captures network traffic from Ethernet, Bluetooth, Wireless (IEEE.802.11), Token Ring, Frame Relay connections, and more.   
These packets can be used for analysis on a real-time or offline basis.  
The user can use this information to generate statistics and graphs.   

Areas where wireshark is used  

Troubleshooting Network Connectivity  
> Visually understand packet loss  

Examination of Application Layer Sessions (even when encrypted by SSL/TLS see below)  
> 1. View full HTTP session, seeing all headers and data for both requests and responses  
> 2. View Telnet sessions, see passwords, commands entered and responses  
> 3. View SMTP or POP3 traffic, reading emails off the wire  

Extract files from HTTP sessions  
> Export objects from HTTP such as javascript, images, or even executables.  


Detect and Examination of Malware  
> 1. Detect anomalous behaviour that could indicate malware  
> 2. Search for unusual domains or IP address endpoints  
> 3. Filter out the "normal" and find the unusual  
> 4. Extract large DNS responses and other oddness which may indicate malware  


Working with wireshark  

Wireshart installation can be normally installed on ubuntu using the following command.  
![in](https://user-images.githubusercontent.com/17383454/73773070-779b5300-47a7-11ea-9245-b4ce83dcd280.png)  

![install 1](https://user-images.githubusercontent.com/17383454/73773123-9699e500-47a7-11ea-9733-6a3004dbef96.png)  

After doing this i faced a error while tried to capture the packets. It can be resolved by providing necessary access to wireshark to capture the packets.  

![Child error](https://user-images.githubusercontent.com/17383454/73773293-ed9fba00-47a7-11ea-9053-4a85b78b8632.png)   

![Chilld error solved](https://user-images.githubusercontent.com/17383454/73773330-fee8c680-47a7-11ea-9552-9a7348791da3.png)  

After that we need to launch the wireshark with the sudo privileage

```$ sudo wireshark ```

![Successful installation](https://user-images.githubusercontent.com/17383454/73774173-84b94180-47a9-11ea-8e36-360e0e7bf2e1.png)  



