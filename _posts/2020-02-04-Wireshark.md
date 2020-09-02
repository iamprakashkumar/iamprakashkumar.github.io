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

**Data packets capturing**  

To start capturing  
• Select a network interface  
• Click on the blue shark fin button / press Ctrl + E  

To stop capturing st capturing  
• Click on the red stop button / press Ctrl + E  

Top frame:  
Number | Time | Source | Destination | Protocol | Length | Info  

Middle frame examples  
1. Frame
2. Linux cooked capture
3. Internet protocol version, source, destination
4. Transmission control protocol, src port, dst port, seq, len  

Bottom frame:  
Data  

**Wireshark Filters**  

There are 2 ways to filter:  
• Build a filter via the fancy GUI (Expression button)  
• Type a filter into the “Apply a display filter” entry field (below the toolbar)  
   https://wiki.wireshark.org/DisplayFilters


**Wireshark Filters Relations**  

**Most common Wireshark filters**

tcp.port eq 80 
tcp.srcport==443  

Filter for HTTP and HTTPS traffic:  
tcp.port==443 or tcp.port==80  
ssl or http   

tcp.port in {80 443 8080}    
tcp.port == 80 || tcp.port == 443 || tcp.port == 8080  

Filter for a protocol:  
tcp  
udp  
dns  

IP addresses:  
ip.addr == 10.43.54.65  
! ( ip.addr == 10.43.54.65 )  

Examples for web traffic:  
http.request.uri == https://www.wireshark.org/  
http.host matches "acme\.(org|com|net)"  
http.response.code == 200  
http.request.method == "GET“  
tcp contains "admin"  

Filter for http traffic with specific addresses and frame time and not 200 response (e.g. you want to see 301 Moved permanently and 500 Server error packets):  

'''http && ( (ip.dst == 192.168.178.27 ) || (ip.dst == 193.70.91.56 ) ) && frame.time > "2019-01-24 00:01:00.0000" && frame.time < "2019-01-25 15:01:53.0000" && http.response.code != 200'''  

**SSL ManInTheMiddle with Wireshark**  

To test the decryption of SSL traffic with Wireshark:  
• Create private keys of the server and the client  
• Start a server which uses the certificate with the key and send some test packets  
• Configure Wireshark  

**Create certificates**  

Create a server certificate  
'''openssl req -new -x509 -out server.crt -nodes -keyout server.pem -subj /CN=localhost'''  

Create a client certificate  
'''openssl req -new -x509 -nodes -out client.crt -keyout client.key -subj /CN=Moi/O=Foo/C=NL'''  

**Start a server**  

Start a server at localhost:4443  
'''openssl s_server -cipher AES256-SHA -accept 4443 -www -CAfile client.crt -verify 1 -key server.pem -cert server.crt '''  

**Send a request with python(3) and stop the capture**  


'''import urllib.request  
import ssl  
context = ssl._create_unverified_context() with urllib.request.urlopen("https://localhost:4443/",context=context) as url:  
 s = url.read()  
 print(s)'''    
 
 
 





























































