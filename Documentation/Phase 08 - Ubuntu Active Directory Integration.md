# Phase 08 – Ubuntu Active Directory Integration

## Objective

Integrate Ubuntu Server with the Windows Active Directory domain to enable centralized authentication using Kerberos and SSSD.

---

## Environment

| Component | Value |
|-----------|-------|
| Ubuntu Server | 24.04 LTS |
| Hostname | ubuntu01 |
| Domain Controller | DC01 |
| Domain | TECHNOVA.LOCAL |
| Ubuntu IP | 192.168.100.20 |
| Domain Controller IP | 192.168.100.10 |

---

## Prerequisites

- Active Directory Domain Controller configured
- DNS configured correctly
- Ubuntu Server with static IP
- Network connectivity verified

---

## Tasks Performed

### 1. Installed Required Packages

Installed the packages required for Active Directory integration.

```bash
sudo apt update

sudo apt install realmd sssd sssd-tools adcli samba-common-bin oddjob oddjob-mkhomedir packagekit krb5-user
```

---

### 2. Verified DNS Configuration

Verified Ubuntu was using the Domain Controller as its DNS server.

```bash
resolvectl status
```

Initially, the DNS search domain was missing.

Updated Netplan configuration to include:

```yaml
search:
  - technova.local
```

Applied changes:

```bash
sudo netplan apply
```

---

### 3. Verified Active Directory Discovery

Executed:

```bash
realm discover technova.local
```

Successfully discovered:

- Realm Name
- Domain Name
- Kerberos
- Active Directory
- Required packages

---

### 4. Verified Kerberos Authentication

Obtained a Kerberos ticket.

```bash
kinit Administrator
```

Verified:

```bash
klist
```

Successfully received Kerberos Ticket Granting Ticket (TGT).

---

### 5. Joined Ubuntu to Active Directory

Executed:

```bash
sudo realm join -U Administrator technova.local
```

Authenticated using the Domain Administrator password.

Ubuntu joined the Active Directory domain successfully.

---

### 6. Verified Domain Membership

Executed:

```bash
realm list
```

Output confirmed:

- TECHNOVA.LOCAL
- kerberos-member
- login policy
- SSSD client

---

### 7. Verified Domain User Resolution

Verified domain user lookup.

```bash
id Administrator@technova.local
```

Verified user database.

```bash
getent passwd 'TECHNOVA\Administrator'
```

Both commands successfully returned Active Directory user information.

---

### 8. Verified SSSD Service

Executed:

```bash
sudo systemctl status sssd
```

Confirmed:

- SSSD service active
- Authentication backend running
- Domain communication established

---

## Commands Used

```bash
realm discover technova.local

kinit Administrator

klist

realm list

id Administrator@technova.local

getent passwd 'TECHNOVA\Administrator'

sudo systemctl status sssd
```

---

## Verification

Successfully verified:

- Domain discovery
- Kerberos authentication
- Active Directory join
- Domain membership
- User resolution
- SSSD service

Ubuntu Server is now authenticated against the Active Directory domain.

---

## Screenshots

Include screenshots of:

- Netplan configuration
- resolvectl status
- realm discover
- kinit
- klist
- realm join
- realm list
- id Administrator@technova.local
- getent passwd 'TECHNOVA\Administrator'
- sudo systemctl status sssd

---

## Challenges Faced

### Problem

`realm discover technova.local`

returned:

```
No such realm found
```

### Root Cause

The DNS search domain was not configured in Netplan.

### Resolution

Added the following configuration:

```yaml
search:
  - technova.local
```

Applied the configuration using:

```bash
sudo netplan apply
```

After the DNS configuration was corrected, the domain was successfully discovered and Ubuntu joined the Active Directory domain.

---

## Key Learnings

- Configured enterprise DNS on Ubuntu.
- Integrated Linux with Windows Active Directory.
- Used Kerberos for centralized authentication.
- Configured SSSD for identity management.
- Verified Linux domain authentication using Active Directory users.

---

## Next Phase

Join a Windows 11 client machine to the TECHNOVA.LOCAL domain and verify centralized authentication.