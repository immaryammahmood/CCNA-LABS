# Packet Tracer Lab: Connecting Wired and Wireless Networks

<h3>Overview</h3>

This Cisco Packet Tracer lab focuses on identifying network devices, selecting the correct cables, and establishing physical connections between wired and wireless network components.

<h3>Devices Used</h3>

| Device | Model / Type | Purpose |
|---|---|---|
| Router0 | Cisco 2621XM | Main router connecting LAN, WAN, and ISP cloud |
| Router1 | Cisco 2621XM | Router connecting secondary LAN network |
| Switch | Switch-PT | Provides wired LAN connectivity |
| Wireless Router | Wireless Router-PT | Provides wireless network access |
| Cloud | Cloud-PT | Simulates ISP/internet connection |
| Cable Modem | Cable Modem-PT | Provides cable internet connectivity |

<h3>Router Modules Used</h3>

**Router0**

**Router Model:** Cisco 2621XM

**Installed Modules:**

- **NM-1FE-FX**
- **WIC-2T**

**Router1**

**Router Model:** Cisco 2621XM

**Installed Modules:**

- **NM-1FE-FX**
- **WIC-2T**

<h3>Network Connections and Cable Selection</h3>

| # | Connection | Cable Used | Purpose |
|---|---|---|---|
| 1 | Router0 FastEthernet → Cloud Ethernet | Copper Straight-Through | Connects Router0 to ISP Cloud |
| 2 | Cloud Coaxial Port → Cable Modem Coaxial Port | Coaxial Cable | Connects ISP cloud to cable modem |
| 3 | Router0 Serial 0/0/0 → Router1 Serial 0/0 | Serial DCE/DTE Cable | Creates WAN connection |
| 4 | Router0 FastEthernet → netacad.pka Server FastEthernet | Copper Cross-Over | Connects router directly to server |
| 5 | Router0 Console Port → Configuration Terminal RS232 | Console Cable | Provides router configuration access |
| 6 | Router1 FastEthernet → Switch-PT FastEthernet | Copper Straight-Through | Connects router to wired LAN |
| 7 | Cable Modem → Wireless Router Internet Port | Copper Straight-Through | Provides internet access |
| 8 | Wireless Router Ethernet Port → Family PC | Copper Straight-Through | Connects PC to wireless router |
<br>

<h3>Wired Network Connections</h3>




| # | Connection | Cable Used | Purpose |
|---|---|---|---|
| 1 | Router0 → Cloud | Copper Straight-Through | Ethernet connection |
| 2 | Router0 → Router1 | Serial DCE/DTE Cable | WAN connection |
| 3 | Router0 → netacad.pka Server | Copper Cross-Over | Direct Ethernet connection |
| 4 | Router1 → Switch-PT | Copper Straight-Through | LAN connection |
| 5 | Router0 → Configuration Terminal | Console Cable | Device management |
| 6 | Cloud → Cable Modem | Coaxial Cable | ISP connection |

<br>

<h3>Wireless Network Connections</h3>

| # | Connection | Connection Type | Cable / Medium | Purpose |
|---|---|---|---|---|
| 1 | Cable Modem → Wireless Router Internet Port | WAN Connection | Copper Straight-Through | Internet access |
| 2 | Wireless Router → Family PC | LAN Connection | Copper Straight-Through | Wired client connection |
| 3 | Wireless Router → Wireless Devices | Wireless Connection | Wi-Fi | Wireless access |

<br>

<h3>Topology</h3>

<div align="center">
  <img width="679" height="423" alt="image" src="https://github.com/user-attachments/assets/f7da6d0a-b215-4050-9ae7-b06ae01aa7e8" />
</div>
