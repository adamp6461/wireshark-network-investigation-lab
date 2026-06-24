# Incident Report: Network Traffic Investigation

## Executive Summary

A network traffic investigation was conducted using Wireshark to analyze packet-level communication generated within a Windows 11 virtual machine.

The objective was to capture and examine common network protocols during normal user activity, including Domain Name System (DNS) queries, Internet Control Message Protocol (ICMP) traffic, and Transmission Control Protocol (TCP) communication.

Traffic was intentionally generated through web browsing and network connectivity testing to simulate a basic troubleshooting scenario. Packet captures were analyzed to validate successful name resolution, connectivity, and TCP session establishment.

No abnormal or malicious network activity was identified during the investigation.

---

# Investigation Objectives

The objectives of this investigation were to:

* Capture live network traffic using Wireshark
* Analyze DNS name resolution
* Validate ICMP connectivity testing
* Inspect TCP packet details
* Observe the TCP Three-Way Handshake
* Document packet-level findings
* Establish a baseline of normal network activity

---

# Environment

| Component             | Details                  |
| --------------------- | ------------------------ |
| Operating System      | Windows 11               |
| Analysis Tool         | Wireshark                |
| Packet Capture Driver | Npcap                    |
| Network Interface     | Ethernet                 |
| Test Host             | Google DNS (8.8.8.8)     |
| Investigation Type    | Network Traffic Analysis |

---

# Investigation Timeline

| Step | Activity                               |
| ---- | -------------------------------------- |
| T1   | Verified packet capture interfaces     |
| T2   | Started live packet capture            |
| T3   | Generated ICMP traffic using ping      |
| T4   | Filtered ICMP packets                  |
| T5   | Inspected packet contents              |
| T6   | Investigated DNS queries and responses |
| T7   | Reviewed TCP packet details            |
| T8   | Identified TCP Three-Way Handshake     |

---

# Evidence Collected

## DNS Analysis

Wireshark captured successful DNS queries and responses generated during web browsing.

### Findings

* Standard DNS Queries observed
* Standard DNS Responses observed
* IPv4 (A) Records returned
* IPv6 (AAAA) Records returned
* Canonical Name (CNAME) Records identified

### Assessment

DNS name resolution completed successfully, confirming the client was able to resolve hostnames into IP addresses before initiating network communication.

---

## ICMP Analysis

Controlled ICMP traffic was generated using the Windows ping utility.

### Command Executed

```cmd
ping 8.8.8.8 -n 5
```

### Findings

* 5 Echo Requests transmitted
* 5 Echo Replies received
* 0% Packet Loss

### Assessment

Successful ICMP communication confirmed network connectivity between the client and the destination host.

---

## TCP Analysis

Transmission Control Protocol packets were examined to validate reliable network communication.

### Findings

* Source and destination ports identified
* TCP sequence numbers observed
* TCP acknowledgment numbers observed
* TCP flags successfully analyzed

### Assessment

Packet inspection confirmed normal TCP communication and reliable transport behavior.

---

## TCP Three-Way Handshake

Wireshark filtering identified the TCP session establishment process.

### Observed Sequence

1. SYN
2. SYN/ACK
3. ACK

### Assessment

The successful three-way handshake confirmed that the client and remote host established a reliable TCP connection before exchanging application data.

---

# Findings

The investigation confirmed:

* Successful DNS resolution
* Successful ICMP communication
* No packet loss during connectivity testing
* Successful TCP connection establishment
* Normal encrypted web traffic
* No abnormal packet behavior observed

---

# MITRE ATT&CK Reference

The investigation included review of the following ATT&CK technique for contextual understanding of observed network activity.

| Technique                       | ID        | Relationship                                |
| ------------------------------- | --------- | ------------------------------------------- |
| Application Layer Protocol: DNS | T1071.004 | DNS protocol observed during packet capture |

**Note:** All observed traffic was intentionally generated in a controlled lab environment and represents expected network behavior.

---

# Conclusion

Network traffic analysis successfully demonstrated the use of Wireshark to capture, filter, and inspect packet-level communications within a Windows environment.

Analysis confirmed successful DNS resolution, reliable ICMP communication, proper TCP session establishment, and expected encrypted network traffic. Packet inspection did not identify evidence of network anomalies, communication failures, or suspicious behavior.

This investigation demonstrated practical experience with packet capture, protocol analysis, network troubleshooting, and documentation of technical findings.

**Investigation Status:** Closed

**Severity:** Informational / Lab Environment
