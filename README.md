# Azure Hybrid Network Lab  
**BGP over IPsec (IKEv2/VTI) + OSPF (LAN)**

---

## 📌 Overview

This project demonstrates a **hybrid network architecture between Azure and on-premises infrastructure**, using:

- IPsec (IKEv2 / VTI)
- BGP (Azure ↔ pfSense)
- OSPF (LAN routing)
- End-to-end connectivity validation
- Real-world troubleshooting scenario

---

## 🧠 Architecture

<p align="center">
  <img src="architecture/diagram.png" width="700">
</p>

---

## ⚙️ Technologies Used

- Azure Virtual Network (VNet)
- pfSense (IPsec + FRR BGP)
- FRRouting (BGP / OSPF)
- Windows Server / Client
- Ubuntu Server
- tcpdump (packet analysis)

---

## 🔗 Routing Design

- **BGP** used between Azure and pfSense (dynamic routing over IPsec)
- **OSPF** used internally between pfSense and LAN router
- No static routes between environments

---

## 🔐 IPsec Tunnel

- IKEv2 with VTI
- AES-256 encryption
- SHA256 authentication
- Stable tunnel with continuous traffic flow

---

## 🌐 End-to-End Connectivity

- LAN → Azure VM connectivity validated
- Azure → LAN connectivity validated
- ICMP tests confirm bidirectional communication

---

## 🧪 Troubleshooting Scenario

A real issue was identified and resolved:

- ICMP traffic entering IPsec tunnel
- No return traffic
- Root cause: routing propagation issue
- Fix: corrected route advertisement (BGP/OSPF alignment)

📂 Details:  
👉 `troubleshooting/`

---

## 📸 Screenshots

See full lab validation:  
👉 `screenshots/`

---

## 🚀 Key Takeaways

- Dynamic routing is critical in hybrid environments  
- IPsec alone is not enough — routing must be correct  
- Troubleshooting skills are as important as configuration  

---

## 👤 Author

Hands-on lab focused on **real-world hybrid networking, not theory**.
