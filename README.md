# Network-Design-and-Architecture-Using-Netsim
A multi-site enterprise network simulation using Tetcos NetSim modelling Cape Town, Singapore, Buenos Aires, and NOC. It analyses LAN/WAN performance, subnetting, application behaviour, and real-time tools like MS Teams and Zoom, identifying bottlenecks and optimising network efficiency.


# 🌐 Global Enterprise Network Simulation (Tetcos NetSim)

A multi-site enterprise network simulation modelling real-world communication between headquarters and regional offices using **Tetcos NetSim**.  
This project analyses application behaviour, subnet design, WAN/LAN performance, and real-time communication systems under varying network conditions.

---

## 📌 Project Overview

This simulation represents a global organisation with four major sites:

- 🏢 Cape Town (Headquarters – South Africa)
- 🌏 Singapore (Asia-Pacific Office)
- 🌎 Buenos Aires (South America Office)
- 🖥 Network Operations Centre (NOC)

The network supports enterprise applications such as:

- Email (TCP-based communication)
- FTP & Database services
- Web browsing & OneDrive (Cloud storage)
- MS Teams & Zoom (Real-time voice/video communication)

The objective is to evaluate **performance, scalability, and bottlenecks** across LAN and WAN environments.

---

## 🧠 Key Objectives

- Design a hierarchical multi-site enterprise network
- Implement subnetting using private IP ranges
- Simulate real-world application traffic in NetSim
- Analyse LAN vs WAN performance differences
- Evaluate real-time communication behaviour (Teams vs Zoom)
- Identify network bottlenecks and optimise performance
- Study scalability under increased user load

---

## 🏗 Network Design Architecture

### 🏢 Cape Town (Core Headquarters)
- Segmented into:
  - CEO Zone
  - Server Zone
  - Employee Zone
- Two logical firewall layers (switch-based emulation)
- High-speed LAN (5 ms delay)
- Central application hosting (Mail, DB, File servers)

---

### 🌏 Singapore Office
- 5 office users + 10 remote users (WFH)
- Printer + Email services
- MS Teams & Zoom integration
- Hybrid wired + wireless design
- LAN delay: 5 ms | WAN delay: 20 ms

---

### 🌎 Buenos Aires Office
- 5 local users + remote workers
- Strong focus on collaboration (Teams/Zoom)
- QoS-enabled voice traffic (G.729 / G.7211)
- LAN delay: 2 ms | WAN delay: 10 ms

---

### 🖥 NOC (Network Operations Centre)
- 5 users + printer system
- Central monitoring & coordination hub
- Direct communication with all offices
- LAN delay: 5 ms | WAN delay: 10 ms

---

## 🌐 IP Addressing & Subnetting

A hybrid private addressing scheme was used:

| Site | Subnet | Class | Purpose |
|------|--------|-------|---------|
| Cape Town | 192.168.20.0/24 | Class C | HQ LAN |
| Singapore | 192.168.40.0/24 | Class C | Regional Office |
| Buenos Aires | 192.168.30.0/24 | Class C | Regional Office |
| NOC | 172.16.10.0/29 | Class B | Monitoring Hub |
| WAN Links | 172.16.x.x /30 | Class B | Point-to-point links |

### Design Principles
- Efficient IP allocation
- WAN isolation using /30 subnets
- Scalability for future expansion
- Logical segmentation for security & performance

---

## 📊 Performance Analysis

### 📧 Email Traffic (LAN vs WAN)
- LAN: stable, low delay, consistent throughput
- WAN: bursty traffic with higher overhead
- WAN load significantly higher due to routing complexity

---

### ☁️ OneDrive / HTTP File Download
- Average download time: **~21.97 seconds**
- Delay caused by:
  - WAN propagation latency
  - TCP congestion control
  - Packet fragmentation

---

### 🌐 Web Server Performance
- Server response time: negligible
- End-user delay dominated by WAN transmission
- Network = primary performance bottleneck

---

## 🎧 Real-Time Applications

### MS Teams (CBR)
- Stable bitrate
- Low jitter
- Predictable performance

### Zoom (VBR)
- Variable bitrate
- Burst traffic behaviour
- Higher jitter but adaptive quality

👉 Conclusion:  
Teams = stability | Zoom = adaptability

---

## ⚠️ Bottleneck Analysis

Identified issues:
- High WAN propagation delay (up to 100 ms)
- Packet collisions on backbone links
- Queue congestion under heavy load
- Reduced throughput stability

---

## 🚀 Expansion Scenario

Added load:
- +4 users (Buenos Aires)
- +3 users (Singapore)
- Increased MS Teams & Zoom traffic

### Outcome:
- Higher WAN utilisation
- Increased jitter in Zoom
- Teams remained stable
- Backbone link became critical load point

---

## 🔧 Optimisation & Improvements

### Changes Applied:
- Reduced WAN delay from 100 ms → 30 ms
- Adjusted link propagation parameters

### Results:
- ❌ Packet errors eliminated
- 📈 Throughput improved
- 📉 Jitter reduced
- ⚡ Network stability increased

---

## 📈 Key Findings

- LAN networks are stable and predictable
- WAN links introduce delay and jitter
- Backbone is the most critical performance area
- CBR traffic is more stable than VBR traffic
- Small configuration changes significantly impact performance

---

## 🧾 Conclusion

This simulation demonstrates the behaviour of a real-world global enterprise network under realistic traffic conditions.

It highlights how:

- Distance impacts performance
- Application type shapes network behaviour
- WAN links define system limitations
- Optimization transforms instability into controlled flow

> A network is not just connections — it is behaviour shaped by distance, design, and discipline.

---

## 🛠 Tools Used

- Tetcos NetSim
- Network Simulation Models
- TCP/IP Traffic Analysis
- Application Layer Modelling

---

## 📌 Author

**Muhammed**  
Network Simulation & Cybersecurity Enthusiast  
