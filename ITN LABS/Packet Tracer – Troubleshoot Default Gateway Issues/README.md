# Packet Tracer – Troubleshoot Default Gateway Issues

### Overview

This Cisco Packet Tracer lab focuses on troubleshooting connectivity problems caused by incorrect or missing default gateway configurations. The activity follows a systematic troubleshooting methodology: verify network documentation, isolate problems, determine solutions, implement changes, verify connectivity, and document the results.

### Objectives

- Verify network documentation and identify connectivity issues.
- Complete the missing default gateway information.
- Test local and end-to-end connectivity.
- Identify addressing and default gateway problems.
- Implement appropriate solutions.
- Verify that connectivity issues have been resolved.
- Document the troubleshooting process.

### Network Addressing

| Device | Interface | IP Address     | Subnet Mask     | Default Gateway |
|--------|-----------|----------------|-----------------|-----------------|
| R1     | G0/0      | 192.168.10.1   | 255.255.255.0   | N/A             |
| R1     | G0/1      | 192.168.11.1   | 255.255.255.0   | N/A             |
| S1     | VLAN 1    | 192.168.10.2   | 255.255.255.0   | —               |
| S2     | VLAN 1    | 192.168.11.2   | 255.255.255.0   | —               |
| PC1    | NIC       | 192.168.10.10  | 255.255.255.0   | —               |
| PC2    | NIC       | 192.168.10.11  | 255.255.255.0   | —               |
| PC3    | NIC       | 192.168.11.10  | 255.255.255.0   | —               |
| PC4    | NIC       | 192.168.11.11  | 255.255.255.0   | —               |

### Troubleshooting Methodology

The lab uses a structured troubleshooting approach:

1. Verify the network documentation.
2. Test connectivity to isolate the problem.
3. Determine the likely cause.
4. Identify an appropriate solution.
5. Implement one solution at a time.
6. Retest connectivity.
7. Document the results.

### Key Concepts

### Default Gateway

A default gateway allows a host to communicate with devices located on a different network. For a host, the default gateway is normally the IP address of the router interface connected to its local network.

For this topology:

- **Devices on 192.168.10.0/24** use **192.168.10.1** as their default gateway.
- **Devices on 192.168.11.0/24** use **192.168.11.1** as their default gateway.

### Troubleshooting Commands

The following commands can be used during the troubleshooting process:

### ipconfig

Displays the PC's IP address, subnet mask, and default gateway.

### ping

Tests connectivity to another device.

**Examples:**

```
ping 192.168.10.11
ping 192.168.10.1
ping 192.168.11.11
```

### Troubleshooting Approach

The lab begins by checking local connectivity before testing communication between different networks. This helps isolate local problems before investigating remote connectivity.

For example, if PC1 cannot communicate with PC2, both devices are on the same network, so the problem should first be investigated on PC1, PC2, or their local connection rather than assuming that the router is responsible.

After local connectivity is confirmed, end-to-end tests can be performed between devices on different networks, such as PC1 and PC4.

### Verification

After implementing each identified solution:

1. Repeat the connectivity test that originally exposed the problem.
2. Confirm that communication is successful.
3. Continue troubleshooting any remaining connectivity issues.
4. Test communication between both local and remote networks.
5. Document the completed troubleshooting process.
