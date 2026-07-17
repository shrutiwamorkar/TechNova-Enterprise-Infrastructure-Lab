# TechNova Enterprise Infrastructure Lab

## Overview

This project demonstrates the deployment of a complete enterprise infrastructure using Windows Server 2022, Ubuntu Server 24.04, Active Directory Domain Services, DNS, DHCP, Group Policy, Linux administration, and VirtualBox.

The objective is to simulate a production enterprise environment while documenting every configuration step, troubleshooting activity, and best practice.

---

## Technologies Used

- Windows Server 2022
- Ubuntu Server 24.04
- Active Directory Domain Services
- DNS
- DHCP
- Group Policy
- VirtualBox
- PowerShell
- Bash
- VS Code
- Git & GitHub

---

## Infrastructure
## Infrastructure

```mermaid
flowchart TB

    Internet((Internet))
    Router[Home Router]

    Router --> VBox

    subgraph VirtualBox["Oracle VirtualBox"]

        NAT["NAT Network Adapter"]

        Ubuntu["Ubuntu01<br/>Ubuntu Server 24.04 LTS<br/>IP: 192.168.100.20"]

        NAT --> Ubuntu

        Ubuntu --> Internal

        subgraph Internal["Internal Network"]

            DC["DC01<br/>Windows Server 2022<br/>192.168.100.10<br/>AD DS<br/>DNS"]

            Client["Windows Client<br/>Phase 09"]

        end

        Internal --> DC
        Internal --> Client

    end

    Internet --> Router
```

## Documentation

- Phase 01 – Environment Preparation
- Phase 02 – Windows Server Installation
- Phase 03 – Active Directory Installation
- Phase 04 – DNS Configuration
- Phase 05 – Organizational Units & Users
- Phase 06 – Group Policy
- Phase 07 – Ubuntu Server Installation
- Phase 08 – Ubuntu Active Directory Integration
- Phase 09 – Windows Client Domain Join
- Phase 10 – File Server
- Phase 11 – DHCP Server
- Phase 12 – Backup & Recovery

---

## Skills Demonstrated

- Active Directory Administration
- DNS Management
- Linux Administration
- Windows Server Administration
- Kerberos Authentication
- Identity Management
- Group Policy
- Virtualization
- Infrastructure Documentation
- Troubleshooting
- Git Version Control

---

## Current Progress

- [x] Environment Preparation
- [x] Windows Server Installation
- [x] Active Directory Installation
- [x] DNS Configuration
- [x] Organizational Units
- [x] Group Policy
- [x] Ubuntu Installation
- [x] Ubuntu Domain Join
- [ ] Windows Client Join
- [ ] File Server
- [ ] DHCP
- [ ] Backup
