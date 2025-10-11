# 🌐 Computer Networks Final Project

## 👩‍💻 Project Title: *Network Topology Design, Configuration & Demonstration*

---

### 🧩 Overview  
This project demonstrates my understanding of **computer networking concepts** using **Cisco Packet Tracer**.  
It is divided into two main parts focusing on network topology design, configuration, and a unique feature — **IPv4 Default Routing** 🌍.

---

## 🛰️ Part I – Network Topologies Design & Simulation

### 🔹 **Objective**
Design, configure, and document the following network topologies:

- 🚌 **Bus Topology**
- 💫 **Star Topology**
- 🔗 **Ring Topology**
- 🌐 **Mesh Topology**
- 🏗️ **Extended Star Topology**
- ⚙️ **Hybrid Topology** *(integration of the above)*

---

### 💡 **Hybrid Topology Highlights**
The hybrid topology integrates **core**, **distribution**, and **access** layers with VLAN segmentation and dual-stack addressing (IPv4 + IPv6).

#### ⚙️ **Key Configurations**
- IPv4 & IPv6 addressing implemented on all routers and switches  
- VLAN segmentation for Staff, IT, and Management networks  
- HTTP/DNS/DHCP server hosted on Server VLAN  
- Basic security with passwords, port security,
- IPv4 Default Route configured for efficient routing  

---

### 📋 **IP Addressing & VLAN Table**
## IP Addressing Table

| VLAN Name   | VLAN ID | IPv4 Network       | IPv6 Network         | Default Gateway (IPv4) | Default Gateway (IPv6) | Department      |
|-------------|---------|--------------------|----------------------|-----------------------|------------------------|-----------------|
| Admin       | 10      | 192.168.10.0/24    | 2001:db8:10::/64     | 192.168.10.1          | 2001:db8:10::1         | Admin Area      |
| Security    | 20      | 192.168.20.0/24    | 2001:db8:20::/64     | 192.168.20.1          | 2001:db8:20::1         | Security Dept   |
| IT          | 30      | 192.168.30.0/24    | 2001:db8:30::/64     | 192.168.30.1          | 2001:db8:30::1         | IT Dept         |
| Server      | 40      | 192.168.40.0/24    | 2001:db8:40::/64     | 192.168.40.1          | 2001:db8:40::1         | Server VLAN     |

.
🧠 Verification Commands
| Purpose                 | Command                 |
| ----------------------- | ----------------------- |
| View IPv4 Routing Table | `show ip route`         |
| Verify VLANs            | `show vlan brief`       |
| Check Trunk Links       | `show interfaces trunk` |
| Test Connectivity       | `ping [destination IP]` |
| Verify IPv6 Routing     | `show ipv6 route`       |


---

## 🚦 Part II – Unique Feature Configuration

### 🌍 **Feature: IPv4 Default Route**
A **default route** allows a router to send packets to a next-hop address when no specific route is found in its routing table.

 
🧭 **Command used:**
ip route 0.0.0.0 0.0.0.0 192.168.100.2


---

 ### 📝 ***License***



This project was developed for academic submission in CMGP325.
Reproduction or distribution without permission is not allowed. 🚫


