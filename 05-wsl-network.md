# WSL2 Network Discovery

## Problem

WSL2 runs in a virtual network and cannot directly access SQL Server using localhost.

---

## IP Discovery

Different IP addresses were observed:

- 10.xx5.xxx.xxx → Internal DNS resolver (not usable for TCP)
- 172.xx.xx.x → Windows host gateway (correct IP)
- 172.xx.x.x → WSL internal IP

---

## Key Insight

The correct IP to connect from WSL to SQL Server is the Windows host gateway (172.19.x.x range).

---

## Test Connection

```bash
nc -zv 172.xx.xx.x 1433
