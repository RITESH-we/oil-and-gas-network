# 🛢️ Resilient 5-Zone Oil and Gas Network Architecture

[![Cisco Packet Tracer](https://img.shields.io/badge/Simulator-Cisco%20Packet%20Tracer-005073?logo=cisco&logoColor=white)](https://www.netacad.com/courses/packet-tracer)
[![Architecture](https://img.shields.io/badge/Design-Purdue%20Model%20ICS/OT-red)](./configs/firewall_acls.cfg)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](./LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://github.com/RITESH-we/oil-and-gas-network/pulls)

A resilient five-zone network architecture designed for oil and gas industrial environments. Engineered around Purdue Model principles to protect critical Industrial Control Systems (ICS) and Operational Technology (OT), this architecture isolates sensitive zones while enabling central oversight through a Secure Operations (Secure Ops) center.

---

## 🏗️ Architecture

```text
                                [ 🌐 EXTERNAL / INTERNET ]
                                            │
                                            ▼
┌────────────────────────────────────────────────────────────────────────────────────────┐
│ 🛡️ DEMILITARIZED ZONE (DMZ) | VLAN 50                                                 │
│ [ Web Server ]     [ Email Server ]     [ DNS ]     [ FTP ]     [ Reverse Proxy ]      │
└───────────────────────────────────────┬────────────────────────────────────────────────┘
                                        │ (Firewall ACLs)
                                        ▼
┌────────────────────────────────────────────────────────────────────────────────────────┐
│ 🏢 ENTERPRISE ZONE | VLAN 30                                                           │
│ [ Finance Dept ]         [ HR Workstations ]         [ IT / Marketing ]                │
└───────────────────────────────────────┬────────────────────────────────────────────────┘
                                        │ (Inter-VLAN Routing)
                                        ▼
┌────────────────────────────────────────────────────────────────────────────────────────┐
│ ⚙️ SECURE OPERATIONS CENTER (SECURE OPS) | VLAN 10                                     │
│ [ SCADA Server ]     [ Data Historian ]     [ SIEM ]     [ NMS ]     [ Jump Server ]   │
└───────────────────────────────────────┬────────────────────────────────────────────────┘
                                        │ (Enforced Jump Host Protocol)
                                        ▼
┌────────────────────────────────────────────────────────────────────────────────────────┐
│ 🎮 CONTROL ZONE | VLAN 20                                                              │
│ [ HMIs ]             [ Historian Databases ]          [ Industrial Control Servers ]   │
└───────────────────────────────────────┬────────────────────────────────────────────────┘
                                        │ (Modbus / OT Protocols)
                                        ▼
┌────────────────────────────────────────────────────────────────────────────────────────┐
│ ⚡ FIELD ZONE | VLAN 40                                                                │
│ [ PLCs ]             [ Sensors (Pressure, Temp, Flow, Gas) ]         [ Actuators ]     │
└────────────────────────────────────────────────────────────────────────────────────────┘
oil-and-gas-network/
│
├── 📂 configs/
│   ├── core_switch.cfg       # Core L3 switch VLAN and routing configurations
│   └── firewall_acls.cfg     # Inter-zone firewall rules & Access Control Lists
│
├── 📂 docs/
│   └── cost_analysis.md      # Financial breakdown and hardware selection report
│
├── 📂 simulation/
│   └── topology.pkt          # Cisco Packet Tracer master simulation file
│
├── .gitignore
├── LICENSE
└── README.md
