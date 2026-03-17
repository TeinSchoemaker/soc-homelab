# Cybersecurity Homelab – Wazuh SIEM Detection Lab

## 1. Overview

This project is a cybersecurity homelab built using VirtualBox to simulate a small corporate network environment. The lab includes multiple Windows and Linux systems connected within an isolated network and monitored using the Wazuh SIEM platform.

The primary goal of this project is to gain hands-on experience with:

- SIEM deployment and configuration  
- Centralized log collection  
- Security event monitoring  
- Threat detection and alert analysis  
- SOC (Security Operations Center) workflows  

This environment allows for safe testing of security scenarios and investigation of alerts in a controlled setting.

---

## 2. Lab Environment

The lab simulates a corporate infrastructure with multiple systems performing different roles:

- **homelab-dc** – Windows Server acting as Domain Controller  
- **homelab-win-client** – Windows workstation (domain joined)  
- **homelab-linux-client** – Ubuntu Linux endpoint  
- **homelab-corp-svr** – Internal corporate server  
- **homelab-sec-box** – Wazuh SIEM server  
- **homelab-sec-work** – Security workstation used for monitoring and investigation  

All machines are hosted in Oracle VirtualBox and connected through a shared internal network.

### Lab Infrastructure Screenshot

![VirtualBox Lab](screenshots/virtualbox-lab.png)

---

## 3. Network Architecture

The lab environment is designed to simulate a small enterprise network. All endpoints communicate within a VirtualBox NAT/internal network, and logs from each system are forwarded to the Wazuh SIEM server.

Each endpoint runs a **Wazuh agent**, which collects system and security logs and sends them to the central Wazuh manager for analysis.

### Network Diagram

![Network Diagram](diagrams/network-diagram.png)

---

## 4. Monitoring Setup

Wazuh is used as the central SIEM platform for this lab.

### Components

- Wazuh Server (Manager)
- Wazuh Agents on all endpoints
- Dashboard for visualization and alerting

### Configuration Steps

- Installed Wazuh server on `homelab-sec-box`
- Deployed Wazuh agents on all Windows and Linux machines
- Configured agents to forward logs to the Wazuh server
- Verified connectivity between agents and server

### Monitored Data

Windows systems:

- Security Event Logs  
- Authentication events  
- Process activity  

Linux systems:

- Authentication logs  
- System logs  
- Audit events  

### Wazuh Agent Status

![Wazuh Agents](screenshots/wazuh-agents.png)

---