# Debian-based
**Examples:**
- Ubuntu, Kubuntu, Xubuntu, ...
- Linux Mint
- PopOS
- ElementaryOS

## Instructions
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

