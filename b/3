# Experiment 3 – Ping Command for Connectivity Testing

## Aim
To verify network connectivity between computers in a LAN using the Ping command in Cisco Packet Tracer.

## Requirements
- Cisco Packet Tracer
- 2 PCs
- 1 Cisco 2960 Switch
- 2 Copper Straight-Through cables

## Network Topology
```text
PC0 ---- Cisco 2960 Switch ---- PC1
```

## IP Address Configuration

| Device | IP Address | Subnet Mask | Default Gateway |
|---|---|---|---|
| PC0 | 192.168.1.1 | 255.255.255.0 | Not required |
| PC1 | 192.168.1.2 | 255.255.255.0 | Not required |

## Theory
Ping is a network diagnostic command used to check whether a destination device is reachable. It sends an ICMP Echo Request; if the destination is reachable, it returns an ICMP Echo Reply. It can also measure Round-Trip Time (RTT).

## Procedure
1. Open Cisco Packet Tracer.
2. Place two PCs and one Cisco 2960 switch.
3. Connect both PCs to the switch using Copper Straight-Through cables.
4. Configure PC0 with IP `192.168.1.1` and subnet mask `255.255.255.0`.
5. Configure PC1 with IP `192.168.1.2` and subnet mask `255.255.255.0`.
6. On PC0, open **Desktop → Command Prompt** and run `ipconfig`.
7. Test connectivity using `ping 192.168.1.2`.
8. On PC1, run `ping 192.168.1.1`.

## Expected Output
```text
Pinging 192.168.1.2 with 32 bytes of data:
Reply from 192.168.1.2: bytes=32 time<1ms TTL=128
Reply from 192.168.1.2: bytes=32 time<1ms TTL=128
Reply from 192.168.1.2: bytes=32 time<1ms TTL=128
Reply from 192.168.1.2: bytes=32 time<1ms TTL=128

Packets: Sent = 4
Received = 4
Lost = 0 (0% loss)
```

## Simulation Mode
1. Switch from Realtime to Simulation mode.
2. In Edit Filters, enable ARP and ICMP.
3. Run the Ping command from PC0.
4. Click Capture/Forward repeatedly.
5. Observe ARP Request, ARP Reply, ICMP Echo Request and ICMP Echo Reply.

## Packet Flow
```text
PC0 -- ARP Request --> Switch --> PC1
PC0 <-- ARP Reply --- Switch <-- PC1
PC0 -- ICMP Echo Request --> PC1
PC0 <-- ICMP Echo Reply --- PC1
```

## Result
Network connectivity between two PCs was successfully verified using Ping. ICMP Echo Request and Echo Reply packets were observed in Simulation Mode.
