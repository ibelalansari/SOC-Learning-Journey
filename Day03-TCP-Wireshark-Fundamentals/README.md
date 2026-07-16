# Day 03 - TCP, Wireshark & Network Traffic Fundamentals

## Overview

On Day 3 of my SOC Analyst learning journey, I explored fundamental networking concepts by capturing and analyzing live network traffic using Wireshark.

The primary objective of this lab was to understand how network communication occurs at the packet level and to analyze common protocols used in everyday network traffic.

---

# Lab Objectives

- Install and configure Wireshark
- Capture live network traffic
- Understand TCP Three-Way Handshake
- Analyze TCP Flags
- Observe DNS Query and Response
- Analyze ICMP Echo Request and Reply
- Analyze ARP Request and Response
- Practice Wireshark Display Filters
- Save packet captures for future analysis

---

# Lab Environment

| Item | Value |
|------|-------|
| Operating System | Windows 10 |
| Tool | Wireshark 4.6.7 |
| Network | Home Wi-Fi |
| Packet Capture Format | .pcapng |

---

# Packet Capture

Capture File

```
captures/day03-first-capture.pcapng
```

---

# TCP Three-Way Handshake

```
Client                           Server

SYN ----------------------------->

          <----------------------- SYN + ACK

ACK ----------------------------->
```

This process establishes a reliable TCP connection before data transmission begins.

---

# TCP Flags

| Flag | Description |
|------|-------------|
| SYN | Starts a TCP connection |
| SYN-ACK | Server acknowledges the connection request |
| ACK | Confirms received packets |
| FIN | Gracefully terminates a connection |
| RST | Immediately resets a connection |

---

# Screenshots

## 1. Wireshark Home

<p align="center">
<img src="screenshots/01-wireshark-home.png" width="900">
</p>

---

## 2. Live Packet Capture

<p align="center">
<img src="screenshots/02-live-packet-capture.png" width="900">
</p>

---

## 3. DNS Analysis

Display Filter

```
dns
```

<p align="center">
<img src="screenshots/03-dns-filter.png" width="900">
</p>

### Observation

- DNS Query
- DNS Response
- Google lookup
- ChatGPT lookup

---

## 4. ICMP Analysis

Display Filter

```
icmp
```

<p align="center">
<img src="screenshots/04-icmp-filter.png" width="900">
</p>

### Observation

- Echo Request
- Echo Reply
- Successful Ping

---

## 5. TCP Traffic

Display Filter

```
tcp
```

<p align="center">
<img src="screenshots/05-tcp-filter.png" width="900">
</p>

### Observation

- HTTPS Communication
- TLS Traffic
- TCP Sessions

---

## 6. TCP SYN Packets

Display Filter

```
tcp.flags.syn == 1
```

<p align="center">
<img src="screenshots/06-tcp-syn.png" width="900">
</p>

### Observation

Connection initiation packets.

---

## 7. TCP SYN-ACK Packets

Display Filter

```
tcp.flags.syn == 1 && tcp.flags.ack == 1
```

<p align="center">
<img src="screenshots/07-tcp-syn-ack.png" width="900">
</p>

### Observation

Server acknowledgement during connection establishment.

---

## 8. TCP ACK Packets

Display Filter

```
tcp.flags.ack == 1 && tcp.flags.syn == 0
```

<p align="center">
<img src="screenshots/08-tcp-ack.png" width="900">
</p>

### Observation

Acknowledgement packets exchanged after successful connection.

---

## 9. Ping Verification

Command

```cmd
ping google.com
```

<p align="center">
<img src="screenshots/09-ping-command.png" width="900">
</p>

---

## 10. ARP Analysis

Display Filter

```
arp
```

<p align="center">
<img src="screenshots/10-arp-filter.png" width="900">
</p>

### Observation

ARP Request

```
Who has 192.168.110.149?
```

ARP Reply

```
192.168.110.149 is at 00:e0:4d:00:32:4b
```

This demonstrates how IP addresses are resolved to MAC addresses within a local network.

---

# Wireshark Display Filters Used

```text
dns

icmp

tcp

arp

tcp.flags.syn == 1

tcp.flags.syn == 1 && tcp.flags.ack == 1

tcp.flags.ack == 1 && tcp.flags.syn == 0
```

---

# Key Learnings

- Installed Wireshark successfully
- Captured live network traffic
- Understood TCP Three-Way Handshake
- Learned TCP Flags
- Analyzed DNS communication
- Captured ICMP Echo Request and Reply
- Observed ARP Request and Response
- Practiced common Wireshark display filters
- Saved packet captures for future investigation

---

# Repository Structure

```
Day03-TCP-Wireshark-Fundamentals
│
├── README.md
│
├── captures
│   └── day03-first-capture.pcapng
│
└── screenshots
    ├── 01-wireshark-home.png
    ├── 02-live-packet-capture.png
    ├── 03-dns-filter.png
    ├── 04-icmp-filter.png
    ├── 05-tcp-filter.png
    ├── 06-tcp-syn.png
    ├── 07-tcp-syn-ack.png
    ├── 08-tcp-ack.png
    ├── 09-ping-command.png
    └── 10-arp-filter.png
```

---

# Next Steps

- Windows Event Logs
- Sysmon
- Microsoft Defender
- Microsoft Sentinel
- KQL
- Splunk
- Detection Engineering

---

## Author

**Belal Ansari**

GitHub: https://github.com/ibelalansari

LinkedIn: https://linkedin.com/in/ibelalansari
