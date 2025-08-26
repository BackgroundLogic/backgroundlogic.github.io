---
{"dg-publish":true,"permalink":"/pages/home-server/"}
---

---
# Why a Home Server?
It started with wanting to stop using google/microsoft for things like backing up photos, contacts, documents, ect. I considered using a service like Proton where it's hosted in a famously neutral country, but decided that for the long run, I'd rather just have all the data in a box at home. 

Frankly, I wanted more say of what is done with my data existing online. Now I'm more selective with what I share online and everything else gets backed up to NextCloud and Jellyfin.

# Hardware
Motherboard: Raspberry Pi 4 8GB
Case: Argon EON Pi NAS 
Storage: 1x1TB SSD, 1x4TB HDD

# Software
OS: Raspberry Pi OS (latest)
Management Software: Open Media Vault 7
Docker Containers: 
- PiHole - DHCP server, network wide adblocking
- NginxProxyManager - GUI frontend for Nginx, used for reverse proxy
- Jellyfin - A media server for personal use
- NextCloud - A cloud similar to office365 or google
- Actual Budget - A budgeting software similar to YNAB
