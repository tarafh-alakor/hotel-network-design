Design and Implementation of an Hotel System Network Design

This project presents the design and implementation of a complete enterprise network infrastructure for a hotel environment using Cisco Packet Tracer. The network is designed to support multiple departments distributed across three floors while ensuring secure communication, network segmentation, dynamic routing, wireless connectivity, and centralized management.

The goal of the project is to build a scalable and secure network architecture that allows all departments to communicate efficiently while maintaining network isolation through VLAN technology.

Project Overview

The hotel building consists of three floors. Each floor hosts multiple departments that require reliable wired and wireless connectivity. Each floor is connected through its own router and switch. All routers are located in the server room within the IT department and are interconnected using serial links.

Dynamic routing is implemented to allow communication between all networks across the three floors. Each router also acts as the DHCP server for the devices connected within its respective floor.

The network supports laptops, desktop computers, printers, mobile devices, and wireless connections.

Network Architecture
Floor	Departments	Router	Switch
Floor 1	Reception, Store, Logistics	Router-F1	Switch-F1
Floor 2	Finance, HR, Sales / Marketing	Router-F2	Switch-F2
Floor 3	IT, Admin	Router-F3	Switch-F3

All routers are installed in the server room located in the IT department.

Each floor contains one access switch that connects all devices on that floor including computers, printers, and wireless access points.

Router Interconnection Network

The three routers are interconnected using serial DCE cables forming the backbone network of the hotel infrastructure.

Router Connection	Network Address
Router 1 – Router 2	10.10.10.0 /30
Router 2 – Router 3	10.10.10.4 /30
Router 1 – Router 3	10.10.10.8 /30

This interconnection allows dynamic routing between all floors.

VLAN Network Design

Each department is assigned to a separate VLAN to improve security, performance, and traffic management.

First Floor
Department	VLAN	Network
Reception	VLAN 80	192.168.8.0 /24
Store	VLAN 70	192.168.7.0 /24
Logistics	VLAN 60	192.168.6.0 /24
Second Floor
Department	VLAN	Network
Finance	VLAN 50	192.168.5.0 /24
HR	VLAN 40	192.168.4.0 /24
Sales / Marketing	VLAN 30	192.168.3.0 /24
Third Floor
Department	VLAN	Network
Admin	VLAN 20	192.168.2.0 /24
IT	VLAN 10	192.168.1.0 /24

Each department operates within its own broadcast domain while still being able to communicate with other departments through inter-VLAN routing.

Wireless Network

Each floor contains a wireless access point that provides Wi-Fi connectivity for mobile devices such as laptops and smartphones. Wireless users connect to the same departmental networks and receive their IP addresses dynamically through DHCP.

This ensures seamless connectivity for both wired and wireless devices within the hotel environment.

DHCP Implementation

Each router functions as the DHCP server for its corresponding floor. Devices connected to the network automatically obtain IP addressing information including the default gateway and network configuration.

Dynamic addressing simplifies network management and allows new devices to connect without manual configuration.

Dynamic Routing

The network uses OSPF (Open Shortest Path First) as the routing protocol. OSPF dynamically advertises all networks between routers and ensures efficient path selection across the hotel infrastructure.

This routing mechanism enables communication between all VLAN networks across the three floors.

Network Security

Security measures are implemented to prevent unauthorized access to the network. Port security is configured on the switch located in the IT department.

Only a specific device named Test-PC is allowed to access port Fa0/1. If another device attempts to connect to this port, the port will automatically shut down to protect the network.

This mechanism ensures that only authorized devices can access critical network ports.

Secure Remote Access

Secure Shell (SSH) is configured on all routers to allow encrypted remote login for network administrators. This allows administrators to manage and monitor the network securely without requiring physical access to the routers.

SSH provides authentication and encrypted communication to protect sensitive administrative sessions.

Network Devices
Device Type	Purpose
Routers	Provide inter-VLAN routing and connect all floors
Switches	Connect devices within each floor
Wireless Access Points	Provide Wi-Fi connectivity
Desktop Computers	Department workstations
Laptops and Smartphones	Wireless user devices
Printers	Department printing services
Network Verification

The network was thoroughly tested to ensure full connectivity and proper configuration.

Test	Result
VLAN segmentation	Successful
Inter-VLAN communication	Successful
DHCP address assignment	Successful
OSPF route propagation	Successful
Wireless connectivity	Successful
SSH remote login	Successful
Port security enforcement	Successful

All devices in the network are able to communicate with each other according to the project requirements.

Project Files
File	Description
Packet Tracer File	Complete network topology implementation
Network Diagram	Visual representation of the network architecture
Documentation	Detailed explanation of the project design
Author

Tarafh Al-Akor
Information Technology Student
Network Design and Implementation Project
