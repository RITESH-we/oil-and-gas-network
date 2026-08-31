# 🛢️ Resilient 5-Zone Oil and Gas Network Architecture

A secure, segmented 5-zone network architecture designed for oil and gas industrial environments. Built to protect critical Industrial Control Systems (ICS) and Operational Technology (OT), this design isolates sensitive field zones while enabling central oversight through a Secure Operations center.

---

## 🏗️ Architectural Zones & Subnetting Scheme

| Zone | VLAN ID | Subnet | Gateway IP | Key Components |
|---|---|---|---|---|
| **Secure Operations** | VLAN 10 | `192.168.10.0/24` | `192.168.10.1` | SCADA Servers, Data Historian, SIEM, NMS, Jump Server |
| **Control Zone** | VLAN 20 | `192.168.20.0/24` | `192.168.20.1` | HMIs, Historian Databases, Industrial Control Servers |
| **Enterprise Zone** | VLAN 30 | `192.168.30.0/24` | `192.168.30.1` | Corporate IT (Finance, HR, IT, Marketing) |
| **Field Zone** | VLAN 40 | `192.168.40.0/24` | `192.168.40.1` | PLCs, Pressure/Temp/Flow/Gas Sensors, Actuators |
| **DMZ** | VLAN 50 | `192.168.50.0/24` | `192.168.50.1` | Web, Email, DNS, FTP, Reverse Proxy Servers |

---

## ✨ Features

✅ Multi-zone OT/IT isolation aligned with Purdue Model security principles  
✅ Real-time process monitoring via field PLCs, sensors, and actuators  
✅ Firewall Access Control Lists (ACLs) restricting cross-zone traffic  
✅ Centralized SCADA management and SIEM/NMS oversight in Secure Ops  
✅ Fully integrated Cisco Packet Tracer simulation ready for deployment  
✅ Extensible switch CLI configuration scripts and cost documentation  

---

## 📁 Repository Structure

```text
.
├── configs/
│   ├── core_switch.cfg       # Core switch VLAN and routing configurations
│   └── firewall_acls.cfg     # Inter-zone firewall Access Control Lists
├── docs/
│   └── cost_analysis.md      # Network infrastructure cost breakdown
├── simulation/
│   └── topology.pkt          # Cisco Packet Tracer master network model
├── .gitignore
├── LICENSE
└── README.md
