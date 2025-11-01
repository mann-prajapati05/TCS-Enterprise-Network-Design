# TCS-Enterprise-Network-Design
TCS Enterprise Network Design (Cisco Packet Tracer) => This project simulates the real-world **Tata Consultancy Services (TCS)** enterprise network, connecting the Mumbai Head Office (HQ) with five Regional Hubs — Hyderabad, Bengaluru, Chennai, Pune, and Delhi-NCR — along with their distributed local offices.

---
---

## 🏢 Project Overview

This project is a complete simulation of the **Tata Consultancy Services (TCS)** corporate network using **Cisco Packet Tracer**, replicating how a global enterprise connects its **Headquarters**, **Regional Hubs**, and **Distributed Offices** using a mix of **Star**, **Ring**, and **Hierarchical topologies**.

It demonstrates professional **Enterprise Networking concepts**, including:
- Hierarchical network design
- Inter-VLAN communication
- Dynamic routing (OSPF)
- DHCP-based address allocation
- Centralized services (DNS, FTP, HTTP, Email)
- Redundant links and fault tolerance
- Private WAN backbone with MPLS/SD-WAN-like design

---
## 🏗️ Network Architecture

### 🧩 Design Topology
- **Star + Ring Hybrid Topology**
  - HQ (Mumbai) at the center
  - 5 Regional Hubs in a ring topology (for redundancy)
- **Each Regional Hub** connects to:
  - HQ (Mumbai)
  - Two neighboring Regional Hubs
  - Multiple local offices

### 🌍 IP Addressing
- Single private block: `10.0.0.0/8`
- Subnetting applied per region, hub, and department
- DHCP servers provide dynamic IPs to clients

## 📍 IP Addressing & Subnetting
| Category | Network Range | Subnets + VLANs | Description |
|-----------|----------------|----------------|--------------|
| **Global Private Block** | 10.0.0.0/8 | - | Reserved for internal TCS addressing |
| **Mumbai HQ** | 10.0.0.0/11 | VLAN10, VLAN20, VLAN30 , VLAN40 | HR, Sales, IT ,Server Room|
| **Hyderabad Hub** | 10.32.0.0/11 | VLAN60 , VLAN100 , Vlan90  | AI Solutions, Sales, Server Room|
| **Bengaluru Hub** | 10.64.0.0/11 | - | Future use |
| **Chennai Hub** | 10.96.0.0/11 | VLAN70, VLAN110 | Sales ,Server Room |
| **Pune Hub** | 10.128.0.0/11 | -| Future use |
| **Delhi-NCR Hub** | 10.160.0.0/11 | - | Future use |

Each region uses **subnetted ranges** from `10.0.0.0/8`, maintaining scalability and logical separation.

---
### 🧠 Routing & Switching
- **Dynamic Routing Protocol:** OSPF (Single Area)
- **Inter-VLAN Communication:** Layer-3 switches at each office
- **Redundant Links:** Between hubs for fault tolerance
- **Server rooms:** At HQ and each Regional Hub

---

## 🖥️ Network Services

| Service | Location | Description |
|----------|-----------|-------------|
| 🧭 **DNS Server** | Mumbai HQ | Handles name resolution for all internal TCS resources |
| 💾 **FTP Server** | Mumbai HQ | Secure internal file transfer system |
| 🌐 **HTTP Server** | Mumbai HQ | Hosts the internal TCS intranet site |
| 📧 **Email Server** | Mumbai HQ | Handles all enterprise email communication |
| 🔢 **DHCP Server** | All Regional Hubs | Dynamically assigns IPs to local networks |
| 🔐 **Firewall/NAT Gateway** | HQ Edge Router | Protects and controls internet-bound traffic |

---

## 🧩 Departments and Offices
| Region | Offices | Departments |
|---------|----------|-------------|
| **Mumbai HQ** | 1 | HR, Sales, IT |
| **Hyderabad Hub** | 2 | Sales (Office 1), AI Solutions (Office 2) |
| **Chennai Hub** | 1 | IT (office 1) |
| **Other Hubs** | Planned expansion | - |

---
