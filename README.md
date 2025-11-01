# TCS-Enterprise-Network-Design
TCS Enterprise Network Design (Cisco Packet Tracer) => This project simulates the real-world **Tata Consultancy Services (TCS)** enterprise network, connecting the Mumbai Head Office (HQ) with five Regional Hubs — Hyderabad, Bengaluru, Chennai, Pune, and Delhi-NCR — along with their distributed local offices.

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

### 🧠 Routing & Switching
- **Dynamic Routing Protocol:** OSPF (Single Area)
- **Inter-VLAN Communication:** Layer-3 switches at each office
- **Redundant Links:** Between hubs for fault tolerance
- **Server rooms:** At HQ and each Regional Hub

---

## 🖥️ Implemented Network Services
| Service | Location | Description |
|----------|-----------|-------------|
| DNS | Mumbai HQ | Domain name resolution for internal resources |
| HTTP | Mumbai HQ | Company intranet / web hosting |
| FTP | Mumbai HQ | Centralized file transfer service |
| Email | Mumbai HQ | Internal mail service |
| DHCP | Every Hub | Automatic IP allocation per subnet |

---

## 🧩 Departments and Offices
| Region | Offices | Departments |
|---------|----------|-------------|
| **Mumbai HQ** | 1 | HR, Sales, IT |
| **Hyderabad Hub** | 2 | Sales (Office 1), AI Solutions (Office 2) |
| **Chennai Hub** | 1 | IT (office 1) |
| **Other Hubs** | Planned expansion | - |

---
