# 3. Installing Kali

[Home](../README.md) · Previous: [Creating the VM](02-create-vm.md) · Next: [Post Install](04-post-install.md)

Start the VM. At the Kali boot menu, choose **Graphical install** (the plain **Install** option is the same installer in text mode).

## Language and Location

| Prompt | Value |
|--------|-------|
| Language | English |
| Location | United States |
| Keyboard | American English |

## Network and User Setup

| Prompt | My value | Notes |
|--------|----------|-------|
| Hostname | `debugged` | How the machine identifies itself on a network |
| Domain name | `home` | Can be left blank for a home lab |
| Full name | Your name | |
| Username | `djxsec` | Lowercase, no spaces |
| Password | Strong and unique | Kali gives you `sudo` through this account; there's no separate root password by default |
| Time zone | Central | |

## Partitioning

1. **Guided: use entire disk**
2. Select the virtual disk, something like `SCSI1 (0,0,0) (sda)`
3. **All files in one partition (recommended for new users)**
4. **Finish partitioning and write changes to disk** → **Yes**

> This only wipes the **virtual** disk you created, not your real hard drive.

## Software Selection

The default desktop is **Xfce** (lightweight). I switched it to **GNOME** for the look and feel. Leave the default tool selection checked unless you know you want the full `kali-linux-large` set.

This step takes the longest, often 10 to 30 minutes.

## Bootloader

1. Install the **GRUB** boot loader to the primary drive: **Yes**
2. Device: **`/dev/sda`**

## Finish

1. **Continue** to reboot. VirtualBox usually ejects the ISO for you; if it boots back into the installer, remove the ISO under Settings → Storage
2. Log in with your username and password
3. You should land on the GNOME desktop
