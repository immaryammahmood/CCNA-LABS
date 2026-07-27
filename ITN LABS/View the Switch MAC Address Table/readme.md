# View the Switch MAC Address Table

<h3>Devices Used</h3>

- 2 × Cisco Catalyst 2960 Switches
- 2 × PCs
- Console Cables
- Ethernet Cables

## Topology

```
PC-A ─── S1 ─── S2 ─── PC-B
```

<p align="center"><img width="625" height="245" alt="image" src="https://github.com/user-attachments/assets/7ae3660f-1f9f-4661-8056-afb3ebf268e0" /></p>


<h3>IP Addressing</h3>

| Device | Interface | IP Address |
|--------|-----------|------------|
| PC-A | NIC | 192.168.1.1 |
| PC-B | NIC | 192.168.1.2 |
| S1 | VLAN 1 | 192.168.1.11 |
| S2 | VLAN 1 | 192.168.1.12 |

<h3>Configuration</h3>

- Configure hostnames.
- Configure VLAN 1 management IP addresses.
- Configure console and VTY passwords.
- Configure the enable secret.
- Save the configuration.

<h3>Verification</h3>

- Record PC MAC addresses.
- Record switch interface MAC addresses.
- Display the MAC address table.
- Clear the dynamic MAC address table.
- Generate traffic using `ping`.
- Observe the updated MAC address table and ARP cache.

<h3>Commands Used</h3>

<h3>Windows</h3>

```cmd
ipconfig /all
arp -a
ping <IP Address>
```

<h3>Cisco IOS</h3>

```cisco
enable
configure terminal
hostname
interface vlan 1
ip address
no shutdown
line console 0
password cisco
login
line vty 0 15
password cisco
login
enable secret class
show interface fa0/1
show mac address-table
clear mac address-table dynamic
copy running-config startup-config
```
