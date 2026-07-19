# Packet Tracer - Implement Basic Connectivity

## Lab Overview

This lab introduces foundational network device configuration and connectivity verification using Cisco Packet Tracer. It bridges the gap between basic networking concepts and practical hands-on implementation by having you configure switches and PCs to communicate in a local network.

## What This Lab Does

The lab simulates a small corporate network environment with:
- 2 Switches (S1 and S2) that act as network infrastructure devices
- 2 PCs (PC1 and PC2) that serve as end-user devices
- A single subnet (192.168.1.0/24) connecting all devices

You'll move through three stages of configuration:
1. Configure the switches with hostnames, security settings, and management interfaces
2. Configure the PCs with IP addresses for network communication
3. Verify connectivity between all devices to ensure the network functions correctly

## Key Learning Outcomes

### Network Device Management
- Hostname Configuration: Understand how to identify devices on a network
- Access Control: Learn why console passwords (cisco) and privileged EXEC passwords (class) are critical for device security
- MOTD Banners: Implement legal warnings to protect network infrastructure from unauthorized access
- Configuration Persistence: Understand the difference between RAM (running config) and NVRAM (saved config), and why `copy running-config startup-config` is essential

### IP Addressing & Switch Management
- Switch Management Interfaces: Learn that switches are Layer 2 devices that work with MAC addresses, but require IP addresses for management and monitoring purposes
- VLAN 1 Configuration: Understand that switches have a management interface (typically VLAN 1) separate from port forwarding functions
- Interface States: Learn the importance of the `no shutdown` command in enabling interfaces and why interface status (up/down) matters

### Network Connectivity Verification
- Ping Command: Use ping to test Layer 3 (IP) connectivity between devices
- Troubleshooting Basics: Understand that connectivity failures indicate configuration errors that need correction
- Show Commands: Use `show ip interface brief` and `show running-config` to verify your configurations

## Network Topology

```
┌─────────────────────────────────────────┐
│     192.168.1.0/24 Network              │
│                                         │
│  S1 (192.168.1.253)  S2 (192.168.1.254)│
│       Switch              Switch        │
│          │                  │           │
│          └──────────────────┘           │
│             (LAN Connection)            │
│          │                  │           │
│       PC1                 PC2           │
│  (192.168.1.1)      (192.168.1.2)      │
│                                         │
└─────────────────────────────────────────┘
```

## Skills Practiced

- CLI Navigation: Entering configuration mode, using context-sensitive help
- Device Naming: Setting hostnames for network identification
- Security Implementation: Configuring authentication mechanisms
- IP Configuration: Assigning addresses to network interfaces
- Verification Commands: Using show commands to validate configurations
- Troubleshooting: Using ping to diagnose connectivity issues
- Configuration Management: Saving configurations to persistent storage

## Real-World Context

This lab demonstrates why network administrators need to:
1. Secure access to network devices (passwords & banners)
2. Configure device management interfaces for remote monitoring and administration
3. Ensure end-to-end connectivity across the network
4. Verify configurations before deploying them to production networks

---

**Lab Type**: Hands-on Configuration & Verification  
**Difficulty**: Beginner
