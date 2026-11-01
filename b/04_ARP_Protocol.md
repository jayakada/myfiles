# Experiment 4 – ARP Protocol Simulation in LAN

## Aim
To simulate the working of Address Resolution Protocol (ARP) in a LAN and observe how a device resolves an IP address into a MAC address before communication.

## Requirements
- Cisco Packet Tracer 8.x or above
- 1 Cisco 2960 Switch
- 2 PCs
- Copper Straight-Through cables

## Network Topology
```text
PC0 ---- Switch0 ---- PC1
```

## IP Addressing

| Device | IP Address | Subnet Mask | Gateway |
|---|---|---|---|
| PC0 | 192.168.1.10 | 255.255.255.0 | Not required |
| PC1 | 192.168.1.20 | 255.255.255.0 | Not required |

## Theory
ARP (Address Resolution Protocol) finds the MAC address associated with an IP address on a local network.
- ARP Request: Broadcast message asking who owns the target IP address.
- ARP Reply: Unicast response containing the target device's MAC address.

## Procedure
1. Open Cisco Packet Tracer.
2. Add one 2960 switch and two PCs.
3. Connect both PCs to the switch using Copper Straight-Through cables.
4. Configure PC0 as `192.168.1.10/24`.
5. Configure PC1 as `192.168.1.20/24`.
6. On PC0 Command Prompt, run `ping 192.168.1.20`.
7. Switch to Simulation Mode and clear previous events.
8. Enable only ARP and ICMP filters.
9. Run `ping 192.168.1.20` again.
10. Click Capture/Forward repeatedly and observe the packet sequence.
11. On PC0, run `arp -a` to view the ARP table.

## ARP Packet Flow
```text
PC0 -- ARP Request (Broadcast) --> Switch --> PC1
PC0 <-- ARP Reply (Unicast) ----- Switch <-- PC1
PC0 -- ICMP Echo Request -----------------> PC1
PC0 <-- ICMP Echo Reply ------------------ PC1
```

## Expected Observations
- ARP Request is broadcast to devices.
- The destination PC sends an ARP Reply.
- ARP Reply is unicast.
- The MAC address is stored in the ARP cache.
- Later packets can use the stored entry until it expires.

## Command
```bash
arp -a
```

Example output (MAC address will vary):
```text
Internet Address    Physical Address    Type
192.168.1.20        000C.85A2.1F23       Dynamic
```

## Result
ARP was successfully simulated in Cisco Packet Tracer. The ARP Request was broadcast, the ARP Reply was unicast, and the ARP cache was updated.
