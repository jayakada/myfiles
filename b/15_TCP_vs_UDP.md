# Experiment 15 – TCP vs UDP Basic Communication Simulation

## Aim
To simulate and compare TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) communication using Cisco Packet Tracer.

## Requirements
- 1 Cisco 2960 Switch
- 1 PC
- 1 Server
- Copper Straight-Through cables

## Theory
**TCP** is connection-oriented and provides reliable, ordered delivery using acknowledgements and connection establishment.

**UDP** is connectionless. It does not use a handshake or delivery acknowledgements, and is commonly used where low overhead and speed are important.

Examples:
- TCP: HTTP, FTP, SMTP, Telnet
- UDP: DNS, TFTP, DHCP, streaming and VoIP

## Network Topology
```text
       Switch
       /    \\
     PC0   Server0
```

## IP Addressing

| Device | IP Address | Subnet Mask | Gateway |
|---|---|---|---|
| PC0 | 192.168.1.2 | 255.255.255.0 | 192.168.1.1 |
| Server0 | 192.168.1.10 | 255.255.255.0 | 192.168.1.1 |

Gateway is optional when only one LAN is used.

## Procedure

### 1. Create Topology
1. Place one 2960 switch, one PC and one Server.
2. Connect them using Copper Straight-Through cables.

### 2. Configure IP Addresses
Configure PC0 as `192.168.1.2/24` and Server0 as `192.168.1.10/24`.

### 3. Test Connectivity
On PC0 Command Prompt:
```bash
ping 192.168.1.10
```

## Part A – TCP Communication Simulation

### 4. Enable HTTP
1. Open Server0 → Services → HTTP.
2. Turn HTTP **ON**.

### 5. Access HTTP Page
On PC0 → Desktop → Web Browser, enter:
```text
http://192.168.1.10
```

### 6. Observe TCP in Simulation Mode
1. Switch to Simulation Mode.
2. Enable TCP and HTTP filters.
3. Click Capture/Forward.

Observe:
```text
TCP SYN
   ↓
TCP SYN-ACK
   ↓
TCP ACK
   ↓
HTTP GET
   ↓
HTTP Response
   ↓
TCP FIN
   ↓
TCP ACK
```
The first three messages form the TCP Three-Way Handshake.

## Part B – UDP Communication Simulation

### 7. Enable DNS
1. Open Server0 → Services → DNS.
2. Turn DNS **ON**.
3. Create a record:
```text
Name: server.com
Address: 192.168.1.10
```

### 8. Configure DNS on PC
Open PC0 → Desktop → IP Configuration and set:
```text
DNS Server: 192.168.1.10
```

### 9. Test DNS
On PC0 → Desktop → Web Browser, enter:
```text
http://server.com
```
Packet Tracer first sends a DNS Query using UDP. After DNS resolution, the HTTP request uses TCP.

### 10. Observe UDP
1. Switch to Simulation Mode.
2. Enable UDP and DNS filters.
3. Click Capture/Forward.
4. Observe DNS Query and DNS Response.

```text
DNS Query
    ↓
DNS Response

No Handshake
No ACK
```

## TCP vs UDP Comparison

| Feature | TCP | UDP |
|---|---|---|
| Connection | Connection-oriented | Connectionless |
| Handshake | Yes | No |
| Reliable delivery | Yes | No guarantee |
| Acknowledgement | Yes | No |
| Error recovery | Yes | No built-in retransmission |
| Speed | Generally slower | Generally faster |
| Packet ordering | Maintained | Not guaranteed |
| Header size | 20 bytes minimum | 8 bytes |

## Expected Output
**TCP:** Successful webpage access, three-way handshake observed, reliable delivery and acknowledgements.

**UDP:** DNS query successful, no handshake and no acknowledgements.

## Result
TCP and UDP were successfully simulated in Cisco Packet Tracer. TCP demonstrated reliable communication using a three-way handshake and acknowledgements, while UDP demonstrated connectionless communication.
