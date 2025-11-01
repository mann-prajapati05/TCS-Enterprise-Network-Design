============================================================
     TCS ENTERPRISE NETWORK DESIGN - PROJECT INFORMATION
============================================================

Author     : Mann Prajapati (B.Tech Engineering Student)
Platform   : Cisco Packet Tracer
Project    : Enterprise-Level Network Simulation of Tata Consultancy Services (TCS)
Version    : 1.0
Date       : November 2025

------------------------------------------------------------
1. PROJECT OVERVIEW
------------------------------------------------------------
This project simulates the real-world TCS corporate network,
connecting the Mumbai Head Office (HQ) with five Regional Hubs:
Hyderabad, Bengaluru, Chennai, Pune, and Delhi-NCR.

The network represents an enterprise-scale WAN architecture
using a hybrid topology (Star + Ring) to ensure scalability,
redundancy, and fault tolerance.

------------------------------------------------------------
2. NETWORK TOPOLOGY STRUCTURE
------------------------------------------------------------
• Mumbai HQ (Central Core)
• 5 Regional Hubs (Distribution Layer)
    - Hyderabad
    - Bengaluru
    - Chennai
    - Pune
    - Delhi-NCR
• Multiple Local Offices under each Regional Hub (Access Layer)

TOPOLOGY TYPE:
    - Star Topology: HQ → All Regional Hubs
    - Ring Topology: Regional Hubs interconnected to neighbors
      for redundancy (resilient ring backbone)
    - Hierarchical Enterprise Design (Core / Distribution / Access)

------------------------------------------------------------
3. IP ADDRESSING SCHEME
------------------------------------------------------------
Global Private Block: 10.0.0.0/8

Subnetting applied to distribute networks across regions:

| Region        | Subnet Range     | VLANs/Departments       |
|----------------|------------------|--------------------------|
| Mumbai HQ      | 10.0.0.0/11      | VLAN10 HR, VLAN20 Sales, VLAN30 IT , VLAN40 Server Room|
| Hyderabad Hub  | 10.32.0.0/11     | VLAN60 AI Solutions, VLAN100 Sales , Vlan90 Server Room |
| Bengaluru Hub  | 10.64.0.0/11     | VLAN70 Sales , VLAN110 Server Room |
| Chennai Hub    | 10.96.0.0/11     | Server Room |
| Pune Hub       | 10.128.0.0/11    | Server Room |
| Delhi-NCR Hub  | 10.160.0.0/11    | Server Room |

DHCP Scope per hub provides automatic IP allocation.
All hubs are interconnected via point-to-point router links.

------------------------------------------------------------
4. NETWORK SERVICES CONFIGURED
------------------------------------------------------------
CENTRALIZED (Mumbai HQ)
------------------------
  • DNS Server  - Internal name resolution
  • FTP Server  - File transfer and repository
  • HTTP Server - Corporate intranet and web services
  • Email Server - Internal mail system

REGIONAL HUBS
--------------
  • DHCP Server - Assigns IPs to local offices/departments
  • Local DNS Forwarder
  • Local Switches (L3) for inter-VLAN routing

------------------------------------------------------------
5. ROUTING & COMMUNICATION
------------------------------------------------------------
ROUTING PROTOCOL:
    → OSPF (Single Area 0)

PURPOSE:
    - Dynamic route exchange between HQ, hubs, and offices
    - Automatic path selection
    - Redundancy through multiple inter-hub links

------------------------------------------------------------
6. VLAN & INTER-VLAN CONFIGURATION
------------------------------------------------------------
• Implemented using Layer-3 Switches at HQ and Offices
• Each department assigned unique VLAN ID and subnet
• VLAN-to-VLAN communication enabled via IP routing

SAMPLE:
    VLAN 10 - HR Dept (10.0.0.0/14)
    VLAN 20 - Sales Dept (10.4.1.0/14)
    VLAN 30 - IT Dept (10.8.0.0/14)
    VLAN 30 - IT Dept (10.12.0.0/14)

------------------------------------------------------------
7. WAN & REDUNDANCY DESIGN
------------------------------------------------------------
• WAN Backbone simulated using Serial & Gigabit links
• MPLS/SD-WAN architecture conceptually represented
• Redundant links between regional hubs for failover
• Each hub connected to HQ + two neighboring hubs
  (ensuring loop-free but redundant ring connectivity)

------------------------------------------------------------
8. SECURITY & MANAGEMENT
------------------------------------------------------------
• DHCP Snooping & Port Security on access switches
• ACLs applied to restrict inter-departmental access
• Default gateway & routing protection on core routers
• Centralized management concept from HQ

------------------------------------------------------------
9. FUTURE ENHANCEMENTS
------------------------------------------------------------
1. Implement NAT & Internet Gateway simulation
2. Add HSRP redundancy between Layer-3 switches
3. Integrate SNMP and Syslog monitoring servers
4. Deploy ASA Firewall at HQ edge
5. Expand VPN connectivity for remote clients

------------------------------------------------------------
10. TESTING & VERIFICATION
------------------------------------------------------------
✅ Ping tests successful between:
   - HQ ↔ All Regional Hubs
   - Offices within same hub
   - Inter-VLAN communication (via L3 Switch)
✅ OSPF adjacency verified between all routers
✅ DHCP successfully allocates dynamic IPs
✅ DNS resolution functioning for internal hosts
✅ FTP, HTTP, and Email servers reachable

------------------------------------------------------------
11. FILES INCLUDED
------------------------------------------------------------
• TCS_Network_Design.pkt  → Cisco Packet Tracer Project
• README_TCS_Project_Info.txt  → Network Summary (this file)
• Individual Config Files  → Router & Switch CLI outputs
• TCS_Network_Overview.png → Network Topology Diagram

------------------------------------------------------------
12. PROJECT SUMMARY
------------------------------------------------------------
This simulation represents a real enterprise-level design:
- Scalable private WAN with dynamic routing
- Centralized IT services
- Multi-department VLAN-based segmentation
- MPLS-like redundant inter-hub backbone
- DHCP-based automation
- Realistic addressing hierarchy (10.0.0.0/8)

------------------------------------------------------------
13. AUTHOR INFORMATION
------------------------------------------------------------
Name   : Mann Prajapati
Role   : B.Tech Engineering Student (Networking & AI Enthusiast)
Year   : 2025
LinkedIn: https://www.linkedin.com/in/mann-prajapati-831a46327/
GitHub : https://github.com/mann-prajapati05

============================================================
       END OF DOCUMENT - TCS NETWORK PROJECT INFO
============================================================
