# Network Scan using Nmap & Wireshark

This project demonstrates how to perform **network port scanning** on a local network using **Nmap**, and how to analyze the scan traffic using **Wireshark**. It was created as part of a cybersecurity internship task to develop hands-on skills in basic network reconnaissance.

---

## Objectives

- Identify live hosts and open ports on a target machine
- Understand Nmap scan types (SYN, TCP connect, version detection, etc.)
- Capture and analyze scan traffic using Wireshark
- Document observations and findings

---

## Tools Used

-  **Nmap** - For scanning networks and ports  
-  **Wireshark** - For capturing and analyzing packet-level data  
-  **Kali Linux / Ubuntu** - Operating system used in the lab environment  
-  **VirtualBox / VMware** - For setting up the test network (Kali + Metasploitable)

---

## Steps Performed

### 1. Identify IP Addresses
``` bash
ip a    # To check own IP
``` 
### 2.Run Nmap Scan
``` bash
sudo nmap -sS -oN scan_results.txt 192.168.154.0/24
```
   
  -sS → SYN scan (stealthy and fast) <br>
  -oN → Output saved to a human-readable file (scan_results.txt) <br>
   192.168.154.0/24 → Scans all hosts in the subnet <br>
   
``` bash
sudo nmap -sV 192.168.154.0/24
```   
   -sV → Service and version detection  

### 3. Capture with Wireshark
Used filters like: tcp.port == 80 or ip.addr == 192.168.154.160 <br>

Analyze:

  TCP handshakes <br>
  SYN, SYN-ACK, RST patterns <br>
  Service banners from version detection 

## Output Files 
   scan_results.txt – Nmap scan output <br> 
   packet_capture.pcap – Wireshark capture file <br>
   Screenshots – Evidence of scan and capture steps

## Learnings 
   Understood how Nmap communicates with hosts during different scan types <br>
   Gained experience with Wireshark filters and analysis

## Conclusion
   This task provided foundational experience in performing ethical network scans and analyzing the resulting network traffic. These techniques are essential for roles in cybersecurity,          penetration testing, and system auditing.

## Disclaimer

This project was conducted in a **controlled lab environment** using authorized systems only.  
Do **not** use tools like Nmap or Wireshark on public or unauthorized networks.  
Always ensure you have **explicit permission** before performing any network scans or packet captures.

