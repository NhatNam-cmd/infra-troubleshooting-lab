# NET-001 — Incorrect Default Gateway

**Environment:** Simulated incident (N08)  
**Focus:** IPv4 connectivity, gateway diagnosis, service verification  
**Status:** Resolved in simulation

## Issue

PC-A (`192.168.10.10/24`) could not access an internal application at `10.10.20.50`. PC-B on the same subnet worked normally.

Expected gateway: `192.168.10.1`.

## Investigation

Initial hypotheses:
- Incorrect default gateway on PC-A.
- Cable or access-switch port issue.

| Check | Evidence | Finding |
|---|---|---|
| PC-A IP configuration | `ipconfig`: gateway `192.168.10.254` | Incorrect gateway |
| Switchport status | Fa0/3: `connected`, VLAN 10 | Physical link issue less likely |
| Reference workstation | PC-B could access the server | General outage less likely |

**Diagnosis:** PC-A's default gateway did not match the documented router address.

## Fix & Verification

**Fix:** Changed PC-A's gateway from `192.168.10.254` to `192.168.10.1`.

**Post-fix checks:**
- Ping `192.168.10.1` — Success
- Ping `10.10.20.50` — Success
- `curl http://10.10.20.50:8080/health` — HTTP `200 OK`, `{"status":"healthy"}`

**Result:** Connectivity and application health check restored in the simulation. No real-user confirmation was performed.

---

*Evidence note: Diagnostic outputs and fix results were provided by an AI-guided simulation. Hypotheses, test selection, and corrective action were proposed during the exercise; no real devices were modified.*