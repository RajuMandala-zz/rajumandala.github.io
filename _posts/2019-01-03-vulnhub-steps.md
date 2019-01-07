---
title: "Vulnhub solving steps"
tags:
  - Vulnhub
---
For all the VMs available on Vulnhub, we follow the below steps
  1. Lab setup
  2. Finding Victim's IP address
  3. Port scanning
  4. Exploitation
  5. Post Exploitation

### Lab setup
My Host OS is macOS Mojave. I used VMware Fusion 11 for Kali and Vulnhub VM.  My network configuration is Bridged.

### Finding victim's IP address
Once the lab is set up, we need to find out the IP address of the victim VM. This can be done by either netdiscover or nmap.
```sh
netdiscover -r 192.168.1.0/24
```

### Port scanning
Once we know the IP address of the victim, we need to find out the services running on that machine. We use nmap to do this.
```sh
nmap -sC -sV -oA quick 192.168.1.104
```

### Exploitation
Once we identify the ports running on the victim. We will search for vulnerabilities existing in the respective services. We use many tools here like Searchsploit, Metasploit etc. If the service we are targeting is running as unprivileged account, we will get the unprivileged shell.

### Post exploitation
In the post exploitation phase, using privilege escalation techniques we convert the unprivileged shell to privileged shell.
