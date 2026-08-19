# Packet Tracer — Connect a Router to a LAN

Summary
- Configure router interfaces per the addressing table, verify interface and routing information, and test end-to-end connectivity between PCs.

Objectives
- Part 1: Display router/interface information using show commands.
- Part 2: Configure router Ethernet and Serial interfaces with provided addresses and descriptions.
- Part 3: Verify configuration and test connectivity.

Equipment / Topology
- 2 Routers (R1, R2)
- 2 Switches (S1, S2)
- 4 PCs (PC1..PC4)
- Serial connection between R1 and R2 (S0/0/0)

Addressing Table
Device | Interface | IP Address | Subnet Mask | Default Gateway
---|---:|---|---|---
R1 | G0/0 | 192.168.10.1 | 255.255.255.0 | N/A
R1 | G0/1 | 192.168.11.1 | 255.255.255.0 | N/A
R1 | S0/0/0 (DCE) | 209.165.200.225 | 255.255.255.252 | N/A
R2 | G0/0 | 10.1.1.1 | 255.255.255.0 | N/A
R2 | G0/1 | 10.1.2.1 | 255.255.255.0 | N/A
R2 | S0/0/0 | 209.165.200.226 | 255.255.255.252 | N/A
PC1 | NIC | 192.168.10.10 | 255.255.255.0 | 192.168.10.1
PC2 | NIC | 192.168.11.10 | 255.255.255.0 | 192.168.11.1
PC3 | NIC | 10.1.1.10 | 255.255.255.0 | 10.1.1.1
PC4 | NIC | 10.1.2.10 | 255.255.255.0 | 10.1.2.1

Step-by-step (commands and actions only)

Part 1 — Display router information
1. Open the router CLI (use the console or CLI tab in Packet Tracer).
2. Useful show commands:
   - show interfaces
   - show interfaces serial0/0/0
   - show interfaces gigabitEthernet0/0
   - show ip interface brief
   - show ip route

Part 2 — Configure interfaces
1. On R1: configure Gi0/0
   - configure terminal
   - interface gigabitEthernet 0/0
   - ip address 192.168.10.1 255.255.255.0
   - description LAN connection to S1
   - no shutdown
   - end
2. On R1: configure Gi0/1
   - configure terminal
   - interface gigabitEthernet 0/1
   - ip address 192.168.11.1 255.255.255.0
   - description LAN connection to Sx
   - no shutdown
   - end
3. On R1: configure Serial0/0/0 (if not already configured)
   - configure terminal
   - interface serial 0/0/0
   - ip address 209.165.200.225 255.255.255.252
   - description Serial link to R2
   - no shutdown
   - end
4. On R2: configure Gi0/0, Gi0/1, and Serial0/0/0 using the addressing table.
5. Save configs to NVRAM:
   - copy running-config startup-config
   (or) write memory

Part 3 — Verify configuration & test connectivity
1. Quick checks:
   - show ip interface brief
   - show interfaces <interface>
   - show running-config interface <interface>
   - show ip route
2. Ping tests (examples):
   - From R1: ping 192.168.10.10
   - From PC1 CLI: ping 10.1.2.10
   - From R2: ping 192.168.11.10

Optional: Add routes or enable a routing protocol if networks are not reachable
- Example static routes on R1 pointing to R2 via the serial interface:
  - configure terminal
  - ip route 10.1.1.0 255.255.255.0 209.165.200.226
  - ip route 10.1.2.0 255.255.255.0 209.165.200.226

Troubleshooting checklist
- Verify interfaces are not administratively down: show ip interface brief
- Verify serial DCE clocking if applicable: show controllers serial 0/0/0
- Verify routing table entries: show ip route
- Verify interface details (MAC, bandwidth, errors): show interfaces <interface>

End of lab README
