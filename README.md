# Project_Computer-Networks_CSE421

# ✈️ Federal Flight Agency Network  
### Cisco Packet Tracer | Computer Networks Project

---

## 📌 Project Overview

This project is a **mission-critical enterprise network design and implementation** created in **Cisco Packet Tracer** for the **Federal Flight Agency Network**, a next-generation aerospace organization working on **fully autonomous aircraft systems**.

The objective of this project was to design a **highly reliable**, **redundant**, and **well-segmented** network infrastructure capable of supporting:

- Real-time communication
- Telemetry systems
- Autonomous navigation
- Simulation labs
- Maintenance operations
- Emergency backup control

This project was not just about connecting routers and PCs. It focused on building a **real-world scalable network architecture** using:

- **VLSM subnetting**
- **Static routing**
- **Dynamic routing (RIPv2)**
- **DHCP**
- **DNS**
- **Web services**
- **Email services**
- **Redundant path design**
- **Network segmentation and controlled communication**

---

## 🎯 Project Goals

The main goal of this project was to simulate a network where multiple critical departments of an aerospace organization can communicate **securely**, **efficiently**, and with **redundancy**.

The project had to satisfy several networking constraints, including:

- ✅ Strict logical segmentation  
- ✅ Backup communication paths  
- ✅ Routing isolation  
- ✅ No default routes  
- ✅ Local and centralized DHCP deployment  
- ✅ Centralized DNS and Web services  
- ✅ Internal email communication  
- ✅ Static addressing for emergency systems

---

## 🏢 Network Units Implemented

The network is divided into several major units:

### 🏛️ 1. Command Center (HQ)
The HQ acts as the **central control unit**.

**Responsibilities:**
- Central monitoring
- Centralized DNS server
- Centralized Web server
- Direct link to Simulation Core
- Direct link to Emergency Node

**Services hosted:**
- **DNS**
- **HTTP Web Server** (Displays: *"Autonomous Flight Control System Active"*)

### 🤖 2. AI Navigation Unit
The AI division was segmented into two sub-units:
- **ML Engine**
- **Data Processing Cell**

**Features implemented:**
- Local DHCP through routers
- Dynamic routing
- Redundant path toward HQ

### 🧪 3. Aircraft Simulation Lab
This part contains:
- **Simulation Core**
- **Testing Sandbox**

**Key role:**
Acts as the **central transit backbone** between several departments.

**Features implemented:**
- Centralized DHCP server
- DHCP relay using `ip helper-address`
- Static route toward HQ
- Dynamic RIPv2 toward AI and Hangar networks

### 🔧 4. Maintenance Hangar
This division contains:
- **Diagnostics Bay**
- **Repair Unit**

**Features:**
- Local DHCP allocation
- Dynamic routing
- Communication allowed toward HQ **only through Simulation Lab**

### 🚨 5. Emergency Control Node
This is the backup control unit.

**Features implemented:**
- Static addressing only
- No DHCP
- No dynamic routing participation
- Direct dedicated connection to HQ

---

## 🧠 What I Did in This Project

This project was fully implemented by designing both the **logical network architecture** and the **router/server configuration**.

### 🧮 1. Designed VLSM Addressing Scheme
I created a full **VLSM-based subnetting plan** to efficiently allocate address space according to the size of each unit.

| Network | Purpose |
|--------|--------|
| `1.0.0.0/21` | HQ |
| `1.0.8.0/22` | Simulation Core |
| `1.0.12.0/22` | Simulation Sandbox |
| `1.0.16.0/23` | ML Engine |
| `1.0.18.0/23` | Data Processing |
| `1.0.20.0/23` | Diagnostics |
| `1.0.22.0/23` | Repair |
| `1.0.24.0/25` | Emergency |
| `1.0.24.128/28` | Backbone |

### 🌐 2. Built Complete Network Topology
I created the entire topology in **Cisco Packet Tracer** with:
- Multiple routers and switches
- PCs and printers
- DNS server, Web server, and Mail server

### 🔀 3. Implemented Static Routing
I configured **manual static routes** where required to ensure controlled and predictable routing behavior.
- HQ to Emergency Node
- HQ to Simulation networks
- Simulation Core toward HQ

### 🔁 4. Implemented Dynamic Routing (RIPv2)
For the backbone-connected networks, I configured **RIPv2** because multiple internal departments needed dynamic route exchange while maintaining scalability.
**Features used:** `version 2`, `no auto-summary`, `passive-interface`

### 🛡️ 5. Configured Redundant Paths / Failover
One of the important project requirements was **redundancy**. I configured:
- Primary route from AI networks toward HQ
- Floating static backup route through **Simulation Sandbox**

### 📡 6. Configured DHCP
- **Centralized DHCP:** Hosted on the Simulation Core server.
- **DHCP Relay:** `ip helper-address` was configured in Simulation Sandbox.
- **Local DHCP:** Pools were created on routers for ML Engine, Data Processing Cell, Diagnostics Bay, and Repair Unit.

### 🌍 7. Configured DNS and Web Services
At HQ, I configured DNS resolution for the web service and hosted a web page accessible via:
`www.federalfgt.control`

### 📧 8. Configured Email Services
I implemented internal mail communication using **SMTP** and **POP3**. Configured mail communication between:
- `mail.hq.federal`
- `mail.ai.federal`

### 🧷 9. Static Addressing for Emergency Node
The Emergency Control Node was configured with **only static IP addressing** (no DHCP, no dynamic routing) to meet reliability and isolation requirements.

---

## ⚙️ Routers Configured

The following routers were fully configured manually:
- `R_HQ`
- `R_SimCore`
- `R_SimSandbox`
- `R_ML`
- `R_DP`
- `R_Diag`
- `R_Repair`
- `R_Emergency`

Each router includes interface addressing, routing configuration, DHCP configuration (where required), and RIP configuration (where required).

---

## 🧪 Connectivity Validation

After configuration, I tested end-to-end connectivity across the network. Validation included:

- ✅ PC to PC communication
- ✅ DHCP address assignment
- ✅ DNS name resolution
- ✅ Web server access
- ✅ Email communication
- ✅ Route propagation
- ✅ Inter-subnet communication
- ✅ Redundancy behavior

---

## 📚 Networking Concepts Used

This project helped apply multiple important computer networking concepts in one large implementation:

- VLSM subnetting
- Static routing & floating static routes
- RIPv2
- DHCP & DHCP relay
- DNS, Web server, SMTP, POP3
- Network segmentation & redundancy
- Route control
- Enterprise topology design

---

## 🛠️ Files Included in This Repository

- 📁 Cisco Packet Tracer file (`.pkt`)
- 📁 Topology diagram
- 📁 VLSM tree
- 📁 IP addressing table
- 📁 Configuration commands
- 📁 Project documentation

---

## 🚀 What I Learned From This Project

This project gave me practical hands-on experience with enterprise-level network design. Through this project I learned how to:

- Design scalable subnet structures
- Configure routers manually
- Implement routing protocols and build redundancy
- Manage DHCP centrally and locally
- Deploy DNS/web/email services
- Troubleshoot route propagation issues
- Design networks under real-world constraints

---

## 💡 Assumptions Made

During implementation, some practical assumptions were made. For example, `.com` naming was used instead of `.federal` where necessary in Packet Tracer.

---

## 📌 Final Note

This was a full-scale Cisco Packet Tracer enterprise networking project focused on reliability, routing control, redundancy, and service deployment. It simulates how a real aerospace control infrastructure may be designed for:

- ✈️ Autonomous aircraft operations
- 🛰️ Secure telemetry systems
- 🧠 AI navigation
- 🚨 Emergency failover communication

---

**👨‍💻 Author:** Ahnaf Jahin  
*Computer Networks Project - Cisco Packet Tracer Implementation*
