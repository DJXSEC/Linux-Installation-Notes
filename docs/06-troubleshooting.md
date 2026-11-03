# 6. Troubleshooting

[Home](../README.md) · Previous: [Networking and Snapshots](05-networking-and-snapshots.md)

### Only 32-bit options show up under Version

Hardware virtualization is off. Enable **VT-x** (Intel) or **AMD-V / SVM** (AMD) in your BIOS/UEFI. On Windows, Hyper-V, WSL2, or Memory Integrity can also hide it; see the next item.

### VM is extremely slow or shows a green turtle icon

Windows' Hyper-V is in the way, so VirtualBox is running on top of it. Options:

- Turn off **Hyper-V**, **Virtual Machine Platform**, and **Windows Hypervisor Platform** in "Turn Windows features on or off", then reboot
- Or accept the slowdown if you need WSL2 or Docker running at the same time

### VM boots back into the installer after install

The ISO is still attached. Power off, go to Settings → Storage, select the optical drive, and choose **Remove disk from virtual drive**.

### Black screen or tiny resolution

Settings → Display: set Graphics Controller to **VMSVGA** and Video Memory to **128 MB**. Then check guest additions are loaded (`lsmod | grep vbox`).

### Installer stops at "Install the base system"

Usually not enough disk or RAM. Give the VM at least 2 GB RAM and 20 GB disk, delete the VM, and start over.

### `apt update` fails with signature or key errors

The Kali archive key changed since the ISO was made. Download a current ISO, or follow the key refresh instructions in the official Kali docs.

### No internet inside the VM

- Confirm Adapter 1 is set to **NAT** and **Cable Connected** is checked
- Inside Kali: `ip a` should show an IP on `eth0`
- Restart networking: `sudo systemctl restart NetworkManager`
