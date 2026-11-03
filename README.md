# Kali Linux in VirtualBox: Build Notes

![VirtualBox](https://img.shields.io/badge/Hypervisor-VirtualBox-183A61?style=flat-square&logo=virtualbox&logoColor=white)
![Kali](https://img.shields.io/badge/OS-Kali%20Linux-557C94?style=flat-square&logo=kalilinux&logoColor=white)
![Status](https://img.shields.io/badge/Status-Working%20Lab-2ea44f?style=flat-square)

A documented walkthrough of how I built my Kali Linux lab VM inside VirtualBox, from a blank hypervisor to a hardened, snapshotted machine ready for security work. Every setting below is what I actually used, with notes on why.

## Wiki

| # | Page | What it covers |
|---|------|----------------|
| 1 | [Prerequisites](docs/01-prerequisites.md) | Host requirements, downloads, verifying the ISO |
| 2 | [Creating the VM](docs/02-create-vm.md) | VirtualBox settings, CPU, RAM, disk, attaching the ISO |
| 3 | [Installing Kali](docs/03-install-kali.md) | Installer walkthrough: user, partitioning, desktop, GRUB |
| 4 | [Post Install](docs/04-post-install.md) | Updates, guest additions, first hardening steps |
| 5 | [Networking and Snapshots](docs/05-networking-and-snapshots.md) | Network modes for lab isolation, snapshot strategy |
| 6 | [Troubleshooting](docs/06-troubleshooting.md) | Problems I hit and how to fix them |

## My Build at a Glance

| Setting | Value |
|---------|-------|
| Hypervisor | Oracle VirtualBox |
| Guest OS | Kali Linux 2025.2 (Installer ISO) |
| VM type | Linux / Debian (64-bit) |
| RAM | ~4.5 GB (4507 MB) |
| Disk | 50 GB, dynamically allocated VDI |
| Partitioning | Entire disk, all files in one partition |
| Desktop | GNOME |
| Bootloader | GRUB on `/dev/sda` |
| Hostname | `debugged` |

## Why This Exists

Kali is the base for the rest of my security work (web app testing with Burp Suite, my own security tooling, and phishing analysis). Writing the build down means I can rebuild it the same way every time and anyone following along can do the same.

## Quick Start

If you just want the short version:

1. Download the Kali **Installer** ISO and VirtualBox
2. New VM: Linux, Debian 64-bit, 4 GB+ RAM, 2+ CPUs, 50 GB disk
3. Skip unattended install, attach the ISO, boot, choose **Graphical install**
4. Use the whole disk, one partition, install GRUB to `/dev/sda`
5. After first boot: `sudo apt update && sudo apt full-upgrade -y`, then take a snapshot

Full details are in the wiki pages above.
