# View Wired and Wireless NIC Information

<h3>Overview</h3>

This lab focuses on identifying and managing wired and wireless Network Interface Cards (NICs) on a Windows computer.

The activity demonstrates how to view network adapter information, check connection status, identify wireless and Ethernet interfaces, and use Windows networking tools to troubleshoot connectivity issues.

<h3>Objectives</h3>

- Identify wired and wireless network adapters on a PC
- View NIC status and configuration details
- Understand the difference between Ethernet and Wi-Fi connections
- Use Windows network settings to enable and disable adapters
- Analyze network information using system tools

<h3>Tools Used</h3>

| Tool | Purpose |
|---|---|
| Windows Network and Sharing Center | Manage and view network adapters |
| Network Connections | Enable or disable NICs |
| Command Prompt | View network configuration using commands |
| ipconfig /all | Display detailed adapter information |
| Network Status Settings | Check connectivity and troubleshoot issues |


<h3>Network Interfaces Examined</h3>

| Interface Type | Description |
|---|---|
| Wired NIC (Ethernet) | Provides network connectivity through a physical Ethernet cable |
| Wireless NIC (Wi-Fi) | Provides wireless connectivity through available Wi-Fi networks |


<h3>Lab Procedure</h3>

1. Opened Windows Network and Sharing Center to view available network adapters.

2. Identified the available network interfaces, including:
   - Wired Ethernet NIC
   - Wireless Wi-Fi NIC

3. Checked wireless adapter information:
   - Viewed connected SSID
   - Checked connection speed
   - Viewed MAC address and IP configuration
   - Verified wireless security settings

4. Used the `ipconfig /all` command to examine detailed network information:
   - IP address
   - MAC address
   - Default gateway
   - DNS server details
   - DHCP information

5. Checked the Ethernet adapter status and compared wired network information with the command-line output.

6. Enabled and disabled network adapters to observe changes in network connectivity.

7. Used Windows system tray network icons to identify:
   - Active network connections
   - Disabled adapters
   - Network connectivity problems

8. Performed basic troubleshooting by checking adapter status and restoring network connectivity.

