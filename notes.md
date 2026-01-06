# Engineering Notes — Linux Security Lab

---

## Session: Initial Server Setup
**Date:** 2026-01-05  
**Goal:** Install Ubuntu Server and enable secure SSH access

### What Broke
- SSH connection from Windows timed out
- GUI removal caused the system to appear frozen

### Investigation
- Verified SSH service was running
- Confirmed firewall rules allowed port 22
- Realized VM was using NAT networking
- Learned NAT does not allow inbound connections by default

### Fix
- Added VirtualBox NAT port forwarding:
  - Host port 2222 → Guest port 22
- Connected using:
  ```bash
  ssh -p 2222 student@127.0.0.1
