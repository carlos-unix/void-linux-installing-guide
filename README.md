# How to install Void Linux step by step

## Booting
Firstly you'll need a bootable USB drive with the [Void base ISO](https://repo-default.voidlinux.org/live/current/void-live-x86_64-20250202-base.iso). I strongly recommend [Ventoy](https://github.com/ventoy/Ventoy) for this purpose.

## Starting base system

Void will open a command-line interface and request for a new login. The login is always `anon` and the pass is `voidlinux`. After logging in, call the script `void-installer`. The screen will show some interfaces to configure network, packages, permissions, etc, as explained below.

## Setting things up
In this step, you'll configure network, packages of ISO, mirrors...

#### Keyboard

Choose your default keyboard and press `Enter`. 

#### Network

You'll have to put it manually. Put the network name, the protocol and the pass. For example, if your network's name is _Jane_, your protocol is _wpa_ (most common) and your pass is _jane123_, complete the fields with these information.

#### Source 
I strongly recommend select it from ISO, not from network. You'll get a minimal installation of the distro by doing that.

#### Hostname

Choose the PC hostname, like: _Void_, _VoidLinux_, or whatever you want. 

#### Locale

Basically, the locale you are in. It'll appear with the language abreviation, the country abreviation and the unicode. Like: _en_US-UTF-8_ for example. After that, choose your timezone. For example, _America/Sao_Paulo_. 

#### RootPassword

If you don't wanna set any password for `root` access, just skip it.

#### UserAccount

Put your username to access system and choose a password for it. Like: `anon` (user) and `meanon` (pass). After that, choose what the user will control on system. I personally recommend the default choices and also _lp_, _network_, _users_, _storage_. To select options, press `Space` and you'll see an asterik on the options. 

#### BootLoader

Choose disk drive, and set it to initialize with a graphical interface (GRUB) on your disk of installation. 

#### Partition

That's the most simple part, don't be afraid. Select the disk and press for using `cfdisk` (easy). It will open a black interface to set/delete/change type of partitions at the disk. If you already have partitions on disk, just delete all of them by changing one for one pressing `arrow_key_down` in each one. Done, create a initial partition with 300M, and change its type to _EFI System_. Create another one to the the main system partition (_/_) and a last one to the the _/home_ partition, and let type by default (_Linux filesystem_). I don't recommend you using _swap_, do it by your own risk. Press `write` when you finish it, and `quit`. 

#### Filesystems

You'll have to configure some things on the disk partitions your just created. Click on it and select each partition previosly created. 

For example: 

_/dev/sda1_ 300M (click on `change`) |
type: vFAT (FAT32) |
mount point: _/boot/efi_

/dev/sda2 70G (click on `change`) |
type: ext4 |
mount point: _/_

/dev/sda3 100G (click on `change`) |
type: ext4 |
mount point: _/home_

Is everything completed? Return to the main screen and click to `install`. Wait for system's installation and reboot system. Take out your USB and wait...

You can also see about installing a graphical interface of XFCE [on this link](https://github.com/carlos-unix/void-linux-xfce-script).

Any suggestion may be added on "Issues".
