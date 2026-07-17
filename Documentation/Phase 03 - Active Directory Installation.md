# Phase 03 - Active Directory Installation

## Objective

Install Active Directory Domain Services (AD DS) on Windows Server and promote the server to a Domain Controller.

---

## Environment

| Component | Value |
|------------|-------|
| Server Name | DC01 |
| Operating System | Windows Server 2022 |
| Domain | TECHNOVA.LOCAL |
| IP Address | 192.168.100.10 |

---

## Tasks Performed

- Installed Active Directory Domain Services role
- Added DNS Server role
- Promoted server to Domain Controller
- Created new forest TECHNOVA.LOCAL
- Configured Directory Services Restore Mode (DSRM)
- Restarted server after promotion

---

## Verification

Verified that:

- Domain Controller promotion completed successfully
- Active Directory Users and Computers opened successfully
- DNS Manager installed automatically
- Server Manager reported successful deployment

---

## Key Learnings

- Active Directory provides centralized authentication.
- Every Domain Controller stores the Active Directory database.
- DNS is a mandatory dependency for Active Directory.

---

## Next Phase

Configure DNS zones and verify name resolution.