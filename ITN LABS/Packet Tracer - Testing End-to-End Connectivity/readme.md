# End-to-End Connectivity Testing

## Overview

This lab verifies end-to-end connectivity between two PCs connected through two Cisco Catalyst 2960 switches. Basic switch management is configured, and ICMP echo requests are used to validate communication across the network.



<h3>Topology</h3>

```
PC-A ─── S1 ───────── S2 ─── PC-B
        Fa0/6      Fa0/1 Fa0/1      Fa0/18
```
<p align="center"><img width="490" height="393" alt="image" src="https://github.com/user-attachments/assets/bf3ec768-366d-42e9-aeec-268e0e2030f0" /></p>


---

<h3>Devices Used</h3>

- 2 × Cisco Catalyst 2960 Switches
  - S1
  - S2
- 2 × PCs
  - PC-A
  - PC-B
- Copper Straight-Through Cables

---

<h3>IP Addressing</h3>

| Device | Interface | IP Address |
|----------|-----------|------------|
| PC-A | Fa0 | 192.168.1.10/24 |
| S1 | VLAN 1 | 192.168.1.2/24 |
| S2 | VLAN 1 | 192.168.1.3/24 |
| PC-B | Fa0 | 192.168.1.11/24 |

---

<h3>Configuration</h3>

- Configure hostnames on both switches.
- Assign management IP addresses to VLAN 1.
- Enable VLAN 1 using `no shutdown`.
- Configure console and VTY passwords.
- Configure the enable secret.
- Save the running configuration.
- Configure static IP addresses on both PCs.

---

<h3>Connectivity Tests</h3>

Verify connectivity by performing the following ping tests:

- PC-A → S1
- PC-A → S2
- PC-A → PC-B
- PC-B → S2
- PC-B → S1
- PC-B → PC-A

Verify interface status on both switches and ensure all links are operational.

---

<h3>Commands Used</h3>

<h3>Windows</h3>

```cmd
ipconfig
ping <IP Address>
```

<h3>Cisco IOS</h3>

```cisco
enable
configure terminal

hostname <hostname>

interface vlan 1
ip address <ip-address> <subnet-mask>
no shutdown

line console 0
password cisco
login

line vty 0 15
password cisco
login

enable secret class

show ip interface brief
show running-config
show interfaces status
show cdp neighbors

copy running-config startup-config
```
