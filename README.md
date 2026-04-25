WARNING - THIS IS ONLY BUILT FOR LINUX DISTRIBUTIONS AT THE MOMENT, IT WONT WORK ON WINDOWS

# OpenRGB Trinity Controller

**RGB lighting controller for Vs Sonic (FNF mod) on Linux**

---

## What is this?

This is a Python script that syncs your RGB keyboard lighting with the Vs Sonic mod in Friday Night Funkin'. It runs on Linux and controls OpenRGB-compatible keyboards to match the in-game window title changes.

This project improves the Vs Sonic mod for Linux users with RGB keyboards by:

- Adding dynamic RGB lighting that matches the game atmosphere
- Auto-launching the game via Wine
- Automatic window title detection (no game modding required)
- Smooth brightness fade effects during key moments

---

## Features

- **Window Title Tracking**: Detects in-game window titles and changes colors automatically
- **Linux + Wine Support**: Works with Vs Sonic running through Wine
- **Auto-Launch**: Starts OpenRGB server and the game automatically
- **Smooth Fades**: Brightness animations for dramatic moments:
  - "UH OH": Yellow → fast fade to 0% (30% per tick, ~0.3s)
  - "SONIC": Slow fade from 0% to 100% (10% per tick, ~1s)
- **Multiple Color Schemes**: Different colors for each game phase

---

## Color Mapping

| Window Title | RGB Color | Brightness | Notes |
|--------------|----------|-------------|-------|
| VS Sonic | Dark Blue #00008B | 100% | Start |
| FUN IS INFINITE | Dark Blue #000064 | 80% | |
| The fun never ends! | Light Blue #00C8FF | 100% | |
| INFINITE | Dark Blue #000064 | 80% | |
| FNU IS NNIIFITE | Purple #640064 | 60% | Glitch |
| FUNFUNFUNFUN | Purple #640064 | 80% | Glitch |
| AAAAAAAA | Dark Red #8B0000 | 100% | Glitch |
| Ready for ROUND 2... | Dark Red #8B0000 | 100% | |
| SONIC.EXE | Bright Red #FF0000 | 100% | |
| Sonic PC Port | Dark Red #8B0000 | 60% | |
| GONNA GETCHA | Purple #640064 | 80% | |
| Friday Night Funkin': Rodentrap | Light Blue #00C8FF | 100% | |
| WELCOME BACK | Bright Red #FF0000 | 100% | |
| UH OH | Yellow #FFFF00 | 100% → 0% | **Fast fade** (30%/tick) |
| SONIC | Light Blue #00B4FF | 0% → 100% | **Slow fade** (10%/tick, after UH OH) |

### Fade Effects

- **UH OH**: Yellow flashes, then quickly fades to 0% in ~0.3 seconds (4 steps at 30%/tick)
- **SONIC** (after UH OH): Begins at 0%, slowly fades to 100% in ~1 second (10 steps at 10%/tick)

---

## Requirements

- Linux (Arch Linux tested)
- OpenRGB installed
- Wine (for running Sonic.exe)
- xdotool (for window detection)
- Python 3

### Install Dependencies

```bash
# Install OpenRGB
sudo pacman -S openrgb

# Install xdotool
sudo pacman -S xdotool

# Install Wine (if not already)
sudo pacman -S wine
```

---

## Installation

1. Copy this folder to your preferred location:
   ```bash
   cp -r ~/Desktop/Vs\ Sonic ~/path/to/folder
   ```

2. Make the script executable:
   ```bash
   chmod +x openrgb_trinity_controller.py
   ```

---

## Usage

### Run the Controller

```bash
cd /path/to/folder
python openrgb_trinity_controller.py OR ./openrgb_trinity_controller.py (preferred)
```

This will:
1. Start OpenRGB server (if not already running)
2. Launch Sonic.exe via Wine
3. Track window titles and change RGB colors automatically

### Controls

- **Ctrl+C** - Stop the script

---

## How It Works

1. **Window Detection**: Uses `xdotool` to read the active window title
2. **Pattern Matching**: Compares against known in-game titles
3. **RGB Control**: Sends colors to OpenRGB via CLI

The script doesn't modify any game files - it works by monitoring the window title that the game itself sets via the `WindowTitle` custom event built into the mod.

---

## Troubleshooting

### OpenRGB not found
```bash
# Install OpenRGB
yay -S openrgb
```

### Colors not changing
```bash
# Test OpenRGB directly
openrgb -c FF0000 -m direct
```

### Window title not detected
```bash
# Check if xdotool is working
xdotool getactivewindow getwindowname
```

---

## Files

```
openrgb_trinity_controller.py  - Main controller script
add_rgb_events.py            - (optional) Add events to chart
README.md                  - This file
```

---

## Credits

- **Vs Sonic Mod** - Original FNF mod by community
- **OpenRGB** - RGB lighting control software
- **Friday Night Funkin'** - Original game by ninjamuffin99
- **Your average mentally ill loser/LiderazgoYT** - creator of script

---

## License

This controller is provided as-is for Linux users with RGB keyboards who want enhanced RGB sync with Vs Sonic.

(problems and or bug reports? contact me at liderazgo_reborn on discord!)
