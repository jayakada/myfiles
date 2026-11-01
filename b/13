# Experiment 13 – HTTP Web Server and Client Communication

## Aim
To configure an HTTP Web Server and establish communication between a client PC and the web server using Cisco Packet Tracer.

## Requirements
- Cisco 2911 Router – 1
- Cisco 2960 Switch – 1
- Server – 1
- PC – 1 or 2
- Copper Straight-Through cables

## Theory
HTTP (Hypertext Transfer Protocol) is an Application Layer protocol used for communication between web browsers and web servers. The client sends an HTTP Request; the server processes it and returns an HTTP Response. HTTP uses TCP and Port 80 by default.

## Network Topology
```text
       Router
          |
        Switch
        /    \\
      PC0   Server
```

## IP Addressing

| Device | IP Address | Subnet Mask | Default Gateway |
|---|---|---|---|
| Router G0/0 | 192.168.1.1 | 255.255.255.0 | — |
| Server | 192.168.1.100 | 255.255.255.0 | 192.168.1.1 |
| PC0 | 192.168.1.10 | 255.255.255.0 | 192.168.1.1 |
| PC1 (optional) | 192.168.1.11 | 255.255.255.0 | 192.168.1.1 |

## Procedure

### 1. Create the Network
1. Open Cisco Packet Tracer.
2. Add one Cisco 2911 router, one Cisco 2960 switch, one server and one or two PCs.
3. Connect all devices using Copper Straight-Through cables.

### 2. Configure Router
Open Router CLI:
```bash
enable
configure terminal
interface g0/0
ip address 192.168.1.1 255.255.255.0
no shutdown
exit
```

### 3. Configure Web Server
Open Server → **Desktop → IP Configuration**:
```text
IP Address: 192.168.1.100
Subnet Mask: 255.255.255.0
Default Gateway: 192.168.1.1
```

### 4. Enable HTTP
Open Server → **Services → HTTP** and set HTTP Service to **ON**.

### 5. Create Web Page
Edit the default `index.html` page:
```html
<html>
<head>
<title>Computer Networks Lab</title>
</head>
<body bgcolor="lightblue">
<h1 align="center">WELCOME TO COMPUTER NETWORKS LAB</h1>
<hr>
<h2 align="center">HTTP Web Server Successfully Configured</h2>
<p align="center">Department of Computer Science and Engineering</p>
<p align="center">Cisco Packet Tracer Laboratory Experiment</p>
</body>
</html>
```
Click Save.

### 6. Configure Client PC
Open PC0 → **Desktop → IP Configuration**:
```text
IP Address: 192.168.1.10
Subnet Mask: 255.255.255.0
Default Gateway: 192.168.1.1
```

### 7. Verify Connectivity
On PC0 → **Desktop → Command Prompt**:
```bash
ping 192.168.1.100
```

### 8. Access Web Server
On PC0 → **Desktop → Web Browser**, enter:
```text
http://192.168.1.100
```
Click Go. The configured webpage should appear.

## Expected Output
The browser displays:
```text
WELCOME TO COMPUTER NETWORKS LAB
HTTP Web Server Successfully Configured
```

## Result
The HTTP Web Server was successfully configured in Cisco Packet Tracer. The client PC communicated with the server and accessed the hosted webpage using HTTP.
