# 1. Prerequisites

[Home](../README.md) · Next: [Creating the VM](02-create-vm.md)

## Host Requirements

| Resource | Minimum | What I'd recommend |
|----------|---------|--------------------|
| RAM (host) | 8 GB | 16 GB so the VM can get 4 GB+ comfortably |
| Free disk | 25 GB | 60 GB+ (tools and updates add up fast) |
| CPU | 64-bit with virtualization | 4+ cores |

**Hardware virtualization must be on.** Intel calls it VT-x, AMD calls it AMD-V (sometimes "SVM"). It's toggled in your BIOS/UEFI. Without it, VirtualBox either won't offer 64-bit guests or will run painfully slow.

## Downloads

1. **VirtualBox** from [virtualbox.org](https://www.virtualbox.org/wiki/Downloads). Grab the matching **Extension Pack** too (adds USB 2.0/3.0 support and more).
2. **Kali Linux Installer ISO** from [kali.org/get-kali](https://www.kali.org/get-kali/#kali-installer-images). I used **2025.2**; grab whatever the current release is.

> **Installer ISO vs prebuilt VM:** Kali also offers a ready-made VirtualBox image. That's faster, but installing from the ISO teaches you partitioning, users, and the bootloader, which is the point of this lab.

## Verify the ISO

Never skip this on a security distro. Compare the file's hash against the SHA256 listed on the Kali download page.

**Windows (PowerShell):**

```powershell
Get-FileHash .\kali-linux-2025.2-installer-amd64.iso -Algorithm SHA256
```

**Linux / macOS:**

```bash
sha256sum kali-linux-2025.2-installer-amd64.iso
```

If the hashes don't match exactly, delete the file and download it again.
