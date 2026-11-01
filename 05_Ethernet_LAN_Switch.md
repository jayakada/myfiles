# Experiment 5 – Ethernet LAN Setup Using Switch

## Aim
To design and configure an Ethernet LAN using a switch in Cisco Packet Tracer and verify communication between multiple computers using static IP addressing.

## Requirements
- Cisco 2960 Switch – 1
- PCs – 4
- Copper Straight-Through cables – 4

## Theory
Ethernet LAN connects devices in a limited geographical area using Ethernet technology (IEEE 802.3). A Layer-2 switch forwards Ethernet frames based on destination MAC addresses and learns MAC addresses dynamically.

## Network Topology
```text
             Cisco 2960 Switch
          /       |       |       \\
        PC0      PC1     PC2      PC3
```

## IP Addressing

| Device | IP Address | Subnet Mask |
|---|---|---|
| PC0 | 192.168.1.10 | 255.255.255.0 |
| PC1 | 192.168.1.11 | 255.255.255.0 |
| PC2 | 192.168.1.12 | 255.255.255.0 |
| PC3 | 192.168.1.13 | 255.255.255.0 |

## Procedure
1. Launch Cisco Packet Tracer.
2. Add one Cisco 2960 switch and four PCs.
3. Connect the PCs to the switch using Copper Straight-Through cables.
4. Use these switch ports: PC0–Fa0/1, PC1–Fa0/2, PC2–Fa0/3, PC3–Fa0/4.
5. Configure each PC's IP address and subnet mask under **Desktop → IP Configuration**.
6. From PC0 Command Prompt, run:
   - `ping 192.168.1.11`
   - `ping 192.168.1.12`
   - `ping 192.168.1.13`
7. Optional: Open switch CLI and enter:
```bash
enable
show mac address-table
```

## Observation
- Switch port LEDs turn green.
- PCs have unique IP addresses.
- Successful Ping replies confirm connectivity.
- The switch dynamically learns MAC addresses.

## Result
An Ethernet LAN was successfully configured using a Cisco 2960 switch. All connected PCs communicated using static IP addressing, and connectivity was verified using Ping.
