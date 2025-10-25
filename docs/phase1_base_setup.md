# Phase 1: Debian Base Setup

## Objective
Set up a clean Debian installation for your homelab, including:
- System updates
- User creation
- SSH access
- Firewall setup

---
First we have installed the debian 13 with xfce Gui on our old laptop 
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
