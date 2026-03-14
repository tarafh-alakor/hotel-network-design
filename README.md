
---

# Design and Implementation of an Hotel System Network Design

This project presents the **design and implementation of a scalable hotel network infrastructure** using Cisco Packet Tracer.
The network supports multiple departments across three floors while ensuring **secure communication, efficient traffic management, wireless connectivity, and centralized network administration**.

The design focuses on applying modern networking technologies including **VLAN segmentation, inter-VLAN routing, dynamic routing with OSPF, DHCP automation, secure SSH access, and network security mechanisms**.

---

# Project Overview

The hotel building consists of **three floors**, each containing multiple operational departments.
Each floor includes its own **router and access switch**, while all routers are centralized in the **IT department server room**.

The routers are interconnected using **serial DCE connections** to form the core backbone network.
All devices within the network obtain IP addresses dynamically through DHCP services configured on the routers.

The infrastructure supports both **wired and wireless connectivity** for computers, printers, laptops, and mobile devices.

---

# Network Topology
[https://github.com/tarafh-alakor/hotel-network-design/blob/53d1cd9bae5e67881c4708a57041fbb9c3309e70/README.md
](https://github.com/tarafh-alakor/hotel-network-design/blob/53d1cd9bae5e67881c4708a57041fbb9c3309e70/README.md)
---

# Network Architecture

| Floor   | Departments                    | Router    | Switch    |
| ------- | ------------------------------ | --------- | --------- |
| Floor 1 | Reception, Store, Logistics    | Router-F1 | Switch-F1 |
| Floor 2 | Finance, HR, Sales / Marketing | Router-F2 | Switch-F2 |
| Floor 3 | IT, Admin                      | Router-F3 | Switch-F3 |

All routers are located in the **IT department server room**, which acts as the network core.

Each floor switch connects the department devices including:

* Desktop computers
* Printers
* Wireless access points

---

# Router Interconnection Network

Routers are connected together using **Serial DCE cables**, creating a routed backbone network.

| Router Link         | Network Address |
| ------------------- | --------------- |
| Router 1 ↔ Router 2 | 10.10.10.0 /30  |
| Router 2 ↔ Router 3 | 10.10.10.4 /30  |
| Router 1 ↔ Router 3 | 10.10.10.8 /30  |

This backbone allows dynamic routing and full communication between all floors.

---

# VLAN Network Design

Each department is placed within its own VLAN to ensure **traffic isolation, improved performance, and enhanced security**.

## First Floor VLANs

| Department | VLAN ID | Network         |
| ---------- | ------- | --------------- |
| Reception  | 80      | 192.168.8.0 /24 |
| Store      | 70      | 192.168.7.0 /24 |
| Logistics  | 60      | 192.168.6.0 /24 |

## Second Floor VLANs

| Department        | VLAN ID | Network         |
| ----------------- | ------- | --------------- |
| Finance           | 50      | 192.168.5.0 /24 |
| HR                | 40      | 192.168.4.0 /24 |
| Sales / Marketing | 30      | 192.168.3.0 /24 |

## Third Floor VLANs

| Department | VLAN ID | Network         |
| ---------- | ------- | --------------- |
| Admin      | 20      | 192.168.2.0 /24 |
| IT         | 10      | 192.168.1.0 /24 |

Inter-VLAN routing allows departments to communicate securely across different VLANs.

---

# Wireless Network Infrastructure

Each floor includes a **wireless access point** that enables Wi-Fi connectivity for mobile devices such as:

* Laptops
* Smartphones

Wireless users connect to the same departmental network and receive IP configuration automatically through DHCP.

---

# DHCP Implementation

Each router is configured as the **DHCP server** for the VLANs within its floor.

This enables devices to automatically receive:

| Parameter       | Purpose                           |
| --------------- | --------------------------------- |
| IP Address      | Unique device identification      |
| Default Gateway | Communication with other networks |
| Network Mask    | Defines network boundaries        |
| DNS Server      | Domain name resolution            |

Dynamic addressing significantly simplifies network administration.

---

# Dynamic Routing

The network uses the **Open Shortest Path First (OSPF)** routing protocol.

OSPF dynamically advertises all networks across the routers, allowing:

* Efficient route selection
* Automatic route updates
* Scalable network growth

This ensures seamless communication between all departments across the hotel.

---

# Network Security

Port security is implemented on the switch in the **IT department**.

Only the authorized device **Test-PC** is allowed to connect to port **Fa0/1**.

| Security Feature    | Description                                                          |
| ------------------- | -------------------------------------------------------------------- |
| Sticky MAC Address  | Automatically learns the authorized device MAC address               |
| Maximum MAC Address | Limits the number of allowed devices                                 |
| Violation Mode      | Automatically shuts down the port if an unauthorized device connects |

This mechanism prevents unauthorized devices from accessing sensitive network resources.

---

# Secure Remote Management

Secure Shell (**SSH**) is configured on all routers to allow encrypted remote administrative access.

This provides:

* Secure authentication
* Encrypted management sessions
* Remote troubleshooting capability

SSH ensures secure remote management of the network infrastructure.

---

# Network Devices

| Device Type            | Function                                |
| ---------------------- | --------------------------------------- |
| Routers                | Interconnect floors and perform routing |
| Switches               | Connect departmental devices            |
| Wireless Access Points | Provide Wi-Fi connectivity              |
| Desktop PCs            | Employee workstations                   |
| Laptops & Smartphones  | Wireless client devices                 |
| Network Printers       | Department printing services            |

---

# Network Verification

Extensive testing was performed to verify the correct operation of the network.

| Test Scenario             | Result     |
| ------------------------- | ---------- |
| VLAN segmentation         | Successful |
| Inter-VLAN communication  | Successful |
| DHCP address assignment   | Successful |
| OSPF route propagation    | Successful |
| Wireless connectivity     | Successful |
| SSH remote login          | Successful |
| Port security enforcement | Successful |

All devices across the network are able to communicate according to the project requirements.

---

# Project Files

| File               | Description                                 |
| ------------------ | ------------------------------------------- |
| Packet Tracer File | Complete network topology implementation    |
| Network Diagram    | Visual representation of the network design |
| Documentation      | Detailed explanation of the project         |

---

# Author

**Tarafh Al-Akor**
Information Technology Student
Network Design and Implementation Project

---
