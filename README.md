
# Network Design Documentation

## Overview
This document outlines the configuration and setup of the network across three floors of the building. All routers are placed in the **server room** in the **IT department**, with OSPF as the routing protocol and DHCP configured for dynamic IP allocation.

---

## 📡 **Network Infrastructure**

### 1. Router Placement
- Three routers connecting each floor, all placed in the **server room** in the IT department.
- Routers are connected using **Serial DCE cables**.
- Network addresses between routers:
  - Router 1 ↔ Router 2: `10.10.10.0/30`
  - Router 2 ↔ Router 3: `10.10.10.4/30`
  - Router 1 ↔ Router 3: `10.10.10.8/30`

---

### 2. VLAN and IP Configuration Per Floor

#### 🏢 **1st Floor**
- **Reception**: VLAN 80 – `192.168.8.0/24`
- **Store**: VLAN 70 – `192.168.7.0/24`
- **Logistics**: VLAN 60 – `192.168.6.0/24`

#### 🏢 **2nd Floor**
- **Finance**: VLAN 50 – `192.168.5.0/24`
- **HR**: VLAN 40 – `192.168.4.0/24`
- **Sales**: VLAN 30 – `192.168.3.0/24`

#### 🏢 **3rd Floor**
- **Administration**: VLAN 20 – `192.168.2.0/24`
- **HR**: VLAN 10 – `192.168.1.0/24`

---

### 3. Switch Configuration Per Floor
- **Each floor** has **one switch** connecting devices to respective VLANs.
- **WiFi Networks** on each floor are configured to connect **laptops and phones**.

---

## 🔄 **Routing Configuration**

### 4. OSPF Configuration
- Use **OSPF** as the dynamic routing protocol to advertise routes between routers.
- Area 0 is used to ensure interconnectivity between all VLANs and subnets.

---

## 📡 **DHCP Configuration**

### 5. DHCP Setup
- **All devices** in the network obtain IP addresses dynamically.
- Each router is configured as the **DHCP server** for the respective VLANs on each floor.

---

## 🔐 **Security Configuration**

### 6. SSH Configuration
- **SSH** is configured on all routers to allow secure remote login.
- Credentials are set for secure user access to routers.

---

### 7. Port Security
- **Port security** is configured in the IT department switch to restrict unauthorized devices.
- The maximum number of devices is limited per port.

---

## 🖥️ **Testing and Remote Login**

### 8. Test-PC Setup
- A **PC named Test-PC** is added in the IT department to test remote login and connectivity.
- Remote login is verified through SSH to all routers.

---

## 📄 **Configuration Summary**

### Router Configuration Highlights
- Configure router interfaces with appropriate subnet masks and IPs.
- Enable OSPF for route advertisement.
- Set up DHCP pools for each VLAN.
- Enable SSH access on all routers.
- Configure port security for critical VLANs.

### Switch Configuration Highlights
- Configure VLANs on switches as per the floor plan.
- Assign VLANs to respective ports.
- Enable port security on key ports.

---

## 📝 **Verification and Documentation**
- Verify connectivity between all devices.
- Ensure VLAN segmentation and routing is correctly configured.
- Test DHCP functionality and IP assignment.
- Validate SSH connectivity and remote login.

---

## 🛠️ **Troubleshooting and Maintenance**
- Periodic testing of SSH, DHCP, and OSPF routes.
- Review port security and access control settings.
- Monitor network traffic for anomalies.

---

✅ **End of Documentation**  
📧 For technical assistance, contact the IT department.

---

This README file provides a structured guide for configuring and maintaining the network. Let me know if you'd like assistance with configuration commands or further refinement! 😊
