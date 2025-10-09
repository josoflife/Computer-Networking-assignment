# 🌐 CMGP325 Final Project: Hybrid Network Topology

## 🧭 Overview

Welcome to my **CMGP325 Networking Final Project!** 🎓
This project showcases the design, simulation, configuration, and documentation of a **Hybrid Network Topology** in **Cisco Packet Tracer**.

It combines multiple topologies — **Bus**, **Mesh**, **Star**, **Ring**, and **Extended Star** — into one fully functional hybrid network featuring **IPv4 & IPv6**, **VLAN segmentation**, **DHCP/DNS/HTTP servers**, and **security policies** 🖥️🔐.

A key highlight of this project is my **unique feature**: the implementation of an **IPv4 Default Route** that ensures seamless connectivity between internal VLANs and the simulated ISP 🌍.

---

## 🧩 Project Structure

### 🕸️ Topologies Implemented

* **Bus**, **Mesh**, **Star**, **Ring**, and **Extended Star** – all merged into one hybrid topology.
* Departmental segmentation into **Admin**, **Security**, **IT**, and **Server VLANs**.

### 📊 VLAN Segmentation

| VLAN Name | VLAN ID | IPv4 Network    | IPv6 Network     | Default Gateway (IPv4) | Default Gateway (IPv6) | Department       |
| --------- | ------- | --------------- | ---------------- | ---------------------- | ---------------------- | ---------------- |
| Admin     | 10      | 192.168.10.0/24 | 2001:db8:10::/64 | 192.168.10.1           | 2001:db8:10::1         | Admin Area 👩‍💼 |
| Security  | 20      | 192.168.20.0/24 | 2001:db8:20::/64 | 192.168.20.1           | 2001:db8:20::1         | Security Dept 🔒 |
| IT        | 30      | 192.168.30.0/24 | 2001:db8:30::/64 | 192.168.30.1           | 2001:db8:30::1         | IT Dept 👨‍💻    |
| Server    | 40      | 192.168.40.0/24 | 2001:db8:40::/64 | 192.168.40.1           | 2001:db8:40::1         | Server VLAN 🖥️  |

---

## ⚙️ Network Design & Configuration

### 🏗️ Logical Structure

* **Core Router** – main routing device connecting the internal VLAN and the ISP.
* **Core Switch** – backbone for inter-switch trunking.
* **Distribution Switches** – connect departmental switches.
* **Access Switches** – provide device-level connectivity.
* **Servers** 🖥️:

  * **DHCP** – allocates IPv4 and IPv6 addresses.
  * **DNS** – resolves internal hostnames.
  * **HTTP** – hosts a brief summary about the project.

---

## 🌍 Unique Feature: IPv4 Default Route 🛣️

### 🎯 Objective

To configure and test an **IPv4 default route** on the core router, allowing all VLANs to send packets destined for external networks to the simulated ISP router.

### ⚙️ Configuration Commands

Below is the configuration applied to the **Core Router**:

```bash
CoreRouter(config)# ip route 0.0.0.0 0.0.0.0 192.168.50.2
```

* `0.0.0.0 0.0.0.0` → Represents all unknown IPv4 destinations.
* `192.168.50.2` → The next-hop IP address of the **ISP router**.

### ✅ Verification Commands

```bash
CoreRouter# show ip route
CoreRouter# ping 8.8.8.8
CoreRouter# traceroute 8.8.8.8
```

**Expected Results:**

* The routing table shows a static default route (`S* 0.0.0.0/0 [1/0] via 192.168.50.2`).
* Pings to external IPs succeed through the ISP router.
* Traceroute confirms the path through the ISP gateway.

### 🌐 Impact

* Provides universal reachability for all internal VLANs.
* Simplifies routing management — only one route needed for unknown destinations.
* Demonstrates understanding of **Layer 3 routing fundamentals** and **default route logic**.

---

## 🛡️ Security Features

* **Access Control Lists (ACLs):** restrict printer access to local VLANs only 🖨️
* **Password Protection:** secures privileged router and switch access 🔑
**Password🤐🤫**
  R1="verysecret"
  Distributing switches= "DISTRsecret"
  admin switch ="adminsecret"
  security switch ="secsecret"
  it switch ="itsecret"
  server switch=" server switch"
---

## ✅ Testing & Verification

| Test              | Expected Outcome                  | Command              |
| ----------------- | --------------------------------- | -------------------- |
| IPv4 Connectivity | Devices receive IPs via DHCP      | `show ip int brief`  |
| IPv6 Connectivity | IPv6 communication across VLANs   | `show ipv6 int`      |
| DNS Resolution    | Hostnames resolve correctly       | `nslookup`           |
| HTTP Access       | Web page loads using DNS name     | Browser test 🌐      |
| Default Route     | Ping external network through ISP | `ping`, `traceroute` |
| ACL Enforcement   | Printers restricted to VLAN       | Ping/Print test 🖨️  |

---

## 🖼️ Screenshots & Evidence

📁 **/screenshots/** includes:
📸 Topology layout
📸 VLAN configurations
📸 IPv4 default route table
📸 Successful pings to ISP
📸 ACL test results

---

## 🎥 Demonstration Video

**🔗 Video Link:** [Insert your YouTube or Google Drive link here]

🎬 **Includes:**

* Overview of topology
* VLAN, DHCP, DNS, and default route configuration
* IPv4/IPv6 connectivity tests
* Explanation of default route behavior
* Reflection on lessons learned

---

## 💡 Challenges & Lessons Learned

* Configuring a **default route** helped me understand how internal traffic exits the LAN 🌍
* Misconfigured next-hop IPs caused early connectivity issues ⚠️
* Verifying default routes with `show ip route` ensured correct ISP linking
* Learned the importance of **dual-stack routing** (IPv4 + IPv6)

---

## 📂 Repository Contents

| File/Folder     | Description                         |
| --------------- | ----------------------------------- |
| `project2.pkt`  | Cisco Packet Tracer simulation file |
| `README.md`     | Main project documentation          |
| `/configs/`     | Router and switch config files      |
| `/screenshots/` | Testing and result evidence         |

---

## 👤 Author
josoflife
---

## 📝 License

This project was developed for academic submission in CMGP325.
Reproduction or distribution without permission is not allowed. 🚫

