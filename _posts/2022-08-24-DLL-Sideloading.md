---
title: "Learning about DLL Sideloading"
---

## Introduction
DLL Sideloading is similar to DLL search order hijacking which involves in dropping a malicious DDL to execute second-stage payload. Normally in DLL hijacking, the program that executes our payload tend to crash after execution. However, in this case the program and the payload get executed alongside each other since the original legitimate DLL is also dropped.
Recently Unit 42 from Palo Alto Networks published a blog documenting how the APT29 use such technique on their campaigns, read more about [here](https://unit42.paloaltonetworks.com/brute-ratel-c4-tool/). In order to learn more about the technique, I read blogs from [here](https://blog.sunggwanchoi.com/recreating-an-iso-payload-for-fun-and-no-profit/) and [here](https://crypt0ace.github.io/posts/DLL-Sideloading/) to mimic the attack and to gain hands on experience.

## Steps

- Find a legitimate un/signed executable and vulnerable to DLL-Sideloading using Procmon
- Create a proxy DLL from the legitimate DLL using [SharpDLLProxy](https://github.com/Flangvik/SharpDllProxy)
- Create [Sliver](https://github.com/BishopFox/sliver) shellcode
- Upload them to victim host and profit.

## After thought

It was a fun exercise for me to learn about how DLL Sideloading works and how to build a proxy DLL from the legitimate one. In addition, trying out the Sliver C2 Framework and adding it to my arsenal is always a good thing!