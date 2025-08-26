---
{"dg-publish":true,"permalink":"/pages/home-server/"}
---


# Why a Home Server?
It started with wanting to stop using google/microsoft for things like backing up photos, contacts, documents, ect. I considered using a service like Proton where it's hosted in a famously neutral country, but decided that for the long run, I'd rather just have all the data in a box at home. 

Frankly, I wanted more say of what is done with my data existing online. Now I'm more selective with what I share online and everything else gets backed up to NextCloud and Jellyfin.

# Process
I had previously tinkered with Raspberry Pi home services but with a cheap case and that system eventually burnt itself out. This time I decided I was going to get a good purpose made case and settled on the Argon EON Pi NAS. 

It's solid aluminum which is all connected to the heat sink so the whole body acts as heat distribution (overkill for the Raspberry Pi), it also has a built in SATA board for mounting up to 2xSSD and 2xHDD or 4xSSD (plus a single internal 3.0 USB-A port). The only real downside is that the case is only designed to be compatible with the Raspberry Pi 4, hardly a downside (in 2025). 

For a month or so I prototyped the setup using the internal USB port instead of the drives which I hadn't purchased yet and did not have any spares laying around. The final setup has the OS on the SD card but everything else is stored on the other drives, this includes configuration files, backups, docker images, ect. This way if the SD card ever fails I can simply reinstall it from a backup on a new SD card and plug it in. 

Open Media Vault 7 (OMV7) provides a web based GUI for managing the shares and docker deployments. This and the rare ssh allows me to manage the system from anywhere on my local network. 

The first service I decided to start was PiHole for several reasons. Mostly because I could manage DHCP assignments through it more easily than through my router. Doing this also meant that both OMV7 and PiHole had to assign their own IP addresses. OMV7 can do this easily though settings, PiHole is running in docker so I was able to assign it an address in the docker compose file. With the IP addresses configured PiHole safely took over DHCP. PiHole is also providing adblocking across my whole network for all devices.





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
