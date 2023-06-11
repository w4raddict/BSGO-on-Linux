# Steam Deck + SteamOS
BSGO on the Steam Deck is fun!

## Instructions
### I. Fixing SteamOS
Although SteamOS is Arch-based, the Steam Deck comes shipped with a couple extra modifications that require a couple extra steps:

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

### II. WINE setup
Now we're ready to commence our WINE setup:

```bash
# 2. and 3. update system
sudo pacman -Syyu

# 4. Install WINE
sudo pacman -S winetricks
```

Note that enabling 32-bit is not required since SteamOS ships with 32-bit support activated by default.
