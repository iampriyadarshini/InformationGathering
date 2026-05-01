# NAME : PRIYADARSHINI K
# REG NO : 212224100046
# InformationGathering
Information Gathering Techiques

# To perform information gathering techniques

# AIM:

To perform information gathering techniques using kali linux 

## STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:
Open terminal/browser and try execute necessary commands/use url to perform information gathering

## Pen Test Tools Categories:  

Following Categories of pen test tools are identified for information gathering:

Footprinting is a part of the reconnaissance process which is used for gathering possible information about a target computer system or network.
http://www.whois.com/whois website to get detailed information about a domain name information including its owner, its registrar, date of registration, expiry, name server, owner's contact information, etc.

## OUTPUT:
<img width="1037" height="1036" alt="image" src="https://github.com/user-attachments/assets/f68e3f37-bf6d-4625-8cdc-c6b9a61add3b" />

Domain Registration:
The domain uni-jena.de is an active academic domain used by the University of Jena. The last recorded update was on May 4, 2020.

Registrar:
The domain is managed under Germany’s official registry system by DENIC, which handles all .de domains.

Status:
The domain status is shown as “connect”, meaning the domain is active and properly configured for use.

Name Servers:
The domain uses multiple name servers such as dns-3.dfn.de and dns-extern.uni-jena.de, which help in directing internet traffic to the correct servers.

Contact Details:
Detailed registrant information (like country and owner details) is not publicly displayed due to strict privacy policies followed by DENIC. Only limited technical information is available.


## Finding IP address:
ping command is available on Windows as well as on Linux OS. Following is the example to find out the IP address of facebook.com.

## OUTPUT
<img width="637" height="458" alt="image" src="https://github.com/user-attachments/assets/bf6ec815-5f50-4d78-b40b-0d8d27bf0396" />

The command ping -4 uni-jena.de is used to test the network connectivity to the domain using IPv4. The domain resolves to the IP address 141.35.105.79, and the system successfully sends and receives packets from the server. Each response shows 64 bytes of data along with details such as sequence number (icmp_seq) and TTL value (41), indicating normal packet transmission. The response times vary between approximately 198 ms and 490 ms, showing the delay between the system and the server. The ping statistics at the end indicate that 9 packets were transmitted and all 9 were received with 0% packet loss. This confirms that the connection to the University of Jena server is active, stable, and functioning correctly.


## Finding Hosting Company
get further detail by using ip2location.com website.

## OUTPUT
<img width="1916" height="1142" alt="image" src="https://github.com/user-attachments/assets/3e36722c-04cc-4979-aa5e-355997c69919" />

This IP lookup result shows that the IP address 141.35.104.106 is located in Germany, specifically in Berlin. It is associated with Friedrich Schiller University Jena. The data confirms that the server is hosted within Germany. The IP is not using any proxy, ensuring accurate location details. It is linked to the domain uni-jena.de.


## History of the website:

## OUTPUT
https://web.archive.org/

<img width="1918" height="1140" alt="Screenshot 2026-05-01 200241" src="https://github.com/user-attachments/assets/6b19edb0-dc81-464b-8ec7-077f3d52ab75" />

the Wayback Machine from the Internet Archive, which is used to view historical versions of websites. The domain uni-jena.de (University of Jena) has been archived 9,059 times between October 8, 1997, and April 24, 2026. The timeline graph at the top displays how frequently the website was saved each year, with more activity in recent years. Below that, the calendar view for 2026 highlights specific dates when snapshots of the website were taken, shown as colored circles. Larger circles indicate more captures on that day. This tool helps track how a website has changed over time and is useful for analysis, research, and digital forensics.


# Webserver Fingerprinting:

## Netcat:
sudo nc example.com 80
GET / HTTP/1.1
Host: example.com
<img width="478" height="337" alt="image" src="https://github.com/user-attachments/assets/d9618536-7e0f-4c1a-b25d-8eece93555e8" />

This image shows a successful TCP connection to the web server of University of Jena using the Netcat (nc) command on port 80. After establishing the connection, a manual HTTP request (GET / HTTP/1.1 with the host name) was sent. The server responded with an HTTP status message “301 Moved Permanently”, which means the requested webpage has been permanently redirected to another URL. The response headers indicate that the server is running nginx and provide details such as content type, date, and connection status. The Location field shows that the website has been redirected to https://www.uni-jena.de/, meaning the site forces users to use a secure HTTPS connection. The HTML content below confirms the redirection message, demonstrating how web servers handle requests and redirects at a low level.


## nmap:

## OUTPUT
<img width="627" height="227" alt="image" src="https://github.com/user-attachments/assets/abd32723-1f6d-4000-b497-3f77f4250996" />

This image shows the result of an Nmap scan performed on the domain of University of Jena (uni-jena.de). The scan reveals that the host is active with a low latency of 0.11 seconds, indicating a responsive server. The domain resolves to the IP address 141.35.104.79, and both IPv4 and IPv6 addresses are detected. Out of 1000 scanned ports, 998 ports are closed or filtered, meaning they do not respond to requests, which is a good security practice. However, two ports are open: port 80 (HTTP) and port 443 (HTTPS), which are standard ports used for web services. The presence of these open ports confirms that the server is running a website and allows both regular and secure web communication. Overall, the scan demonstrates that the server is properly configured with minimal exposed services, enhancing its security.


## Whatweb

## OUTPUT
<img width="625" height="232" alt="image" src="https://github.com/user-attachments/assets/47bfed2c-2a62-4cde-a776-614934918ac5" />

This image shows the result of a WhatWeb scan performed on the website of University of Jena (uni-jena.de). The scan identifies the technologies and configuration used by the web server. Initially, the HTTP version of the site returns a “301 Moved Permanently” response, indicating that the website automatically redirects users to the secure HTTPS version (https://www.uni-jena.de/). The server is detected as nginx, and the site is confirmed to be hosted in Germany (DE). The final HTTPS page returns a “200 OK” status, meaning the website is successfully accessible. Additional details show that the site uses HTML5, includes metadata such as Open Graph protocol for web previews, and implements security headers like Strict-Transport-Security (HSTS). The page title identifies it as Friedrich Schiller University Jena. Overall, this scan demonstrates that the website is properly configured with secure redirection and modern web technologies.


# Tracing the Location
TCP Traceroute:
sudo traceroute -T www.google.com

## OUTPUT
<img width="643" height="453" alt="image" src="https://github.com/user-attachments/assets/f6004d15-96a3-4942-a2a0-efad75748445" />

This image shows the output of a traceroute scan performed to the domain of University of Jena (uni-jena.de) using TCP mode (-T). The traceroute command traces the path that network packets take from the local system to the destination server. The results display multiple “hops,” which represent routers or network devices along the route. Each hop shows the IP address and response time in milliseconds, indicating how long it takes for packets to travel through that node. Some hops display * * *, which means those routers did not respond or blocked the request, a common behavior for security reasons. The route passes through different networks, including international backbone providers, before reaching German academic network infrastructure (such as DFN). The increasing latency values indicate the distance and number of networks crossed. Overall, this output demonstrates the path and performance of the connection from the user’s system to the University of Jena server.


## UDP Traceroute:
sudo traceroute -U www.google.com

## OUTPUT
<img width="656" height="470" alt="image" src="https://github.com/user-attachments/assets/79987935-9803-43ab-bbc9-63ea36628e33" />

This image shows the result of a UDP traceroute scan (traceroute -U) to the domain of University of Jena (uni-jena.de). The command traces the path taken by packets using UDP protocol over an IPv6 address. The first few hops display reachable network devices with their IP addresses and response times, indicating initial connectivity from the local network to upstream routers. However, after a few hops, most entries show * * *, which means those routers are not responding to UDP traceroute requests. This is common because many networks block or ignore UDP probes for security reasons. As a result, the full path to the destination cannot be completely mapped using UDP mode. The increasing latency in the visible hops reflects network distance, but the incomplete trace indicates filtering or firewall restrictions along the route.


## ICMP Traceroute:
sudo traceroute  www.google.com

## OUTPUT
<img width="651" height="515" alt="image" src="https://github.com/user-attachments/assets/0881617c-b7df-4f96-8a54-aa8517e64ee8" />

This image shows the output of a traceroute command to the domain of University of Jena (uni-jena.de) using the default protocol (ICMP over IPv6). The traceroute tracks the path that packets take from the user’s system to the destination server by listing intermediate routers, known as hops. Each hop displays an IPv6 address along with response times in milliseconds, indicating how long the packets take to reach that point. Some hops show * * *, meaning those routers did not respond or are blocking traceroute requests, which is common due to firewall or security settings. As the trace progresses, the latency increases, reflecting greater network distance. Toward the end, the route reaches nodes within the German academic network (DFN), indicating proximity to the destination server. Overall, this output demonstrates the network path and performance between the user’s system and the University of Jena server.

## RESULT:
The information gathering techniques tools/procedure were  identified successfully.
