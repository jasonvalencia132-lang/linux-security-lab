# Linux Security Lab (Ubuntu Server)

## Objective
Build a minimal Ubuntu Server environment and configure secure remote access
to practice real-world Linux and security administration tasks.

This lab focuses on:
- Server installation (no GUI)
- Secure SSH access
- Basic system hardening
- Understanding networking and firewalls

---

## Environment
- Host OS: Windows
- Virtualization: VirtualBox
- Guest OS: Ubuntu Server (LTS)
- Access Method: SSH
- Network Mode: NAT with port forwarding

---

## Architecture / Setup
- Ubuntu Server installed in a VirtualBox VM
- GUI packages removed to simulate a headless server
- SSH server enabled
- UFW firewall enabled
- NAT port forwarding:
  - Host: `127.0.0.1:2222`
  - Guest: `:22`

---

## Security Decisions
- Removed graphical desktop to reduce attack surface
- Enabled UFW firewall
- Allowed only SSH traffic
- Disabled root login over SSH
- Managed system remotely using SSH instead of console access

---

## How to Reproduce
1. Create a new Ubuntu Server VM in VirtualBox
2. Install OpenSSH during setup
3. Enable firewall:
   ```bash
   sudo ufw enable
   sudo ufw allow ssh
