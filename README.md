# Wireshark Network Traffic Analysis Project

## Project Overview
This project demonstrates basic network traffic analysis using Wireshark and Nmap.
The goal was to capture live traffic, identify normal vs suspicious behavior, and detect a TCP SYN port scan.

## Lab Environment
- OS: Windows 11
- Network: Mobile hotspot (DHCP assigned private IP)
- Tools:
  - Wireshark
  - Nmap

## Objectives
- Capture live traffic
- Identify normal HTTPS traffic
- Perform a TCP SYN scan using Nmap
- Detect scan behavior in Wireshark
- Write a basic incident report

## Key Finding: TCP SYN Scan Detected

During analysis, multiple TCP SYN packets were observed from the host to the gateway IP within a very short time interval.

Indicators:
- Same source IP
- Same destination IP
- Multiple destination ports
- SYN flag set, ACK flag not set

This behavior is consistent with a TCP SYN port scan.

## Evidence

### SYN Packets Sent to Multiple Ports
![SYN Packets](evidence/syn-packets.png)

### SYN-ACK Response (Open Port 53)
![SYN-ACK Response](evidence/syn-ack-response.png)

### RST Responses (Closed Ports)
![RST Responses](evidence/rst-closed-ports.png)

### Protocol Hierarchy Overview
![Protocol Hierarchy](evidence/protocol-hierarchy.png)

## Skills Demonstrated
- Packet filtering (tcp.flags.syn == 1 and tcp.flags.ack == 0)
- TCP handshake analysis
- Identifying open vs closed ports
- Understanding SYN, SYN-ACK, and RST responses

## Conclusion
This project demonstrates the ability to detect and analyze port scanning activity using Wireshark.
