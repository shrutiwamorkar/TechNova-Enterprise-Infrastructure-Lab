# Phase 04 - DNS Configuration

## Objective

Configure DNS service required by Active Directory.

---

## Tasks Performed

- Verified Forward Lookup Zone
- Verified Reverse Lookup Zone
- Confirmed SRV records
- Verified host (A) records
- Tested DNS resolution

---

## Verification

Executed:

nslookup

Resolve-DnsName

ping dc01

Confirmed successful name resolution.

---


## Key Learnings

- Active Directory relies heavily on DNS.
- Domain joining fails if DNS is incorrectly configured.
