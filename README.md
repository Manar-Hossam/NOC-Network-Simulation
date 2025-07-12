
# 🛰️ NOC Network Simulation – Cisco Packet Tracer

This project simulates a basic Network Operations Center (NOC) environment using Cisco Packet Tracer.  
It includes routing, VLANs, dynamic IP addressing, centralized monitoring, logging, configuration backups, and time synchronization.

---

## 🗺️ Network Topology

- 2 Routers: **Cairo**, **Alex**
- Switches in each region
- Multiple End Devices (PCs, Servers)
- NOC Server (`192.168.200.10`) providing:
  - DHCP
  - SNMP
  - Syslog
  - NTP
  - TFTP

---

## ✅ Implemented Features

- IP Addressing and Static Routing
- VLAN Configuration
- DHCP Server for dynamic IP allocation
- SNMP Monitoring with MIB Browser
- Syslog Server for event tracking
- NTP Time Synchronization
- TFTP Backup/Restore of router configurations
- Access Control Lists (ACLs) for basic traffic filtering

---

## 🔧 Services Configuration

### 📡 DHCP Server

- Scope: `192.168.10.0/24`
- Start IP: `192.168.10.100`
- Default Gateway: `192.168.10.1`
- Subnet Mask: `255.255.255.0`

### 🔒 Access Control List (ACL)

To block devices from network `192.168.20.0/24` from accessing the NOC server:

```bash
access-list 10 deny 192.168.20.0 0.0.0.255  
access-list 10 permit any  
interface g0/2  
ip access-group 10 out  
```

✅ **Result:** Devices in the denied network fail to ping `192.168.200.10`.

---

## ⏰ NTP Configuration

- NTP Server: `192.168.200.10`
- All routers synchronized to the same time.
- Verified using `show clock` and `show ntp associations`

---

## 🧪 SNMP Monitoring

- SNMP enabled on all routers and switches
- Tested using MIB Browser
- Example OID: `.1.3.6.1.2.1.2.2.1.10.1` (Incoming traffic on Interface 1)
- SNMP community string: `public`

---

## 🖥️ Syslog

- Syslog Server: `192.168.200.10`
- Logs router activities and interface status
- Logging command:  
```bash
logging 192.168.200.10
```

---

## 🔁 TFTP Backup & Restore

- TFTP Server IP: `192.168.200.10`
- Backup command: `copy running-config tftp`
- Restore command: `copy tftp running-config`
- Filename example: `cairo-router-backup`

---

## 🧠 Skills Demonstrated

- Network segmentation (VLANs)
- Address planning and static routing
- Service integration (DHCP, SNMP, TFTP, NTP)
- Basic security with ACLs
- Network documentation and logical thinking

---

## 📌 Notes

- Project built with **Cisco Packet Tracer**
- Some services (e.g., NTP, SNMP Walk) are **partially simulated**
- Screenshots and topology available if needed

---

## 🔗 GitHub Repository

[github.com/Manar-Hossam/NOC-Network-Simulation](https://github.com/Manar-Hossam/NOC-Network-Simulation)
