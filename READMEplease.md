# OpenRGB Trinity Controller

RGB lighting controller for Vs Sonic (Friday Night Funkin' mod) on Linux.

---

## What is this?

This script syncs your RGB keyboard lighting with Vs Sonic by detecting the game's window title and changing colors automatically.

**Requirements:**
- Linux (Arch Linux tested)
- OpenRGB installed
- Wine (to run Sonic.exe)
- xdotool (for window detection)
- Python 3

**Install dependencies:**
```bash
sudo pacman -S openrgb xdotool wine
```

---

## Quick Start

```bash
# Clone or download this repo
cd openrgb-trinity-controller

# Make executable
chmod +x openrgb_trinity_controller.py

# Run
./openrgb_trinity_controller.py
```

The script will:
1. Start OpenRGB server (if not running)
2. Launch Sonic.exe via Wine
3. Change keyboard colors based on game window title

---

## Color Reference

| In-Game Title | Color | Brightness |
|---------------|-------|------------|
| VS Sonic | Dark Blue | 100% |
| FUN IS INFINITE | Dark Blue | 80% |
| The fun never ends! | Light Blue | 100% |
| Ready for ROUND 2 | Dark Red | 100% |
| SONIC.EXE | Bright Red | 100% |
| GONNA GETCHA | Purple | 80% |
| Friday Night Funkin': Rodentrap | Light Blue | 100% |
| WELCOME BACK | Bright Red | 100% |
| UH OH | Yellow → fast fade | 100%→0% |
| SONIC (after UH OH) | Light Blue → fade in | 0%→100% |

---

## Troubleshooting

**OpenRGB not found:**
```bash
yay -S openrgb
```

**Colors not changing - test OpenRGB:**
```bash
openrgb -c FF0000 -m direct
```

**Window detection not working:**
```bash
xdotool getactivewindow getwindowname
```

---

## Files

- `openrgb_trinity_controller.py` - Main script
- `README.md` - Full documentation
- `readmenow.txt` - This guide

---

## Credits

- Vs Sonic mod by FNF community
- OpenRGB by CalcProgrammer1
- Friday Night Funkin' by ninjamuffin99
