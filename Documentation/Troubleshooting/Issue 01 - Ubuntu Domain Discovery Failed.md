# Issue 01 - Ubuntu Domain Discovery Failed

## Phase

Phase 08 – Ubuntu Active Directory Integration

---

## Problem

Ubuntu Server was unable to discover the Active Directory domain.

Command executed:

```bash
realm discover technova.local
```

Output:

```text
realm: No such realm found: technova.local
```

---

## Symptoms

- Active Directory domain could not be discovered.
- Domain join could not proceed.
- `realm discover` returned an error.

---

## Root Cause

Although the Domain Controller was configured as the DNS server, the DNS search domain was missing from the Netplan configuration. Because of this, Ubuntu could not resolve the Active Directory DNS records.

---

## Resolution

Edited the Netplan configuration:

```bash
sudo nano /etc/netplan/50-cloud-init.yaml
```

Added the search domain:

```yaml
nameservers:
  addresses:
    - 192.168.100.10
  search:
    - technova.local
```

Applied the configuration:

```bash
sudo netplan apply
```

---

## Verification

Executed:

```bash
realm discover technova.local
```

The command successfully returned the Active Directory domain information.

---

## Lesson Learned

Linux Active Directory integration depends heavily on proper DNS configuration. A missing DNS search domain can prevent realm discovery even when the DNS server is correctly configured.