# Issue 02 - Domain User Lookup Failed

## Phase

Phase 08 – Ubuntu Active Directory Integration

---

## Problem

After successfully joining Ubuntu to the Active Directory domain, the following command failed:

```bash
id Administrator
```

Output:

```text
id: 'Administrator': no such user
```

---

## Symptoms

- Active Directory user could not be found.
- User lookup failed despite successful domain join.

---

## Root Cause

The system was configured to use Fully Qualified Domain Names (FQDN) for Active Directory users. Using only the username was insufficient.

---

## Resolution

Verified the configured login format:

```bash
realm list
```

Output:

```text
login-formats: %U@technova.local
```

Used the correct format:

```bash
id Administrator@technova.local
```

Verified user information:

```bash
getent passwd 'TECHNOVA\Administrator'
```

---

## Verification

Both commands successfully returned the Active Directory user information, confirming that SSSD and Kerberos authentication were working correctly.

---

## Lesson Learned

Always verify the configured login format after joining a Linux system to an Active Directory domain. Different environments may require fully qualified usernames for authentication and user lookup.