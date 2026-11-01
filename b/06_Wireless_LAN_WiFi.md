# Experiment 6 – Wireless LAN (Wi-Fi) Configuration

## Aim
To design and configure a Wireless LAN using a wireless router in Cisco Packet Tracer and establish communication between wired and wireless devices.

## Requirements
- Wireless Router (WRT300N) – 1
- Laptops – 2
- PC – 1
- Copper Straight-Through cable – 1

## Theory
A Wireless LAN allows devices to communicate using radio waves instead of physical cables. Wi-Fi follows IEEE 802.11 standards. A wireless router can provide routing, switching, wireless access and DHCP services.

## Network Topology
```text
              Wireless Router
                /         \\
          Wired PC       Wi-Fi
                         /   \\
                    Laptop0  Laptop1
```

## Configuration

| Parameter | Value |
|---|---|
| Router IP | 192.168.0.1 |
| Subnet Mask | 255.255.255.0 |
| DHCP Server | Enabled |
| SSID | CollegeWiFi |
| Network Mode | Mixed |
| Channel | Auto |
| Security Mode | WPA2 Personal |
| Encryption | AES |
| Passphrase | College@123 |

## Procedure
1. Open Cisco Packet Tracer.
2. Place one WRT300N wireless router, one PC and two laptops.
3. Connect PC0 FastEthernet0 to Router Ethernet Port 1 using a Copper Straight-Through cable.
4. Open the router GUI and configure router IP `192.168.0.1`, subnet mask `255.255.255.0`, and enable DHCP.
5. Go to **GUI → Wireless** and set SSID to `CollegeWiFi`, Network Mode to Mixed and Channel to Auto.
6. Go to **Wireless → Wireless Security**.
7. Select WPA2 Personal, AES and passphrase `College@123`; save.
8. On Laptop0, open **Desktop → PC Wireless → Connect**.
9. Select `CollegeWiFi`, enter the password and connect.
10. Repeat for Laptop1.
11. Set the PC and laptops to DHCP under **Desktop → IP Configuration**.
12. Verify connectivity from Laptop0:
```bash
ping 192.168.0.100
ping 192.168.0.102
ping 192.168.0.1
```

## Example DHCP Addresses
| Device | Example IP |
|---|---|
| PC0 | 192.168.0.100 |
| Laptop0 | 192.168.0.101 |
| Laptop1 | 192.168.0.102 |

The actual addresses may differ depending on DHCP allocation.

## Result
A Wireless LAN was successfully configured using the WRT300N router. Wired and wireless devices connected to the same network, obtained IP addresses through DHCP and communicated using Ping.
