# Cybersecurity & Penetration Testing Toolkit

A collection of essential tools used in penetration testing, vulnerability assessment, reconnaissance, exploitation, password auditing, and network traffic analysis.

> **Disclaimer:** Use these tools only on systems and networks you own or have explicit permission to test. Unauthorized testing may be illegal and unethical.

---

## Reconnaissance & Scanning

Gather information about targets, identify hosts, services, and open ports before performing security assessments.

### Nmap
The most important tool to learn first. Scans for open ports, running services, service versions, and operating system information.

**Common Uses:**
- Port scanning
- Service enumeration
- OS detection
- Network discovery

### Netdiscover
Maps devices on a local network using ARP requests.

**Common Uses:**
- Discover live hosts
- Identify unknown devices
- Internal network reconnaissance

### Whois / Dig
Tools for collecting domain and DNS information.

**Whois:**
- Domain ownership
- Registration details
- Registrar information

**Dig:**
- DNS record lookup
- Nameserver discovery
- DNS troubleshooting

### theHarvester
An OSINT (Open Source Intelligence) tool that collects publicly available information.

**Common Uses:**
- Email enumeration
- Subdomain discovery
- Host identification
- Public intelligence gathering

---

## Web Application Testing

Identify vulnerabilities and security weaknesses in web applications.

### Burp Suite
The industry-standard web application testing platform.

**Features:**
- HTTP/HTTPS interception
- Request modification
- Repeater testing
- Automated scanning (Professional Edition)

### Gobuster
A fast directory and file enumeration tool.

**Common Uses:**
- Hidden directory discovery
- File enumeration
- Virtual host discovery

### Nikto
Web server vulnerability and misconfiguration scanner.

**Checks For:**
- Default files
- Dangerous configurations
- Outdated software
- Common vulnerabilities

### SQLMap
Automated SQL injection testing framework.

**Features:**
- SQL injection detection
- Database enumeration
- Data extraction
- Authentication testing

---

## Exploitation

Simulate attacks and validate vulnerabilities in authorized environments.

### Metasploit Framework
One of the most widely used exploitation frameworks.

**Capabilities:**
- Exploit execution
- Payload generation
- Session management
- Post-exploitation modules

### Netcat (nc)
Known as the "Swiss Army Knife" of networking.

**Common Uses:**
- Port listening
- Network troubleshooting
- Data transfer
- TCP/UDP communication

### Searchsploit
Offline search utility for public exploits from Exploit-DB.

**Benefits:**
- Fast exploit lookup
- Local exploit database
- Vulnerability research

---

## Password & Hash Auditing

Assess password strength and identify weak credentials during authorized security assessments.

### John the Ripper
Popular password auditing and hash analysis tool.

**Features:**
- Dictionary attacks
- Rule-based attacks
- Multiple hash format support

### Hashcat
High-performance password recovery and auditing tool.

**Features:**
- GPU acceleration
- Large-scale hash testing
- Extensive hash support

### Hydra
Online authentication testing tool.

**Supported Services:**
- SSH
- FTP
- HTTP/HTTPS
- RDP
- Many other protocols

---

## Traffic Analysis

Capture and inspect network traffic to understand communication and identify issues.

### Wireshark
The world's most widely used packet analyzer.

**Capabilities:**
- Packet inspection
- Protocol analysis
- Network troubleshooting
- Security investigations

### Tcpdump
A lightweight command-line packet capture tool.

**Benefits:**
- Scriptable
- Fast and efficient
- Ideal for servers and remote systems

---

## Recommended Learning Path

1. Nmap
2. Burp Suite
3. Wireshark
4. Netcat
5. Gobuster
6. SQLMap
7. Metasploit
8. Hashcat
9. John the Ripper
10. theHarvester
11. Searchsploit

---

## License

This repository is intended for educational and authorized security testing purposes only. Users are responsible for complying with all applicable laws, regulations, and organizational policies.

---

### Learn • Practice • Secure 🔐
