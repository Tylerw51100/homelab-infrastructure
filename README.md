# Home Lab Infrastructure

## Overview
This project documents my self-hosted, enterprise-style lab environment designed to simulate real-world IT infrastructure. It focuses on high availability, network segmentation, automation, and secure service delivery across a multi-node virtualized environment.

---

## Architecture Diagram

![Network Diagram](diagrams/network-overview.png)

---

## Architecture Overview

This lab is designed to replicate a small-scale enterprise environment with:

- High availability virtualization using a Proxmox cluster  
- Distributed storage using Ceph  
- VLAN-segmented network architecture for isolation and security  
- Redundant and filtered DNS infrastructure  
- Reverse proxy for centralized service access  
- Infrastructure automation using Terraform and Ansible  

---

## Core Components

### Virtualization & Compute
- 4-node Proxmox high-availability cluster  
- Virtual machines hosting Linux and Windows systems  

### Storage
- Ceph distributed storage across cluster nodes  
- TrueNAS system for backups and general NAS usage  

### Networking
- Ubiquiti UniFi-based infrastructure (gateway, switching, routing)  
- VLAN segmentation (IoT, management, VPN, storage, secure LAN, camera network)  
- Layer 3 routing implemented for performance optimization  

---

## Design Decisions

- **Layer 3 Routing for Camera VLAN**  
  Offloaded routing from the gateway to a Layer 3 switch to reduce gateway load and improve performance.

- **Ceph Distributed Storage**  
  Provides redundancy and high availability across multiple nodes.

- **Redundant DNS Architecture**  
  BIND9 master/slave configuration with AdGuard Home upstream for filtering and failover.

- **VLAN Segmentation**  
  Separates IoT, management, and user traffic to improve security and reduce lateral movement.

- **Reverse Proxy (NGINX Proxy Manager)**  
  Centralized access to internal services with simplified routing and management.

---

## Services

- DNS: BIND9 (master/slave) with AdGuard Home  
- Reverse Proxy: NGINX Proxy Manager  
- Containerized services via Docker Compose  
- VPN: NetBird (secure overlay network)  
- PXE boot server for OS deployment (netboot-xyz) 
- Self-hosted applications (password manager, notes app, VS Code server, etc.)

---

## Automation

- Infrastructure provisioning using Terraform  
- Configuration management with Ansible  
- Bash scripting and cron jobs for maintenance and task automation  

---

## Security

- VLAN-based network segmentation  
- Firewall rules and traffic isolation  
- IDS/IPS enabled on UniFi gateway  
- UFW configured on Linux virtual machines  
- Internal honeypots deployed across VLANs  

---

## What This Demonstrates

- System administration and troubleshooting  
- Network design and VLAN segmentation  
- High availability and redundancy concepts  
- Infrastructure automation (IaC + configuration management)  
- Security best practices in self-hosted environments  

---

## Notes

- All sensitive information (IPs, domains, credentials) has been sanitized  
- This project is intended for learning, experimentation, and skill development  

---

## Author

Tyler Wetherington
