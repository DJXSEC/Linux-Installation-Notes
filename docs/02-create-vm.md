# 2. Creating the VM

[Home](../README.md) · Previous: [Prerequisites](01-prerequisites.md) · Next: [Installing Kali](03-install-kali.md)

## New Virtual Machine

Open VirtualBox and click **New**.

| Field | Value | Notes |
|-------|-------|-------|
| Name | `Kali VM` | Anything works |
| ISO Image | Leave empty for now | Attaching it here can trigger unattended install |
| Type | Linux | |
| Version | Debian (64-bit) | Kali is built on Debian Testing |
| **Skip Unattended Installation** | ✅ Checked | Newer VirtualBox versions try to auto install; Kali should be installed manually |

## Hardware

| Setting | My value | Guidance |
|---------|----------|----------|
| Base Memory | 4507 MB | 2048 MB works, 4096 MB+ is much smoother with GNOME |
| Processors | 2 | Never give more than half your physical cores |
| Enable EFI | Off | Default BIOS boot is the simplest path |

## Virtual Hard Disk

| Setting | My value | Guidance |
|---------|----------|----------|
| Size | 50 GB | 20 GB is the floor; tools and updates fill it quickly |
| Type | VDI | VirtualBox's native format |
| Pre-allocate full size | Off | Dynamic disks only use space as they fill |

## Attach the ISO

1. Select the VM → **Settings** → **Storage**
2. Click the empty **optical drive** (CD icon) under the controller. Older VirtualBox versions list it under **Controller: IDE**, newer ones under **Controller: SATA**
3. Click the CD icon on the right → **Choose a disk file…** → pick the Kali ISO
4. Click **OK**

## Optional but Worth It

- **Display:** Settings → Display → Video Memory to **128 MB**, Graphics Controller **VMSVGA**. Fixes most laggy or tiny screen issues.
- **Clipboard:** Settings → General → Advanced → Shared Clipboard **Bidirectional** (only if you trust what's in the VM).
