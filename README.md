# 🎓 University Campus Network – Final CN Lab Project

This is a simulation of a **university campus network** using **Cisco Packet Tracer** created as part of our final project for the Computer Networks Lab.

---

## 📌 Project Objectives

- Design a campus-wide network with departmental segmentation
- Implement VLANs for logical separation
- Configure **Inter-VLAN routing** using a **Layer 3 switch**
- Use **Dot1Q tagging** for trunk ports
- Employ **Router-on-a-Stick** configuration with **sub-interfaces**
- Enable dynamic routing with **RIP (Routing Information Protocol)**

---

## 🧰 Tools & Technologies

- Cisco Packet Tracer
- Layer 2 Switches
- Layer 3 Switch
- Router (with sub-interface support)
- RIP Routing Protocol
- VLANs and Trunking (802.1Q)

---

## 🗂️ Network Design Overview

- **VLAN 10** – Computer Science Dept
- **VLAN 20** – Electrical Engineering Dept
- **VLAN 30** – Administration
- **VLAN 40** – Library
- **VLAN 99** – Management (Native VLAN)

### 🌐 Network Topology Includes:

- Multiple end devices in each department
- Inter-VLAN communication via Layer 3 switch
- RIP configuration for inter-network communication
- Trunk links between switches
- Router with sub-interfaces for VLANs

---

## ⚙️ Key Configurations

### VLAN Configuration
```bash
Switch(config)# vlan 10
Switch(config-vlan)# name CS

Switch(config)# interface fa0/1
Switch(config-if)# switchport mode access
Switch(config-if)# switchport access vlan 10
```
### Trunk Port
```bash
Switch(config)# interface fa0/24
Switch(config-if)# switchport mode trunk
Switch(config-if)# switchport trunk encapsulation dot1q
```
### Router Sub-Interfaces (Router-on-a-Stick)
```bash
Router(config)# interface g0/0.10
Router(config-subif)# encapsulation dot1Q 10
Router(config-subif)# ip address 192.168.10.1 255.255.255.0
```
### RIP Routing
```bash
Router(config)# router rip
Router(config-router)# version 2
Router(config-router)# network 192.168.0.0
```



