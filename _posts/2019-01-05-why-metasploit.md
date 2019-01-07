---
title: "Metasploit Part 1: Why do we need Metasploit?"
date: 2019-01-05 12:30:30
tags:
  - Metasploit
---
In the last [post](/kioptrix-1/) we found a vulnerability exists in the Samba service.

As an attacker, to take advantage of this vulnerability, you need to have exploit and payload.

1. You can write them on your own (This is time consuming)
2. You can download them from Web (If you don't understand what the exploit or payload is doing, then there will be a high chance of you getting hacked or giving the access of the victim machine to the author of the payload)
3. You can use Metasploit framework. (There are bunch of trusted and well reviewed exploits and payloads ready for you to explore)

The team behind Metasploit know how excited you will be after knowing about these exploits and payloads, So they created a VM, [Metasploitable](https://metasploit.help.rapid7.com/docs/metasploitable-2), to test these exploits.

> It is illegal to run these exploits against systems for which you don't have permission to do so.

In the next post we will see how to use Metasploit.
