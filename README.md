# Linux-Installation-Notes
This is my step-by-step instructions to download Linux inside of Virtual Box.
## 📦 What You'll Need

- [VirtualBox](https://www.virtualbox.org/)
- Kali Linux 2025.2 ISO from [kali.org](https://www.kali.org/get-kali/)
- At least 2GB RAM, 20GB disk space (recommended)

## 🖥️ Step-by-Step Setup

### 1. Download Kali Linux ISO

- Go to [kali.org](https://www.kali.org/get-kali/) and download the **Kali Linux 2025.2 Installer ISO**.

### 2. Create a Virtual Machine

- Open **VirtualBox**
- Click `New`
- Name it whatever you want (e.g. `Kali VM`)
- Choose:
  - **Type:** Linux
  - **Version:** Debian (64-bit)
  - **Memory Size:** 2048 MB or more I chose 4507 MB
  - **Disk:** Create a virtual hard disk (20GB+ recommended) I chose 50 GB

### 3. Attach Kali ISO

- Go to **Settings** → **Storage**
- Under **Controller: IDE**, click the **CD icon** next to "Optical Drive"
- Select "Choose a disk file…" and pick the **Kali ISO**
- Click **OK**

### 4. Start the Virtual Machine

- Start the VM and wait for the **Kali Linux boot menu**
- Select **Install** and press Enter

---

## 🌐 Installer Walkthrough

### Language & Location

- Language: `English`  
- Location: `United States`  
- Keyboard: `United States`

### User Setup

- **Hostname:** `debugged` (You can name this anything)
- **Domain Name:** `home`
- **Full Name:** Your real first and last name
- **Username:** e.g. `djxsec`
- **Password:** Set a secure password
- **Time Zone:** `Central Time (Texas)`

### Partitioning

- Choose: `Use entire disk`
- Disk should show something like: `/dev/sda`
- Select: `All files in one partition (recommended for new users)`
- Finish partitioning and write changes to disk

### Software Selection

- Select: `GNOME` desktop environment (or your preference)

### Bootloader Setup

- Install GRUB bootloader
- Choose: `/dev/sda`

### Final Steps

- Finish the installation
- Reboot the system
- Login with your username and password
- Kali Linux should now boot into the GNOME desktop
