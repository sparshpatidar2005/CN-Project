# Network Attack Detection Using Wireshark 🔐

A Computer Networks project focused on understanding, simulating in controlled lab environments, and analyzing network attacks using **Wireshark**. The project explores Denial of Service (DoS), Distributed Denial of Service (DDoS), and SQL injection traffic, with an emphasis on packet analysis and identifying suspicious network behavior.

## 📌 Project Overview

Network security is an important part of protecting systems, applications, and data. Network traffic analysis helps identify unusual communication patterns and investigate potential attacks.

This project uses Wireshark to capture and inspect packets, apply display filters, compare normal and suspicious traffic, and study how different network attacks appear at the packet level.

## 🎯 Objectives

- Understand the behavior of common network attacks.
- Analyze TCP/IP communication and packet-level activity.
- Identify suspicious traffic patterns using Wireshark.
- Explore DoS and DDoS detection through SYN packet analysis.
- Study SQL injection requests in HTTP traffic.
- Understand the role of packet statistics, conversations, and I/O graphs in network security analysis.

## 📂 Project Files

| File | Description |
|---|---|
| `NETWORK_ATTACKS_DETECTION_USING_WIRESHARK (REPORT).docx` | Detailed project report covering Wireshark, DoS, DDoS, SQL injection, MITM, phishing concepts, and traffic analysis. |
| `dos.mp4` | Video demonstration related to DoS attacks and their network traffic. |
| `ddos.mp4` | Video demonstration related to DDoS attacks and traffic analysis. |
| `sql.mp4` | Video demonstration related to SQL injection and its network traffic. |

The repository intentionally excludes presentation files and the separate phishing video.

## 🛠️ Tools and Technologies

- **Wireshark** — packet capture, protocol inspection, display filters, and traffic visualization.
- **TCP/IP** — understanding transport-layer communication and connection establishment.
- **HTTP** — examining web requests and application-layer traffic.
- **DVWA (Damn Vulnerable Web Application)** — an intentionally vulnerable application used in controlled SQL injection demonstrations.
- **hping3 and Scapy** — discussed in the report for controlled traffic simulation.
- **C** — TCP client-server examples included in the report.

## 🔍 Topics Covered

### 1. Denial of Service (DoS)

A DoS attack attempts to make a service unavailable by overwhelming its resources. The report discusses TCP SYN floods, UDP floods, and ICMP floods.

**Wireshark analysis includes:**
- Filtering TCP SYN packets using `tcp.flags.syn == 1`
- Identifying initial SYN packets without ACK using `tcp.flags.syn == 1 && tcp.flags.ack == 0`
- Inspecting communicating IP addresses through **Statistics → Conversations**
- Comparing packet rates using **Statistics → I/O Graphs**
- Examining retransmissions and incomplete TCP handshakes

### 2. Distributed Denial of Service (DDoS)

A DDoS attack distributes traffic across multiple sources, making analysis and mitigation more challenging.

The report explores:
- Traffic originating from multiple source addresses
- Protocol Hierarchy statistics
- SYN packet patterns
- I/O graph spikes and packet-rate changes
- TCP retransmissions and incomplete sessions

### 3. SQL Injection

SQL injection occurs when user input is interpreted as part of an SQL query instead of being handled strictly as data.

The report discusses SQL injection concepts and analysis using DVWA in a controlled lab environment.

**Wireshark analysis includes:**
- Inspecting HTTP GET and POST requests
- Filtering HTTP traffic
- Examining request parameters and suspicious input patterns
- Following a TCP stream to inspect the client-server exchange
- Comparing request and response behavior

Example display filters discussed in the report include:

```text
http
http.request.method == "POST"
http.request.method == "GET"
tcp.analysis.retransmission
```

A display filter helps narrow the packets being inspected; it does not independently prove that an attack occurred.

### 4. Additional Topics in the Report

The report also discusses Man-in-the-Middle (MITM) attacks and phishing concepts. These topics are documented in the report but do not have separate demonstration videos included in this repository.

## 📊 Learning Outcomes

Through this project, the following concepts are explored:

- Understanding packet headers and network protocols
- Interpreting TCP connection establishment
- Identifying unusual packet volumes and communication patterns
- Using Wireshark display filters
- Examining network conversations and protocol statistics
- Visualizing packet activity over time
- Investigating suspicious HTTP requests
- Understanding the importance of secure web application design and network monitoring

## 🚀 Getting Started

1. Install Wireshark from the official website: https://www.wireshark.org/
2. Open a packet capture or start a capture on an appropriate network interface.
3. Apply the relevant display filters described in the report.
4. Use **Statistics → Conversations**, **Protocol Hierarchy**, and **I/O Graphs** to inspect traffic.
5. Review the report and demonstration videos to understand the analysis workflow.

The videos are demonstrations, while the report provides the broader explanations and procedures. Exact reproduction may require the same lab setup and software configuration used during the demonstrations.

## ⚠️ Ethical Use and Disclaimer

This is an educational Computer Networks project. Traffic generation and vulnerability demonstrations should only be performed on systems and networks that you own or have explicit permission to test. Use intentionally vulnerable applications such as DVWA only in an isolated, controlled lab.

Wireshark observations can help investigate suspicious activity, but individual packets or traffic spikes are not conclusive proof of an attack.

## 📄 License

No license is currently specified. Confirm that you have the right to publish the report and demonstration videos before adding a license or redistributing the materials.

---

**Project:** Network Attack Detection Using Wireshark  
**Domain:** Computer Networks and Network Security  
**Focus:** Packet analysis, attack traffic investigation, and security awareness
