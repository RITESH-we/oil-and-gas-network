**# Resilient 5-Zone Oil and Gas Network Architecture**



**## Project Overview**

**This repository contains the design, network topology, and configuration scripts for a resilient five-zone network architecture tailored for oil and gas industrial environments. Designed to protect critical Industrial Control Systems (ICS) and Operational Technology (OT), the architecture isolates sensitive zones while enabling central oversight through a Secure Operations (Secure Ops) center.**



**## Architectural Zones**

**\* \*\*Secure Operations (Secure Ops):\*\* Central nerve center housing SCADA servers, Data Historian, SIEM, NMS, and Jump Server.**

**\* \*\*Control Zone:\*\* Enforces real-time control of industrial processes via HMIs, Historian Databases, and Industrial Control Servers.**

**\* \*\*Field Zone:\*\* Geographically distributed site housing PLCs, Sensors (Pressure, Temp, Flow, Gas), and Actuators\[cite: 1].**

**\* \*\*Enterprise Zone:\*\* Corporate IT infrastructure segmented by department (Finance, HR, IT, Marketing)\[cite: 1].**

**\* \*\*Demilitarized Zone (DMZ):\*\* External buffer hosting public-facing Web, Email, DNS, FTP, and Reverse Proxy servers\[cite: 1].**



**## Network Addressing \& VLAN Scheme**

**The prototype implementation utilizes private Class C subnets across five primary VLANs\[cite: 1]:**



**| Zone | VLAN ID | Subnet | Gateway IP |**

**| :--- | :--- | :--- | :--- |**

**| Secure Ops | VLAN 10 | `192.168.10.0/24` | `192.168.10.1` |**

**| Control Zone | VLAN 20 | `192.168.20.0/24` | `192.168.20.1` |**

**| Enterprise Zone | VLAN 30 | `192.168.30.0/24` | `192.168.30.1` |**

**| Field Zone | VLAN 40 | `192.168.40.0/24` | `192.168.40.1` |**

**| DMZ | VLAN 50 | `192.168.50.0/24` | `192.168.50.1` |**



**## Deployment \& Simulation Setup**

**1. Download \[Cisco Packet Tracer](https://www.netacad.com/courses/packet-tracer).**

**2. Clone this repository to your local machine:**

&#x20;  **```bash**

&#x20;  **git clone \[https://github.com/Ritesh-we/oil-and-gas-network.git](https://github.com/RITESH-we/oil-and-gas-network.git)**

