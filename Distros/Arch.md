# Arch-based
**Examples:**
- Arch Linux
- SteamOS
- Majaro
- EndeavousOS
- ArcoLinux

## Instructions
To enable 32-bit architecture, you need to **enable multilib**. Follow [this guide](https://low-orbit.net/arch-linux-how-to-enable-multilib) for more infos.

**Note:** On Manjaro and SteamOS, this should be already enabled, but you should still check!

After you're done:
```bash
# 2. and 3. Update & download packages. This may be a large download, but it'll ensure compatiblity
sudo pacman -Syyu

# 4. Install WINE
sudo pacman -S winetricks
```
