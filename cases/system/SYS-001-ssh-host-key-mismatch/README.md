# SYS-001 — SSH Host Key Mismatch

**Environment:** Hands-on lab (Windows PowerShell + Ubuntu VM)  
**Focus:** SSH host identity, known_hosts, cloud-init logs  
**Status:** Resolved

## Issue

An SSH connection from Windows to Ubuntu Node A (`192.168.1.55`) failed with:

```text
WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED!
Host key verification failed.
```

The saved host key did not match the server's current ED25519 host key.

## Investigation

| Check | Evidence / Finding |
|---|---|
| SSH client | Host key mismatch reported in `known_hosts` |
| Ubuntu server | Verified the current ED25519 host key fingerprint directly on Node A |
| Provisioning logs | cloud-init logs showed SSH host keys were removed and regenerated during initial boot on Sep 23 |

**Verified server fingerprint:**

```text
SHA256:3WM30nAls9lWCT4HZmzAZjkmDQcbbThOc0DZ+39RgoY
```

**Diagnosis:** The client's saved host key differed from the current server key. cloud-init confirmed host-key regeneration during provisioning, but the exact origin of the older saved key was not established.

## Fix & Verification

After independently verifying Node A's current fingerprint:

```powershell
ssh-keygen -R 192.168.1.55
ssh nam@192.168.1.55
```

- Removed the outdated `known_hosts` entry.
- Accepted the verified current host key.
- SSH connection succeeded.

**Result:** SSH access restored without disabling host key verification.

---

*Evidence: Commands and log inspection were performed in a personal VirtualBox lab. This was not a production incident.*