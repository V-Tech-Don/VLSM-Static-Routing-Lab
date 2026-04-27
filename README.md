# VLSM-Static-Routing-Lab
VLSM Static Routing Lab

# 🌐 VLSM Static Routing Lab — Cisco Packet Tracer

## Overview
A multi-router static routing lab built in Cisco Packet Tracer demonstrating 
Variable Length Subnet Masking (VLSM), inter-router connectivity, static route 
configuration, and end-to-end endpoint reachability across four separate LANs.

---

## 🗺️ Network Topology

<img width="1467" height="788" alt="Topology" src="https://github.com/user-attachments/assets/1faaa5cb-a0d0-47cf-ac6c-aab38af15573" />


### Devices Used
| Device | Quantity | Role |
|--------|----------|------|
| Cisco 2911 Router | 4 | Inter-network routing |
| Cisco 2960 Switch | 4 | LAN access layer |
| PC | 3 | End devices |
| Laptop | 3 | End devices |
| Server | 2 | End devices |

---

## 📐 Subnetting Design (VLSM)

The 192.168.7.0/24 address block was divided using VLSM into 4 LAN subnets 
sized appropriately for each segment:

| Subnet | Network | Prefix | Mask | Host Range | Hosts | Assigned To |
|--------|---------|--------|------|------------|-------|-------------|
| 1 | 192.168.7.0 | /25 | 255.255.255.128 | 7.1 – 7.126 | 126 | Router0 LAN |
| 2 | 192.168.7.64 | /27 | 255.255.255.224 | 7.65 – 7.94 | 30 | Router1 LAN |
| 3 | 192.168.7.96 | /28 | 255.255.255.240 | 7.97 – 7.110 | 14 | Router2 LAN |
| 4 | 192.168.7.112 | /29 | 255.255.255.248 | 7.113 – 7.118 | 6 | Router3 LAN |

Point-to-point /30 links used for all inter-router connections:

| Link | Network | Router A | Router B |
|------|---------|----------|----------|
| R0 ↔ R1 | 192.168.1.0/30 | 192.168.1.1 | 192.168.1.2 |
| R0 ↔ R2 | 192.168.2.0/30 | 192.168.2.2 | 192.168.2.1 |
| R1 ↔ R3 | 192.168.1.8/30 | 192.168.1.10 | 192.168.1.9 |
| R2 ↔ R3 | 192.168.1.12/30 | 192.168.1.14 | 192.168.1.13 |

---

## 🔧 Router Interface Configuration

| Router | Interface | IP Address | Mask | Connected To |
|--------|-----------|------------|------|--------------|
| Router0 | Gig0/0 | 192.168.1.1 | /30 | Router1 Gig0/0 |
| Router0 | Gig0/1 | 192.168.2.2 | /30 | Router2 Gig0/0 |
| Router0 | Gig0/2 | 192.168.7.1 | /25 | Switch2 LAN |
| Router1 | Gig0/0 | 192.168.1.2 | /30 | Router0 Gig0/0 |
| Router1 | Gig0/1 | 192.168.1.10 | /30 | Router3 Gig0/0 |
| Router1 | Gig0/2 | 192.168.7.65 | /27 | Switch3 LAN |
| Router2 | Gig0/0 | 192.168.2.1 | /30 | Router0 Gig0/1 |
| Router2 | Gig0/1 | 192.168.1.14 | /30 | Router3 Gig0/1 |
| Router2 | Gig0/2 | 192.168.7.97 | /28 | Switch0 LAN |
| Router3 | Gig0/0 | 192.168.1.9 | /30 | Router1 Gig0/1 |
| Router3 | Gig0/1 | 192.168.1.13 | /30 | Router2 Gig0/1 |
| Router3 | Gig0/2 | 192.168.7.113 | /29 | Switch1 LAN |


---

## 💻 Endpoint Device Configuration

| Device | IP Address | Mask | Gateway | Switch | Router |
|--------|------------|------|---------|--------|--------|
| PC0 | 192.168.7.3 | /25 | 192.168.7.1 | Switch2 | Router0 |
| PC1 | 192.168.7.98 | /28 | 192.168.7.97 | Switch0 | Router2 |
| PC3 | 192.168.7.115 | /29 | 192.168.7.113 | Switch1 | Router3 |
| Laptop0 | 192.168.7.99 | /28 | 192.168.7.97 | Switch0 | Router2 |
| Laptop1 | 192.168.7.66 | /27 | 192.168.7.65 | Switch3 | Router1 |
| Server0 | 192.168.7.2 | /25 | 192.168.7.1 | Switch2 | Router0 |
| Server1 | 192.168.7.114 | /29 | 192.168.7.113 | Switch1 | Router3 |

---

## 🗺️ Static Routes

All routing was configured manually using static routes. No dynamic routing 
protocols (OSPF, EIGRP, RIP) were used.

**Router0 example:**

# 🌐 VLSM Static Routing Lab — Cisco Packet Tracer

## Overview
A multi-router static routing lab built in Cisco Packet Tracer demonstrating 
Variable Length Subnet Masking (VLSM), inter-router connectivity, static route 
configuration, and end-to-end endpoint reachability across four separate LANs.

---

## 🗺️ Network Topology

<img width="1467" height="788" alt="Topology" src="https://github.com/user-attachments/assets/964c25d9-0f61-42b9-a989-4fcbd4c8aa27" />


### Devices Used
| Device | Quantity | Role |
|--------|----------|------|
| Cisco 2911 Router | 4 | Inter-network routing |
| Cisco 2960 Switch | 4 | LAN access layer |
| PC | 3 | End devices |
| Laptop | 3 | End devices |
| Server | 2 | End devices |

---

## 📐 Subnetting Design (VLSM)

The 192.168.7.0/24 address block was divided using VLSM into 4 LAN subnets 
sized appropriately for each segment:

| Subnet | Network | Prefix | Mask | Host Range | Hosts | Assigned To |
|--------|---------|--------|------|------------|-------|-------------|
| 1 | 192.168.7.0 | /25 | 255.255.255.128 | 7.1 – 7.126 | 126 | Router0 LAN |
| 2 | 192.168.7.64 | /27 | 255.255.255.224 | 7.65 – 7.94 | 30 | Router1 LAN |
| 3 | 192.168.7.96 | /28 | 255.255.255.240 | 7.97 – 7.110 | 14 | Router2 LAN |
| 4 | 192.168.7.112 | /29 | 255.255.255.248 | 7.113 – 7.118 | 6 | Router3 LAN |

Point-to-point /30 links used for all inter-router connections:

| Link | Network | Router A | Router B |
|------|---------|----------|----------|
| R0 ↔ R1 | 192.168.1.0/30 | 192.168.1.1 | 192.168.1.2 |
| R0 ↔ R2 | 192.168.2.0/30 | 192.168.2.2 | 192.168.2.1 |
| R1 ↔ R3 | 192.168.1.8/30 | 192.168.1.10 | 192.168.1.9 |
| R2 ↔ R3 | 192.168.1.12/30 | 192.168.1.14 | 192.168.1.13 |

---

## 🔧 Router Interface Configuration

| Router | Interface | IP Address | Mask | Connected To |
|--------|-----------|------------|------|--------------|
| Router0 | Gig0/0 | 192.168.1.1 | /30 | Router1 Gig0/0 |
| Router0 | Gig0/1 | 192.168.2.2 | /30 | Router2 Gig0/0 |
| Router0 | Gig0/2 | 192.168.7.1 | /25 | Switch2 LAN |
| Router1 | Gig0/0 | 192.168.1.2 | /30 | Router0 Gig0/0 |
| Router1 | Gig0/1 | 192.168.1.10 | /30 | Router3 Gig0/0 |
| Router1 | Gig0/2 | 192.168.7.65 | /27 | Switch3 LAN |
| Router2 | Gig0/0 | 192.168.2.1 | /30 | Router0 Gig0/1 |
| Router2 | Gig0/1 | 192.168.1.14 | /30 | Router3 Gig0/1 |
| Router2 | Gig0/2 | 192.168.7.97 | /28 | Switch0 LAN |
| Router3 | Gig0/0 | 192.168.1.9 | /30 | Router1 Gig0/1 |
| Router3 | Gig0/1 | 192.168.1.13 | /30 | Router2 Gig0/1 |
| Router3 | Gig0/2 | 192.168.7.113 | /29 | Switch1 LAN |

---

## 💻 Endpoint Device Configuration

| Device | IP Address | Mask | Gateway | Switch | Router |
|--------|------------|------|---------|--------|--------|
| PC0 | 192.168.7.3 | /25 | 192.168.7.1 | Switch2 | Router0 |
| PC1 | 192.168.7.98 | /28 | 192.168.7.97 | Switch0 | Router2 |
| PC3 | 192.168.7.115 | /29 | 192.168.7.113 | Switch1 | Router3 |
| Laptop0 | 192.168.7.99 | /28 | 192.168.7.97 | Switch0 | Router2 |
| Laptop1 | 192.168.7.66 | /27 | 192.168.7.65 | Switch3 | Router1 |
| Server0 | 192.168.7.2 | /25 | 192.168.7.1 | Switch2 | Router0 |
| Server1 | 192.168.7.114 | /29 | 192.168.7.113 | Switch1 | Router3 |

---

## 🗺️ Static Routes

All routing was configured manually using static routes. No dynamic routing 
protocols (OSPF, EIGRP, RIP) were used.

| Router | Destination Network | Mask | Next-Hop | Reaches |
|--------|-------------------|------|----------|---------|
| Router0 | 172.16.10.0 | /24 | 192.168.1.2 | via R1 |
| Router0 | 172.16.20.0 | /24 | 192.168.2.1 | via R2 |
| Router0 | 172.16.30.0 | /24 | 192.168.2.1 | via R2 |
| Router0 | 192.168.7.64 | /27 | 192.168.1.2 | R1 LAN |
| Router0 | 192.168.7.96 | /28 | 192.168.2.1 | R2 LAN |
| Router1 | 172.16.10.0 | /24 | 192.168.1.1 | via R0 |
| Router1 | 172.16.20.0 | /24 | 192.168.1.9 | via R3 |
| Router1 | 172.16.30.0 | /24 | 192.168.1.9 | via R3 |
| Router1 | 192.168.7.0 | /25 | 192.168.1.1 | R0 LAN |
| Router1 | 192.168.7.96 | /28 | 192.168.1.9 | R3→R2 LAN |
| Router2 | 172.16.10.0 | /24 | 192.168.2.2 | via R0 |
| Router2 | 172.16.20.0 | /24 | 192.168.1.13 | via R3 |
| Router2 | 172.16.30.0 | /24 | 192.168.1.13 | via R3 |
| Router2 | 192.168.7.0 | /25 | 192.168.2.2 | R0 LAN |
| Router2 | 192.168.7.64 | /27 | 192.168.2.2 | R0→R1 LAN |
| Router3 | 172.16.10.0 | /24 | 192.168.1.10 | via R1 |
| Router3 | 172.16.20.0 | /24 | 192.168.1.14 | via R2 |
| Router3 | 172.16.30.0 | /24 | 192.168.1.14 | via R2 |
| Router3 | 192.168.7.0 | /25 | 192.168.1.10 | R1→R0 LAN |
| Router3 | 192.168.7.64 | /27 | 192.168.1.10 | R1 LAN |


---

## ✅ Verification — End-to-End Ping Results

All endpoints successfully pinged across networks after configuration. 
Screenshots below confirm full connectivity.

**Laptop0 → multiple networks (0% loss)**

![Laptop0 Ping](verification/Laptop0_Ping.png)

**Laptop1 → multiple networks (0% loss)**

![Laptop1 Ping](verification/Laptop1_Ping.png)

**PC3 → multiple networks (0% loss)**

![PC3 Ping](verification/PC3_Ping.png)

**Server0 → multiple networks**

![Server0 Ping](verification/Server0_Ping.png)

---

## 🔴 Troubleshooting Challenges & Lessons Learned

### Issues Encountered
| # | Problem | Root Cause | Fix Applied |
|---|---------|------------|-------------|
| 1 | Routers could not ping each other | Cables connected to wrong interfaces in Packet Tracer | Deleted and reconnected cables to correct Gig ports |
| 2 | Mismatched /30 subnets on inter-router links | IPs assigned from different subnet blocks on each end | Re-IPed Router1, Router2, Router3 interfaces to matching blocks |
| 3 | Incorrect static route next-hops | Wrong neighbor IPs entered on Router2 and Router3 | Removed bad routes with `no ip route`, re-added with correct next-hops |
| 4 | Missing static routes | Several destination networks not added to routing tables | Added missing routes on all four routers |
| 5 | Endpoints couldn't reach other networks | Default gateway not set or not saved on PC0 and PC3 | Set static IP config via CLI using `ip [addr] [mask] [gw]` command |

### Key Lessons
- ✅ Always verify physical cable-to-interface mapping **before** troubleshooting Layer 3
- ✅ Both ends of a /30 point-to-point link must be in the **same subnet block**
- ✅ Static route next-hops must be on a **directly connected** subnet
- ✅ `show ip interface brief` and `show ip route` are the two most valuable troubleshooting commands
- ✅ Endpoints without a default gateway can only reach their **local subnet**
- ✅ In Packet Tracer, use the CLI `ip` command to set endpoint IPs — more reliable than the GUI

---

## 🛠️ Skills Demonstrated
- VLSM subnetting and IP address design
- Cisco IOS static route configuration
- Inter-router connectivity troubleshooting
- OSI Layer 1/2/3 fault isolation
- Endpoint IP configuration and gateway setup
- Network documentation and verification

---

## 📌 Tools Used
- Cisco Packet Tracer
- Google Sheets (documentation)
- Claude AI (troubleshooting assistant)

---

*Lab completed as part of CCNA studies.*
