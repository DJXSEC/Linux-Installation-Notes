# 5. Networking and Snapshots

[Home](../README.md) · Previous: [Post Install](04-post-install.md) · Next: [Troubleshooting](06-troubleshooting.md)

## Network Modes

Settings → Network → Adapter 1 → **Attached to**. Pick based on what you're doing.

| Mode | Internet | Visible on home network | Use it for |
|------|----------|-------------------------|-----------|
| **NAT** (default) | ✅ | ❌ | Updates, browsing, everyday use |
| **Bridged** | ✅ | ✅ (gets its own IP) | Testing devices on your real network you own |
| **Host-only** | ❌ | Host only | Isolated labs with vulnerable VMs |
| **Internal Network** | ❌ | Other VMs only | Attacker and target VMs talking to each other with zero exposure |

**Rule of thumb:** stay on NAT by default. Only go Bridged when you need to, and never point tools at anything you don't own or have written permission to test.

Check your IP inside Kali:

```bash
ip a
```

## Snapshots

Snapshots are save points. Break something, roll back in seconds.

**Take one:** VM window → **Machine** → **Take Snapshot**, or in the main VirtualBox window, select the VM → **Snapshots** → **Take**.

My snapshot plan:

| Snapshot | When |
|----------|------|
| `01-clean-install` | Right after first login |
| `02-updated` | After `full-upgrade` and guest additions |
| `03-tooled` | After installing my own tools and configs |
| Before anything risky | Running unknown samples, big config changes |

> Snapshots aren't backups. They live on the same disk as the VM. For a real backup, use **File → Export Appliance** to save an `.ova` somewhere else.
