# Experiment 1 – Basic LAN Setup and IP Addressing Between PCs

## Aim
To design and configure a basic Local Area Network (LAN) using Cisco Packet Tracer by assigning IP addresses to PCs and verifying communication using the Ping command.

## Requirements
- Cisco Packet Tracer
- 2 PCs
- 1 Cisco 2960 Switch
- Copper Straight-Through cables

## Network Topology
```text
PC0 ---- Switch ---- PC1
```

## IP Addressing

| Device | IP Address | Subnet Mask | Default Gateway |
|---|---|---|---|
| PC0 | 192.168.1.1 | 255.255.255.0 | Leave blank |
| PC1 | 192.168.1.2 | 255.255.255.0 | Leave blank |

## Procedure
1. Open Cisco Packet Tracer and create a new project.
2. Add PC0, PC1 and one Cisco 2960 switch.
3. Select Copper Straight-Through cable.
4. Connect PC0 FastEthernet0 to Switch Fa0/1.
5. Connect PC1 FastEthernet0 to Switch Fa0/2.
6. On each PC, open **Desktop → IP Configuration** and enter the IP address and subnet mask from the table.
7. On PC0, open **Desktop → Command Prompt** and run `ipconfig`.
8. Test communication using `ping 192.168.1.2`.
9. On PC1, test using `ping 192.168.1.1`.

## Expected Output
```text
Reply from 192.168.1.2
Packets: Sent = 4
Received = 4
Lost = 0
```

## Result
A basic LAN was successfully created in Cisco Packet Tracer. Static IP addresses were assigned to the PCs, and connectivity between them was verified using the Ping command.
