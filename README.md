# Basics-of-Nmap 
# Cyber Security Internship – Task 1

## Task Title: Scan Your Local Network for Open Ports

### Objective
To perform a TCP SYN scan using Nmap on my local network to identify active devices, their open ports, and understand the potential security risks associated with those open ports.

## Tools Used
- **Nmap** – For scanning devices and ports on the network
- **Operating System**: Kali Linux
- **GitHub** – For documentation and submission

## Steps Followed
### 1. Identified Local IP Address
Used the following command:
```bash
ifconfig / ip a   # (on Linux)

 My target IP was identified as 172.16.148.203.

2. Performed Aggressive Full Port Scan on Target

Ran an aggressive Nmap scan on all TCP ports:

nmap -T4 -A -p- 172.16.148.203

To save as HTML:

nmap -T4 -A -p- 172.16.148.203 -oX full_scan.xml
xsltproc full_scan.xml -o full_scan.html

3. Observed Open Ports and Services

I analyzed the scan results to identify:

IP Address	Open Ports	Services Detected

172.16.148.203	22, 80, 443	SSH, HTTP, HTTPS

## Security Risk Analysis

Port 22 (SSH): If exposed to the internet and weak credentials are used, it's vulnerable to brute-force attacks.

Port 80 (HTTP): Sends unencrypted data; could be intercepted in transit.

Port 443 (HTTPS): Secure, but should ensure SSL/TLS certificates are up to date.

## What is the Use of Nmap?

Nmap (short for Network Mapper) is an open-source tool used for network discovery, security auditing, and troubleshooting. It's one of the most powerful and widely used tools in cybersecurity and network administration.

1. Port Scanning

Discover open ports on a system (e.g., 22 for SSH, 80 for HTTP).

Helps identify which services are running and where systems might be vulnerable.

nmap -p 172.16.148.203

2. Service & Version Detection

Detects what service is running on an open port (e.g., Apache HTTP Server).

Identifies software versions, which is useful to find vulnerabilities.

nmap -sV 172.16.148.203

3. Operating System Detection

Tries to identify the OS (Windows, Linux, etc.) of the target device using TCP/IP fingerprinting.

nmap -O 172.16.148.203

4. Vulnerability Detection (via NSE scripts)

Uses Nmap Scripting Engine (NSE) to run scripts that can detect known vulnerabilities.

Example: Finding Heartbleed, SMBv1 vulnerabilities, etc.

nmap --script vuln 172.16.148.203

5. Network Mapping & Device Discovery

Discover all devices on a network.

Helps administrators visualize and secure their network.

nmap -sn 172.16.148.203

## Learning Outcomes

Learned how to perform a comprehensive aggressive scan using Nmap.

Identified network services and assessed their exposure/risk.

Gained insight into reconnaissance methods used in cybersecurity.
