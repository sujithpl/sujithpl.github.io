---
categories:
- personal
date: "2026-04-23T00:00:00Z"
tags:
- self-hosting
- vps
title: Security Hardening a Debian VPS
---
A freshly spun up VPS instance is susceptible to brute force attacks from hackers and bots. Here is a list of steps to shore up the security of the server.

 - [Local] SSH into VPS as root.  
` ssh root@<YOUR_SERVER_IP>`

 - [VPS] Update Debian.  
`apt update && apt upgrade -y`

 - [VPS] Change root password.  
`passwd root`

 - [VPS] Create a user account.  
`adduser vpsuser`

 - [VPS] Add user to to `sudo` group.  
`usermod -aG sudo vpsuser`

 - [Local] Create a SSH key pair.  
`ssh-keygen -t ed25519 -C "mxlinux@my_laptop"`

 - [Local] Upload public key to user account.  
`ssh-copy-id -i ~/.ssh/id_ed25519.pub vpsuser@YOUR_SERVER_IP`

 - [Local] Verify that user can SSH into server with key.  
`ssh-i ~/.ssh/id_rsa.pub vpsuser@YOUR_SERVER_IP`

 - [VPS] Update the SSH configuration in `/etc/ssh/sshd_config`.
   - Change default SSH port: `Port 2026`
   - Disable password login: `PasswordAuthentication no` & `PubkeyAuthentication yes`
   - Disable root login: `PermitRootLogin no`
   - Allow only specific users: `AllowUsers vpsuser`

 - [VPS] Validate the SSH configuration.  
`sshd -t`
  
 - [VPS] Restart the SSH daemon to apply changes.  
`systemctl restart sshd`

 - [Local] Test that user can SSH into server at new port.  
`ssh-copy-id -i ~/.ssh/id_ed25519.pub vpsuser@YOUR_SERVER_IP -p 2026`

 - [VPS] Install UFW.  
`apt install ufw`

 -  [VPS] Configure UFW.  
```
sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw allow http
sudo ufw allow https
sudo ufw allow 2026/tcp
sudo ufw enable
```

  -  [VPS] Verify UFW active rules.  
`sudo ufw status`

Additional steps:
  - Install and configure fail2ban
  - Enable automatic security updates
