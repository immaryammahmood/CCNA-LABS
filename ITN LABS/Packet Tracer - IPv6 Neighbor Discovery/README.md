# Packet Tracer - IPv6 Neighbor Discovery

### Overview

This lab explores the IPv6 Neighbor Discovery (ND) process and how devices use the NDP (Neighbor Discovery Protocol) to determine MAC addresses of destination devices on local and remote networks. Understanding ND is critical for IPv6 communication, as it performs the same essential function as ARP in IPv4 networks.

### Learning Objectives

- Understand how IPv6 Neighbor Discovery works on local networks
- Observe and analyze NDP (Neighbor Discovery Protocol) messages in Packet Tracer simulation mode
- Compare ND behavior for local vs. remote network communication
- Analyze router involvement in multi-LAN IPv6 communication
- Examine router neighbor tables and MAC address learning

### Network Topology

### Addressing Table

| Device | Interface | IPv6 Address / Prefix | Default Gateway |
|--------|-----------|----------------------|-----------------|
| RTA    | G0/0/0    | 2001:db8:acad:1::1/64| N/A             |
| RTA    | G0/0/1    | 2001:db8:acad:2::1/64| N/A             |
| PCA1   | NIC       | 2001:db8:acad:1::a/64| fe80::1         |
| PCA2   | NIC       | 2001:db8:acad:1::b/64| fe80::1         |
| PCB1   | NIC       | 2001:db8:acad:2::a/64| fe80::1         |

### Network Configuration

- **Network 1 (2001:db8:acad:1::/64)**: RTA G0/0/0, PCA1, PCA2
- **Network 2 (2001:db8:acad:2::/64)**: RTA G0/0/1, PCB1
- **Router**: RTA (connects both LANs)

### Lab Structure

### Part 1: IPv6 Neighbor Discovery - Local Network

Observe the Neighbor Discovery process when hosts communicate on the **same network segment**.

**Key Steps:**
1. Clear any existing IPv6 neighbor entries on the router
2. Switch to Simulation mode with ICMPv6 and NDP filters enabled
3. Ping a local host (PCA1 → PCA2) to observe ND process
4. Analyze PDU details at each hop
5. Repeat the ping to observe cached behavior

**What You'll Observe:**
- ICMPv6 echo requests sent without Layer 2 information initially
- NDP messages performing address resolution
- Multicast MAC addresses used during discovery
- MAC address caching on subsequent pings

### Part 2: IPv6 Neighbor Discovery - Remote Network

Observe the Neighbor Discovery process when hosts communicate across **different network segments**.

**Key Steps:**
1. Reset simulation and clear neighbor tables
2. Ping a remote host on different LAN (PCA1 → PCB1)
3. Observe router involvement in ND process
4. Analyze address resolution at each interface
5. Examine router neighbor table entries

**What You'll Observe:**
- Multiple ND exchanges across different network boundaries
- Router performing separate ND for each interface
- Link-local address resolution followed by global address resolution
- Router's role in forwarding and address learning

## Important Concepts

### Neighbor Discovery Protocol (NDP)

NDP is responsible for:
- Determining MAC addresses of IPv6 devices (like ARP for IPv4)
- Router discovery
- Address auto-configuration
- IPv6 prefix discovery

### Key Differences from IPv4 ARP

| Aspect | IPv4 ARP | IPv6 ND |
|--------|----------|---------|
| Multicast Address | 255.255.255.255 (broadcast) | ff02::1 (multicast) |
| Message Type | Request/Reply | Neighbor Solicitation/Advertisement |
| Scope | Local subnet | Can be extended |
| Auto-configuration | Manual | Auto-configuration built-in |

### Multicast MAC Addresses

IPv6 ND uses special multicast MAC addresses (Layer 2) even though the devices may not know each other's addresses at Layer 3.

## Simulation Mode Setup

1. Click **Simulation** button (lower right corner)
2. Set **Show All/None** until "Event List Filters – Visible Events" shows **None**
3. Click **Edit Filters** → **IPv6** tab
4. Check **ICMPv6** and **NDP** boxes
5. Close and observe filtered events

## Commands Reference

### Router Commands

```
show ipv6 neighbors        # Display IPv6 neighbor table (MAC to IPv6 mapping)
clear ipv6 neighbors       # Clear all entries from neighbor table
show ipv6 neighbors [addr] # Show specific neighbor entry
```

### Host Commands

```
ping -n 1 <ipv6-address>   # Send single ping to IPv6 address
```


