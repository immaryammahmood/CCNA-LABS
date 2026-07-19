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

