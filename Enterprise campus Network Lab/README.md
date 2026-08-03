# Enterprise Campus Network with Dual ISP Connectivity

## 📌 Project Overview

This project demonstrates the design and implementation of a highly available three-tier enterprise campus network using Cisco devices in GNS3.

The network consists of an Access Layer, Distribution Layer, Core Layer, and dual ISP edge connectivity. It incorporates dynamic routing, gateway redundancy, DHCP, NAT/PAT, Layer 2 redundancy, and Internet access, simulating a real-world enterprise environment.

The project focuses on enterprise networking concepts including VLAN segmentation, Inter-VLAN routing, OSPF, HSRP, EtherChannel, eBGP, and NAT Overload.

---

# 🏗️ Network Architecture

The network is divided into four layers.

### Access Layer

- SW1
- SW2

Functions:
- End-user connectivity
- VLAN assignment
- Access ports
- 802.1Q trunk uplinks

---

### Distribution Layer

- DSW1
- DSW2

Functions:
- Layer 3 Switching
- Inter-VLAN Routing
- HSRP Default Gateway Redundancy
- DHCP Server
- OSPF Routing
- LACP EtherChannel
- Rapid PVST Root Bridge

---

### Core Layer

- R1
- R2

Functions:
- Enterprise Core Routing
- OSPF Backbone
- eBGP Connectivity
- NAT/PAT
- Internet Edge

---

### ISP Layer

- R3 (ISP1)
- R4 (ISP2)

Functions:
- Internet Service Providers
- eBGP Peering

---

### Internet

- R5

Functions:
- Simulated Internet
- Loopback representing public IP (8.8.8.8)

---

# 🖥️ Topology

(Add topology image here)

Example:

```
PCs
 │
SW1 -------- SW2
 │            │
DSW1=======DSW2
 │            │
R1----------R2
 │            │
R3          R4
  \         /
     Internet
```

---

# 🛠️ Technologies Used

- Cisco IOS
- GNS3
- Layer 2 Switching
- Layer 3 Switching
- VLANs
- Inter-VLAN Routing
- Rapid PVST
- EtherChannel (LACP)
- HSRP
- DHCP
- OSPF
- eBGP
- NAT Overload (PAT)
- Static Routing
- ACLs

---

# 🌐 VLAN Design

| VLAN | Department | Network | Default Gateway |
|------|------------|----------------|----------------|
|10|Finance|10.10.10.0/24|10.10.10.1|
|20|HR|10.20.20.0/24|10.20.20.1|
|30|Sales|10.30.30.0/24|10.30.30.1|
|40|IT|10.40.40.0/24|10.40.40.1|

---

# 🌍 WAN Addressing

| Link | Network |
|------|----------------|
|R1 ↔ R2|192.168.12.0/24|
|R1 ↔ DSW1|192.168.13.0/24|
|R1 ↔ DSW2|192.168.14.0/24|
|R2 ↔ DSW1|192.168.23.0/24|
|R2 ↔ DSW2|192.168.24.0/24|
|DSW1 ↔ DSW2 (Port-Channel)|192.168.34.0/24|
|R1 ↔ ISP1|203.0.113.0/24|
|R2 ↔ ISP2|198.51.100.0/24|
|ISP1 ↔ Internet|192.0.2.0/24|
|ISP2 ↔ Internet|192.0.3.0/24|

---

# 🔁 Routing Protocols

### OSPF

Used as the Interior Gateway Protocol (IGP).

Responsibilities:

- Internal Routing
- Inter-VLAN Connectivity
- Route Advertisement
- Default Route Learning

---

### eBGP

Used between the Enterprise Edge and ISPs.

Enterprise AS : **100**

ISP1 AS : **300**

ISP2 AS : **400**

Internet AS : **65010**

Responsibilities:

- Internet Route Exchange
- External Route Advertisement

---

# 🔐 NAT/PAT

PAT (Port Address Translation) is configured on R1.

Functions:

- Translate private IP addresses into a public IP
- Allow internal users to access external networks
- Conserve public IPv4 addresses

---

# ⚙️ High Availability Features

✔ HSRP

Provides gateway redundancy for all VLANs.

Virtual Gateway Example:

```
VLAN10
Virtual IP : 10.10.10.1
```

---

✔ EtherChannel

LACP-based Port-Channel between DSW1 and DSW2 provides:

- Link Redundancy
- Increased Bandwidth
- Faster Convergence

---

✔ Rapid PVST

Used to prevent Layer 2 loops.

DSW1 configured as Root Bridge.

DSW2 configured as Secondary Root.

---

# 📋 Services Implemented

- DHCP
- HSRP
- NAT/PAT
- OSPF
- eBGP
- EtherChannel
- Rapid PVST

---

# ✅ Verification

The following features were successfully verified.

- DHCP address allocation
- HSRP Active/Standby operation
- EtherChannel formation
- OSPF Neighbor adjacency
- BGP Neighbor adjacency
- NAT translations
- End-to-End Connectivity
- Internet Connectivity (PC1 → 8.8.8.8)

---

# 🧪 Sample Verification Commands

```bash
show ip route

show ip ospf neighbor

show standby brief

show etherchannel summary

show ip bgp summary

show ip nat translations

show ip nat statistics

show interfaces trunk
```


# 🎯 Skills Demonstrated

- Enterprise Network Design
- Cisco Switching
- Cisco Routing
- Layer 2 Redundancy
- Layer 3 Routing
- High Availability
- Dynamic Routing
- Enterprise Edge Connectivity
- NAT/PAT
- Network Troubleshooting

---

# 🚀 Future Enhancements

Planned improvements include:

- iBGP between Enterprise Routers
- HSRP Interface Tracking
- BGP Local Preference
- AS Path Prepending
- Route Maps
- Prefix Lists
- ISP Failover
- Floating Static Routes
- IP SLA Tracking

---

# 👨‍💻 Author

**Madhuvani**

Aspiring Network Engineer | CCNA | Azure AZ-900 | Google Cybersecurity
