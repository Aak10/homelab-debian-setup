# Phase 1: Debian Base Setup

## Objective
Set up a clean Debian installation for your homelab, including:
- System updates
- User creation
- SSH access
- Firewall setup

---
## First we have installed the debian 13 with xfce Gui on our old laptop 
It was a full linux installation on our device.
Having 250gb ssd was a plus 

## Commands to Run on Laptop
```bash
# Update system
sudo apt update && sudo apt upgrade -y

# Install essential packages
sudo apt install -y curl wget git vim htop net-tools ufw openssh-server ca-certificates lsb-release apt-transport-https gnupg

# Create user
No user was created.
so worked only as root.

# Enable SSH
sudo systemctl enable ssh
sudo systemctl start ssh

# Enable firewall
sudo ufw allow OpenSSH
sudo ufw enable

# Reboot system
sudo reboot

change in plan
### Why create a non-root user?

Running everything as `root` is unsafe and untraceable. 
Creating a dedicated sudo user (e.g. `akash`) provides:
- Safer permission boundaries
- Clear audit logs
- Easier SSH hardening

## Verify sudo user
Check existing user and sudo access:

```bash
id akash
groups akash
sudo whoami

Here the user "akash" to always have root power without using sudo, we can modify /etc/passwd or /etc/sudoers.

sudo visudo
akash ALL=(ALL:ALL) NOPASSWD:ALL

but this is not a good practise

