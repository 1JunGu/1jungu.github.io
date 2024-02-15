---
title: sshfs 远程挂载
date: 2024-02-15 18:47
modify: 2024-02-15 18:47
author: Jun Gu
aliases: 
type: 
tags: 
layout: post
---

## 1 Mount remote file system to Windows system 
### 1.1 Download necessary software 

[WinFsp](https://winfsp.dev/rel/)
It requires [winfsp/sshfs-win: SSHFS For Windows](https://github.com/winfsp/sshfs-win) installed. There are two kinds of installer (x86 vs x64) to choose.
> [!info]+ x86 vs x64
> 
"x86" and "x64" are terms describing different families of computer architecture. 
**x86**: This term originally refers to a series of Intel microprocessors starting with the 8086 and including the 80186, 80286, 80386, and 80486. The term "x86" is used because the names of several of Intel's processors ended in "86". It has since come to refer more generally to any **32-bit** processor using a similar instruction set. An x86 (32-bit) processor can directly access up to 4 gigabytes of memory. 
**x64**: This term refers to a 64-bit extension of the x86 architecture. The extension was originally developed by **AMD** and named "x86-64", but it is also known as "x64" in Windows environments. This **64-bit** architecture removes the 4-gigabyte memory limit of x86 and can theoretically address up to 18.4 million terabytes of memory. In addition, x64 architectures typically process data in larger chunks (64 bits at a time), which can lead to better performance for certain kinds of tasks.


It's worth noting that most most modern desktop and laptop processors are based on the x64 architecture and can run both x86 (32-bit) and x64 (64-bit) software.  Currently, `x64` is your best your choice and should be checked in your system info.

### 1.2 Install GUI software 
If you want to use [GUI software](https://github.com/evsar3/sshfs-win-manager), [WinFsp](https://winfsp.dev/rel/) is **NOT** necessary to install on your system, but also requires **SSHFS** installed.

Be sure check sshfs binary path in setting UI 
<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/sshfs.exe.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

Detailed guide could be seen [here](https://blog.xieqiaokang.com/posts/505416489.html)
### 1.3 Limitations 
1. Don’t support keyboard-interactive authentication[^1] such as google authenticator[^2]
2. Using pubkey authentication is a trade-off solution but could threaten the security.
3. Some remote machine could forbid pubkey login in `sshd_config` `PubkeyAuthentication no`


## 2 Solutions using WSL2
If you use ubuntu distribution in WSL2, follow this steps 
```shell
1. sudo apt-get install sshfs
2. mkdir -p mountpoint 
3. sudo sshfs -o allow_other user@host:/path /mountpoint -p port #port is your ssh port
4. #you can view remote file systems in ubuntu and Windows Explorer
```
![[attachments/sshfs_ubuntu_wsl.png]]

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/sshfs_ubuntu_wsl.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

More info are here[How To Use SSHFS to Mount Remote File Systems Over SSH | DigitalOcean](https://www.digitalocean.com/community/tutorials/how-to-use-sshfs-to-mount-remote-file-systems-over-ssh)

## 3 Others 
1. SSHFS mount remote file systems using ssh. So don’t install anything on remote servers.
2. Be careful the permissions

---
[^1]: [Support for Keyboard-Interactive Authentication? · Issue #79 · winfsp/sshfs-win (github.com)](https://github.com/winfsp/sshfs-win/issues/79)
[^2]: [Google Authenticator · Issue #261 · winfsp/sshfs-win (github.com)](https://github.com/winfsp/sshfs-win/issues/261)