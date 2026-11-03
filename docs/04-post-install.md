# 4. Post Install

[Home](../README.md) · Previous: [Installing Kali](03-install-kali.md) · Next: [Networking and Snapshots](05-networking-and-snapshots.md)

## Update Everything

First thing after login. Kali is a rolling release, so a fresh install is already behind.

```bash
sudo apt update
sudo apt full-upgrade -y
sudo reboot
```

`full-upgrade` (instead of `upgrade`) lets apt add or remove packages when dependencies change, which Kali needs.

## Guest Additions

Kali normally ships with the VirtualBox guest packages already installed, which handle auto resizing the screen and the shared clipboard. Check:

```bash
lsmod | grep vbox
```

If nothing comes back, install them:

```bash
sudo apt install -y virtualbox-guest-x11
sudo reboot
```

## First Hardening Steps

This is a security VM, so treat it like one.

| Step | Command |
|------|---------|
| Confirm you're not running as root | `whoami` (should be your user) |
| Check what's listening | `sudo ss -tulpn` |
| Turn on the firewall | `sudo apt install -y ufw && sudo ufw enable` |
| Keep SSH off unless you need it | `sudo systemctl disable --now ssh` |

## Take Your First Snapshot

Before installing anything else, snapshot this clean state. See [Networking and Snapshots](05-networking-and-snapshots.md).
