# IP Addressing Table

## Loopback Interfaces

| Device | Interface | IP Address | Purpose |
|----------|-----------|----------------|----------------|
| R1 | Loopback0 | 1.1.1.1/32 | Router ID |
| R2 | Loopback0 | 2.2.2.2/32 | Router ID |
| R3 | Loopback0 | 3.3.3.3/32 | ISP1 Router ID |
| R4 | Loopback0 | 4.4.4.4/32 | ISP2 Router ID |
| R5 (Internet) | Loopback0 | 8.8.8.8/32 | Simulated Internet |

---

# VLAN Addressing

| VLAN | Department | Network | HSRP Virtual IP |
|------|------------|----------------|----------------|
|10|Finance|10.10.10.0/24|10.10.10.1|
|20|HR|10.20.20.0/24|10.20.20.1|
|30|Sales|10.30.30.0/24|10.30.30.1|
|40|IT|10.40.40.0/24|10.40.40.1|

---

# Distribution Switch SVIs

## DSW1

| Interface | IP Address |
|-----------|----------------|
| Vlan10 | 10.10.10.2/24 |
| Vlan20 | 10.20.20.2/24 |
| Vlan30 | 10.30.30.2/24 |
| Vlan40 | 10.40.40.2/24 |

## DSW2

| Interface | IP Address |
|-----------|----------------|
| Vlan10 | 10.10.10.3/24 |
| Vlan20 | 10.20.20.3/24 |
| Vlan30 | 10.30.30.3/24 |
| Vlan40 | 10.40.40.3/24 |

---

# Point-to-Point Links

| Link | Device A | Device B | Network |
|------|----------|----------|----------------|
| R1 ↔ R2 | 192.168.12.1 | 192.168.12.2 | 192.168.12.0/24 |
| R1 ↔ DSW1 | 192.168.13.1 | 192.168.13.2 | 192.168.13.0/24 |
| R1 ↔ DSW2 | 192.168.14.1 | 192.168.14.2 | 192.168.14.0/24 |
| R2 ↔ DSW1 | 192.168.23.1 | 192.168.23.2 | 192.168.23.0/24 |
| R2 ↔ DSW2 | 192.168.24.1 | 192.168.24.2 | 192.168.24.0/24 |
| DSW1 ↔ DSW2 (Port-Channel1) | 192.168.34.1 | 192.168.34.2 | 192.168.34.0/24 |

---

# ISP Links

| Link | Network |
|------|----------------|
| R1 ↔ R3 | 203.0.113.1 ↔ 203.0.113.2 |
| R2 ↔ R4 | 198.51.100.1 ↔ 198.51.100.2 |
| R3 ↔ Internet | 192.0.2.1 ↔ 192.0.2.2 |
| R4 ↔ Internet | 192.0.3.1 ↔ 192.0.3.2 |

---

# DHCP Pools

| VLAN | DHCP Scope | Default Gateway |
|------|--------------------------|----------------|
|10|10.10.10.21 - 10.10.10.254|10.10.10.1|
|20|10.20.20.21 - 10.20.20.254|10.20.20.1|
|30|10.30.30.21 - 10.30.30.254|10.30.30.1|
|40|10.40.40.21 - 10.40.40.254|10.40.40.1|

---

# BGP Autonomous System Numbers

| Device | AS Number |
|---------|-----------|
| Enterprise (R1 & R2) | 100 |
| ISP1 (R3) | 300 |
| ISP2 (R4) | 400 |
| Internet (R5) | 65010 |

---

# Default Gateways

| Device | Default Gateway |
|---------|----------------|
| PC1 | 10.10.10.1 |
| PC2 | 10.20.20.1 |
| PC3 | 10.30.30.1 |
| PC4 | 10.40.40.1 |

---

# Internet Connectivity Flow

```
PC1
 ↓
SW1
 ↓
DSW1 (HSRP Active Gateway)
 ↓
R1 (NAT/PAT)
 ↓
R3 (ISP1)
 ↓
R5 (Internet)
```
