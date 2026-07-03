# Day 02 – Windows Server Installation & Initial Configuration

**Project:** TechNova Enterprise Platform  
**Server:** DC01  
**Date:** 03 July 2026

---

# Objective

Deploy the first Windows Server virtual machine and prepare it for Active Directory installation.

---

# Virtual Machine Configuration

| Setting | Value |
|----------|-------|
| Platform | Oracle VirtualBox |
| VM Name | DC01 |
| Operating System | Windows Server 2022 Standard Evaluation |
| Edition | Desktop Experience |
| RAM | 3072 MB |
| CPU | 2 vCPUs |
| Disk Type | VDI |
| Disk Allocation | Dynamically Allocated |
| Disk Size | 60 GB |

---

# Network Configuration

| Setting | Value |
|----------|-------|
| Network Mode | NAT |
| IP Address | 10.0.2.10 |
| Subnet Mask | 255.255.255.0 |
| Default Gateway | 10.0.2.2 |
| Preferred DNS | 192.168.0.1 *(Temporary)* |

---

# Server Configuration

| Setting | Value |
|----------|-------|
| Computer Name | DC01 |
| Time Zone | (UTC+05:30) Chennai, Kolkata, Mumbai, New Delhi |

---

# Lab Credentials

Username:
Administrator

Password:
TechNova@2026

> ⚠️ Lab use only. Never store production passwords in plain text.

---

# Concepts Learned

## Windows Server vs Windows 11

Windows Server is designed to provide services such as Active Directory, DNS, DHCP, File Services, and centralized administration, whereas Windows 11 is designed for end users.

---

## Standard vs Datacenter

- Standard → Suitable for most organizations and learning environments.
- Datacenter → Includes advanced virtualization and enterprise features for very large environments.

---

## Desktop Experience vs Server Core

Desktop Experience provides a graphical user interface (GUI).

Server Core provides the same server functionality but is managed primarily through PowerShell and remote administration.

---

## Why Static IP?

A Domain Controller should always use a static IP address because clients must always know where to find authentication and DNS services.

---

## Dynamic vs Fixed Disk

Dynamic disks consume only the storage actually used.

Fixed disks reserve the full size immediately.

Dynamic disks are ideal for home labs.

---

## VDI vs VHD

- VDI → Native VirtualBox format.
- VHD → Microsoft Hyper-V format.

---

# Tasks Completed

- ✅ Created DC01 Virtual Machine
- ✅ Installed Windows Server 2022
- ✅ Configured Administrator account
- ✅ Renamed server to DC01
- ✅ Configured Time Zone
- ✅ Configured Static IP
- ✅ Verified configuration after reboot

---

# Current Architecture

Internet
│
Home Router
│
VirtualBox NAT
│
DC01 (10.0.2.10)

---

# Next Session

- Install Active Directory Domain Services (AD DS)
- Promote DC01 to Domain Controller
- Create TECHNOVA.LOCAL
- Configure DNS

---

# Key Takeaway

Windows Server is only an operating system.

Installing the Active Directory Domain Services role transforms it into a Domain Controller capable of authenticating users, managing computers, and providing enterprise identity services.
