<h1>Wireshark - Examine Ethernet Frames</h1>

Packet-level analysis of Ethernet II frames using Wireshark, covering both local (default gateway) and remote (internet host) traffic. The goal is to break down the Ethernet II header, correlate it with the ARP and ICMP exchanges it carries, and confirm how MAC/IP addressing behaves across a router hop.

<h2>Topology</h2>




PC --- Router (Default Gateway) --- Internet

- Host: 192.168.1.147 / 255.255.255.0
- Default Gateway: 192.168.1.1
- NIC: Intel 82579LM Gigabit, MAC F0-1F-AF-50-FD-C8

<h2>Ethernet II Frame Structure</h2>

<p align="center">

| Field | Length | Notes |
|---|---|---|
| Preamble | 8 Bytes | Synchronization bits, handled by NIC hardware, not visible in capture |
| Destination Address | 6 Bytes | Broadcast or unicast MAC |
| Source Address | 6 Bytes | Always unicast MAC |
| Frame Type | 2 Bytes | 0x0800 = IPv4, 0x0806 = ARP |
| Data | 46-1500 Bytes | Encapsulated upper-layer protocol (ARP, IP/ICMP, etc.) |
| FCS | 4 Bytes | Frame Check Sequence, computed by sender, verified by receiver |

</p>

<h2>Procedure</h2>

1. Check host network config with `ipconfig /all` to note the local IP and default gateway.

<p align="center">
  <img width="931" height="425" alt="image" src="https://github.com/user-attachments/assets/6d19eb1c-15bd-4e28-9418-8dadb0f91663" />
</p>

<br>

2. Open Wireshark on the active NIC and start capturing.
3. Apply a display filter for `arp or icmp` to isolate the relevant traffic.

<br>

<p align="center">
<img width="861" height="533" alt="image" src="https://github.com/user-attachments/assets/1cffd4c8-af44-412e-94ce-71abddbb8c43" />
</p>

<br>


4. Ping the default gateway from a command prompt, then stop the capture.
5. Inspect the first ARP request/reply pair, then the ICMP echo request/reply pair, expanding the Ethernet II layer in the Packet Details pane to read source/destination MAC, EtherType, and payload.
6. Repeat the capture against a remote host (`ping www.cisco.com`) with a clean ICMP-only filter, and compare addressing behavior against the local capture.

<h2>Observed Behavior</h2>

| Exchange | Source MAC | Destination MAC | Frame Type |
|---|---|---|---|
| ARP Request | Dell_50:fd:c8 (host) | Broadcast (ff:ff:ff:ff:ff:ff) | 0x0806 |
| ARP Reply | Netgear_99:c5:72 (gateway) | Dell_50:fd:c8 (host) | 0x0806 |
| ICMP Echo | Host | Gateway | 0x0800 |

<h3>Key takeaways from the capture:</h3>

- The host has no MAC-to-IP mapping for the gateway before the ping, so it broadcasts an ARP request to every device on the segment; only the owner of 192.168.1.1 replies.
- Once the gateway's MAC is resolved, all ICMP echo requests/replies use unicast addressing at Layer 2.
- For the remote host capture, the destination MAC in every frame stays the gateway's MAC (the frame only needs to reach the next hop), while the destination IP address in the data field changes to the remote host's actual IP. This is the normal Layer 2 vs Layer 3 addressing split at a router boundary.
- The OUI (first 3 bytes / 6 hex digits) of a MAC address identifies the NIC vendor; the remaining 3 bytes are the vendor-assigned serial number.
