# Phase 07 – Ubuntu Server Installation

## Objective

Deploy Ubuntu Server 24.04 as an enterprise Linux server that will later be integrated with the Active Directory domain.

---

## Environment

| Component | Value |
|-----------|-------|
| Virtualization Platform | Oracle VirtualBox |
| Operating System | Ubuntu Server 24.04 LTS |
| Hostname | ubuntu01 |
| Network Adapter 1 | NAT |
| Network Adapter 2 | Internal Network (technova.local)|
| Static IP Address | 192.168.100.20/24 |
| DNS Server | 192.168.100.10 |
| Domain | TECHNOVA.LOCAL |

---

## Prerequisites

- Windows Server 2022 Domain Controller (DC01)
- Active Directory configured
- DNS service running
- Internal Network created in VirtualBox

---

## Tasks Performed

### 1. Created Ubuntu Virtual Machine

- Created a new Ubuntu Server virtual machine in VirtualBox.
- Allocated CPU, RAM and storage resources.
- Attached Ubuntu Server ISO.

---

### 2. Installed Ubuntu Server

Completed the installation wizard by configuring:

- Language
- Keyboard Layout
- Storage
- User Account
- Hostname (ubuntu01)

---

### 3. Configured Network

Configured two network adapters.

Adapter 1

- NAT
- Internet connectivity

Adapter 2

- Internal Network
- Communication with Domain Controller

---

### 4. Assigned Static IP Address

Configured Netplan.

Static IP:

192.168.100.20/24

DNS Server:

192.168.100.10

Search Domain:

TECHNOVA.LOCAL

---

### 5. Applied Network Configuration

Executed:

```bash
sudo netplan apply
```

Verified:

```bash
ip addr
ip route
resolvectl status
```

---

### 6. Verified Connectivity

Successfully tested communication with:

- Domain Controller
- DNS Server
- Internet

---

## Verification

Verified:

- Static IP assigned successfully
- DNS server configured
- Internet connectivity available
- Internal network reachable

---

## Screenshots

- Ubuntu installation
- Network Adapter configuration
- Netplan configuration
- IP address
- Routing table
- DNS configuration

---

## Key Learnings

- Installed Ubuntu Server in a virtualized environment.
- Configured dual-network adapters for enterprise networking.
- Learned static IP configuration using Netplan.
- Verified network connectivity before domain integration.

---

## Next Phase

Join Ubuntu Server to the Active Directory domain.