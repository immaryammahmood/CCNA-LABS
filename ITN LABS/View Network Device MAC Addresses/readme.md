# View Network Device MAC Addresses

<h3>Overview</h3>
This Cisco Packet Tracer lab demonstrates how to configure basic network connectivity and examine Ethernet MAC addresses on network devices. The lab focuses on identifying, analyzing, and interpreting MAC addresses on a Cisco switch and a Windows PC using Cisco IOS and Windows networking commands.

<h3>Objectives</h3>

- Configure basic network settings on a Cisco switch.
- Configure IPv4 addressing on a PC.
- Verify network connectivity using ICMP.
- Display and analyze MAC addresses.
- Identify the Organizationally Unique Identifier (OUI) and serial number portions of MAC addresses.
- Examine the switch MAC address table.
- Understand how Layer 2 and Layer 3 address mappings work.

<h3>Network Topology</h3>

- **1 × Cisco Catalyst 2960 Switch**
- **1 × PC**
- Console cable
- Ethernet cable

<h3>IP Addressing</h3>

| Device | Interface | IP Address | Subnet Mask |
|---------|-----------|------------|-------------|
| S1 | VLAN 1 | 192.168.1.2 | 255.255.255.0 |
| PC-A | NIC | 192.168.1.3 | 255.255.255.0 |





<h3>Technologies Used</h3>

- Cisco Packet Tracer
- Cisco IOS CLI
- Ethernet
- IPv4
- ICMP (Ping)
- ARP
- MAC Address Table

<h3>Configuration Tasks</h3>

<h3>Part 1 – Basic Configuration</h3>

- Configure the PC IPv4 address.
- Configure the switch hostname.
- Disable DNS lookup.
- Configure the VLAN 1 interface.
- Verify connectivity using `ping`.

  <p align="center"><img width="596" height="341" alt="image" src="https://github.com/user-attachments/assets/0bb8c1f2-ebc3-4cc9-8051-74ef3df7e382"/></p>

<h3>Part 2 – MAC Address Analysis</h3>
Use the following commands:

### Windows
```bash
ipconfig /all
```
  <p align="center"><img width="622" height="236" alt="image" src="https://github.com/user-attachments/assets/f7d25a80-4bd0-404a-adaf-14c86fdc0542" /></p>


### Cisco IOS
```bash
show interfaces vlan 1
show arp
show mac address-table
```

  <p align="center"><img width="602" height="448" alt="image" src="https://github.com/user-attachments/assets/e1a6558e-cb73-4e14-8d3e-659c556c5029" /></p>



## Commands Used

```bash
enable
configure terminal
hostname S1
no ip domain-lookup

interface vlan 1
ip address 192.168.1.2 255.255.255.0
no shutdown

show interfaces vlan 1
show arp
show mac address-table
```
