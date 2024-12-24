## 📘 Course Details
- **Course Code:** COM204  
- **Course Name:** Computer Networks  
- **Instructor:** Prof. Mahmoud Elmesalawy  
- **Teaching Assistant:** Eng. Adham Ehab  
- **Academic Year:** 2024/2025  

## 👨‍🎓 Student Info
- **Name:** Amr Yasser Badr  
- **Student ID:** 932230126  

---

## 🧠 Project Objective

The goal of this project is to design a scalable and secure computer network for **Helwan National University**.  
In **Phase 1**, the network connects the following four buildings:

1. Administration Building  
2. Faculty of Engineering  
3. Faculty of Computer Science and Information Technology  
4. Faculty of Medicine  

The network ensures:
- Reliable communication between buildings  
- Proper subnetting and IP management  
- Use of VLANs for traffic segmentation  
- Dynamic routing (RIP) and secure remote access via Telnet  

---

## 🏗️ Network Topology

The network was simulated using **Cisco Packet Tracer** with the following components:

- **4 Routers:** One per building  
- **4 Switches:** Cisco 2960-24TT  
- **24 PCs:** Represent departments within faculties (e.g., HR, IT, Student Affairs)  
- **VLANs:** Used to segment traffic by department  
- **Remote Access:** Configured using Telnet  
- **Routing:** Implemented using a mix of RIP and static routes  

---

## 🧩 Network Features

### ✅ Subnetting

- Used **VLSM** to minimize IP waste
- Each department has its own subnet

### ✅ VLAN Configuration

| Department         | VLAN ID | Purpose                      |
|--------------------|---------|------------------------------|
| Human Resources    |   10    | Isolated HR VLAN             |
| IT Department      |   20    | For technical/IT devices     |
| Student Affairs    |   30    | For student service systems  |

---

## 🧮 Subnetting Example

| Building / Department           | VLAN ID | Subnet         | Subnet Mask       | Host Range             | Broadcast Address   |
|----------------------------------|---------|----------------|-------------------|-------------------------|---------------------|
| Admin - HR                       | 10      | 10.0.0.0/26    | 255.255.255.192   | 10.0.0.1 - 10.0.0.62     | 10.0.0.63           |
| Engineering - IT                | 20      | 10.0.0.64/26   | 255.255.255.192   | 10.0.0.65 - 10.0.0.126   | 10.0.0.127          |
| CSIT - Student Affairs          | 30      | 10.0.0.128/26  | 255.255.255.192   | 10.0.0.129 - 10.0.0.190  | 10.0.0.191          |
*(These are examples, actual ranges may vary in Packet Tracer project.)*

---

## 🔧 Sample Router Configuration

```bash
Router> enable
Router# configure terminal
Router(config)# hostname Amr-Yasser-CS
Router(config)# enable password 123

Router(config)# interface gigabitEthernet 0/0
Router(config-if)# ip address 192.168.1.62 255.255.255.192
Router(config-if)# no shutdown

Router(config)# interface gigabitEthernet 0/4
Router(config-if)# ip address 12.0.0.2 255.255.255.0
Router(config-if)# no shutdown
```
## 🧪 Testing

To ensure the network functions correctly, the following tests were performed:

- ✅ **Ping** between buildings (inter-router communication)  
- ✅ **Ping** between departments in different VLANs (with routing)  
- ✅ **Telnet** access to routers and switches using the designated management IPs  
- ✅ **DHCP** address assignment tested for all PCs  
- ✅ **Routing protocol (RIP)** checked using `show ip route`

---

## 🚧 Challenges & Solutions

| **Challenge**              | **Solution**                                                   |
|---------------------------|-----------------------------------------------------------------|
| VLAN misconfiguration     | Reassigned ports and double-checked VLAN IDs                   |
| Routing table errors      | Used `show ip route` and ensured correct RIP settings          |
| IP address conflicts      | Applied DHCP and restructured the subnetting plan              |
| Telnet issues             | Verified line configurations and access-lists (if any)         |

---

## ✅ Conclusion

This project successfully delivers a foundational network for Helwan National University that includes:

- 🔗 Interconnected buildings with dynamic routing  
- 🧩 Logical traffic separation using VLANs  
- 📊 Efficient IP usage with VLSM  
- 🔐 Remote access for management via Telnet  

The network is fully functional and ready for future expansion to include the remaining faculties on campus.

---

## 📎 Files Included

- `Project.pkt` – Cisco Packet Tracer file with full topology  
- `Documentation.pdf` – Full written report with diagrams and configurations  
- `README.md` – Project overview and technical explanation  

---

> Created by **Amr Yasser Badr**
