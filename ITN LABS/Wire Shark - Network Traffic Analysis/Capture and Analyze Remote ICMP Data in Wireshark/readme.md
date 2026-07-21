# Remote Host ICMP Traffic Analysis Using Wireshark

### Overview

Remote ICMP traffic was analyzed by sending ping requests to Internet hosts such as:
- www.google.com
- www.cisco.com
- www.yahoo.com

By sending ping requests to remote websites, the captured packets were analyzed to observe DNS resolution, IP addressing, Ethernet frames, and the role of the default gateway in remote communication.

You will ping remote hosts (hosts not on the LAN) and examine the generated data from those
pings.

---

### Lab Environment

| Category | Details |
|----------|---------|
| **Tools Used** | Wireshark, Windows Command Prompt |
| **Network Environment** | Local Area Network (LAN) |
| **Protocols Analyzed** | ICMP, IPv4, Ethernet II, ARP |

---

## Check Network Information

```bash
ipconfig /all
````

<br>

- Start capturing data on the interface
  With the capture active, ping the following three website URLs from a Windows command prompt:
  Open a Windows command prompt
  1) www.yahoo.com
  2) www.cisco.com
  3) www.google.com
 
- Examining and analyzing the data from the remote hosts
  1) IP Addresses
  2) Mac Addressess
 
