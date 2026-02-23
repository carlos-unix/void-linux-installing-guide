# How to Install Void Linux – Step‑by‑Step Guide

This guide explains how to install **Void Linux Base** from scratch in a clear and beginner‑friendly way. It follows the official installer flow and adds practical tips along the way.


# 1. Prepare the Bootable USB

Download the **Void Linux Base ISO**:
[https://repo-default.voidlinux.org/live/current/](https://repo-default.voidlinux.org/live/current/)

Then create a bootable USB drive. Recommended tools:

* **Ventoy** – easiest for multiple ISOs
* Balena Etcher
* Rufus (Windows)

Boot your PC from the USB device.

# 2. Login and Start Installer

After booting, Void Linux will open a terminal.

Default login credentials:

```
User: anon
Password: voidlinux
```

Start the installer:

```
void-installer
```

You will now configure system options step‑by‑step.


# 3. System Configuration

## Keyboard

Choose your keyboard layout and press **Enter**.

## Network

Enter:

* Network name (SSID)
* Protocol → usually `wpa`
* Password

Example:

```
SSID: Jane
Protocol: wpa
Password: jane123
```

## Source

Choose **Install from ISO** for a minimal, faster installation.

## Hostname

Choose your computer name, for example:

```
voidpc
```

## Locale & Timezone

Example:

```
Locale: en_US.UTF-8
Timezone: America/Sao_Paulo
```

## Root Password

Optional. You can skip if you prefer using sudo later.

## User Account

Create your main user:

* Username
* Password
* Groups → keep defaults + optional: `lp`, `network`, `users`, `storage`

Press **Space** to select groups.

## Bootloader

Select the disk where Void Linux will be installed.
GRUB will be installed automatically.


# 4. Disk Partitioning

Choose **cfdisk** for easier partitioning.

### Suggested Layout (UEFI):

| Partition | Size      | Type             | Mount     |
| --------- | --------- | ---------------- | --------- |
| EFI       | 300MB     | EFI System       | /boot/efi |
| Root      | 50–100GB  | Linux filesystem | /         |
| Home      | Remaining | Linux filesystem | /home     |

Steps:

1. Delete old partitions if needed
2. Create new partitions
3. Set EFI type for the first partition
4. Write changes and quit

Backup your files before partitioning!


# 5. Filesystem Setup

Assign filesystem types:

Example:

```
/dev/sda1 → vFAT → /boot/efi
/dev/sda2 → ext4 → /
/dev/sda3 → ext4 → /home
```

Return to main menu and select **Install**.

Wait for installation to finish, then reboot and remove the USB drive.


# 6. After Installation

Void Base does not include a graphical interface.
You can install one manually, for example XFCE.

Example guide:
👉 [https://github.com/carlos-unix/void-linux-xfce-script](https://github.com/carlos-unix/void-linux-xfce-script)


# Tips & Notes

• Void uses **runit**, not systemd
• Use `xbps-install` to install packages
• Update system with:

```
sudo xbps-install -Syu
```

# 🤝 Contributions

Suggestions and corrections are welcome!
Open an Issue or Pull Request in this repository.


# ⭐ License

MIT License (or choose your preferred license).


If this guide helped you, consider giving the project a ⭐ on GitHub!
