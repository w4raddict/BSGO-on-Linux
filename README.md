# BSGO on Linux in 2023!
**BSGO on Linux doesn't work?** Oh really?

BSGO on Linux is alive and it is a lot of fun. I'll show you:

![Some fun BSGO hacking performed on Linux](Assets/BSGO-on-Linux.png)


This was on PopOS, but I've tested everything on many Debian- and Arch-based distros and it works very well.

## Compatibility overview
**The BSGO client always works with WINE!** It's very easy to set it up!

For Linux support, the custom launchers pose the greatest and pretty much the only barrier to full Linux support.

BSGO server|Launcher works with WINE|Temporary workaround|Linux support planned?
--|--|--|--
[Victii/Mementomori](https://discord.gg/jsGGZZZ9xu)|<font color=FF7F50>limited</font>|PM me|<font color=DC143C>confirmed, but low priority</font>
[2.0 Resurrection](https://discord.gg/fhxpcb4SEr)|<font color=FF7F50>limited</font>|<font color=DC143C>no</font>|<font color=7FFF00>in development</font>

**Note:**
- My recommendation for Linux users is 2.0 Resurrection due to the much more secure launcher as well as the in-development Linux support.
- Mementomori's BSGO launcher, while more feature-rich, has massive security issues, running on administrator privilges for literally no good reason at all. This is very dangerous, especially in combination with the auto-update feature. Use it at your own risk.

## General Setup
1. **Enable 32-bit architecture.** This is because the BSGO client contains some 32-bit executables. By default, modern Linux distributions block the execution of 32-bit code for security reasons and for "cleanness". But we're not clean, we're playing a very old game. Hence, we need to enable 32-bit.
2. **Update & upgrade system.** This is to ensure that your system fetches 32-bit configurations.
4. **Install WINE.** In this guide, we will be installing a package called `winetricks`, which contains everything we need for BSGO.

### Debian-based
**Examples:**
- Ubuntu, Kubuntu, Xubuntu, ...
- Linux Mint
- PopOS

Write in a terminal:
```bash
# 1. enable 32-bit support
sudo dpkg --add-architecture i386

# 2. Update system
sudo apt update

# 3. Download packages. This may be a large download, but it'll ensure compatiblity
sudo apt upgrade -y

# 4. Install WINE
sudo apt install winetricks
```

### Arch-based
**Examples:**
- Arch Linux
- Majaro
- ElementaryOS
- ArcoLinux

To enable 32-bit architecture, you need to **enable multilib**. Follow [this guide](https://low-orbit.net/arch-linux-how-to-enable-multilib) for more infos.

After you're done:
```bash
# 2. and 3. Update & download packages. This may be a large download, but it'll ensure compatiblity
sudo pacman -Syyu

# 4. Install WINE
sudo pacman -S winetricks
```

### Steam Deck+SteamOS
Although SteamOS is Arch-based, the Steam Deck comes shipped with a couple extra modifications that require a couple extra steps:

#### Fixing SteamOS

```bash
# to create a password for your Steam Deck.
passwd

# Disable read-only mode
sudo steamos-readonly disable

# Setup pacman keyring
sudo pacman-key --init

# populate keyring with default Arch Linux keys
sudo pacman-key --populate archlinux
```

#### WINE setup
Now we're ready to commence our WINE setup:

```bash
# 2. and 3. update system
sudo pacman -Syyu

# 4. Install WINE
sudo pacman -S winetricks
```

Note that enabling 32-bit is not required since SteamOS ships with 32-bit support activated by default.

## Testing your setup
1. **Launch BSGO client.** For example:
```bash
wine64 ./client/live/bsgo.exe
```
If it says "Please start the game using the Launcher", it means your setup is complete.

2. **Find out how to launch the launcher.** The launchers are the worst part of Linux compatibility. For example, try:
```bash
wine64 ./Launcher.exe
```

If you can launch the launcher, you're good to go. Otherwise, you might need some extra steps.
