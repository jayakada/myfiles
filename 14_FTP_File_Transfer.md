# Experiment 14 – FTP File Transfer Between Client and Server

## Aim
To configure an FTP server and perform file transfer between a client PC and the server using Cisco Packet Tracer.

## Requirements
- 1 PC
- 1 Server
- 1 Cisco 2960 Switch
- Copper Straight-Through cables

## Theory
FTP (File Transfer Protocol) is used to transfer files between a client and server. FTP uses TCP. The control connection uses Port 21.

## Network Topology
```text
       Switch (2960)
        /        \\
      PC0       Server0
```

## IP Addressing

| Device | IP Address | Subnet Mask | Default Gateway |
|---|---|---|---|
| PC0 | 192.168.1.2 | 255.255.255.0 | 192.168.1.1 |
| Server0 | 192.168.1.10 | 255.255.255.0 | 192.168.1.1 |

The gateway is optional because both devices are on the same LAN.

## Procedure

### 1. Create Network
1. Add one PC, one Server and one 2960 switch.
2. Connect PC0 and Server0 to the switch using Copper Straight-Through cables.

### 2. Configure IP Addresses
PC0 → Desktop → IP Configuration:
```text
IP Address: 192.168.1.2
Subnet Mask: 255.255.255.0
Default Gateway: 192.168.1.1
```
Server0 → Desktop → IP Configuration:
```text
IP Address: 192.168.1.10
Subnet Mask: 255.255.255.0
Default Gateway: 192.168.1.1
```

### 3. Verify Connectivity
On PC0 Command Prompt:
```bash
ping 192.168.1.10
```

### 4. Configure FTP Server
1. Open Server0 → **Services → FTP**.
2. Turn FTP Service **ON**.
3. Add user:
```text
Username: student
Password: cisco123
```

### 5. Create File on Server
In Server0 → Services → FTP, create and save:
```text
Filename: network.txt
Contents:
Welcome to FTP Server
Cisco Packet Tracer Lab
Networking Practical
```

### 6. Access FTP from Client
On PC0 → Desktop → Command Prompt:
```bash
ftp 192.168.1.10
```
Enter username `student` and password `cisco123`.

### 7. FTP Commands

| Command | Purpose |
|---|---|
| `dir` or `ls` | List available files |
| `get network.txt` | Download a file |
| `put student.txt` | Upload a file |
| `delete filename` | Delete a file |
| `pwd` | Display current directory |
| `bye` or `quit` | Disconnect |

Download:
```bash
get network.txt
```
Upload:
```bash
put student.txt
```
Exit:
```bash
bye
```

### 8. Simulation Mode
1. Switch Packet Tracer to Simulation Mode.
2. Enable FTP and TCP filters.
3. Click Capture/Forward repeatedly.
4. Observe TCP SYN, SYN-ACK, ACK, FTP login, file request, file transfer and connection closing (FIN/ACK).

## Expected Output
```text
Connected to 192.168.1.10
Username: student
Login successful

ftp> dir
network.txt

ftp> get network.txt
Transfer complete

ftp> put student.txt
Transfer complete

ftp> bye
Connection closed
```

## Result
The FTP server was successfully configured. The client established a TCP connection, authenticated with valid credentials and successfully uploaded and downloaded files.
