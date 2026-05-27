# Flipper Zero — AetherOS Launcher

BadUSB scripts for the Flipper Zero that open [Aether OS](https://www.aetheros.computer/) in the default browser on any machine the Flipper is plugged into. Intended for personal use on hardware you own or have explicit permission to access. Like all BadUSB scripts, these automate keyboard input — only use them on machines you control.

---

## What's included

```
badusb/aetheros/
  aetheros-mac-cold.txt    macOS — browser is closed (opens via Spotlight)
  aetheros-mac-warm.txt    macOS — browser is already open
  aetheros-linux-cold.txt  Linux — opens terminal and uses xdg-open
  aetheros-linux-warm.txt  Linux — browser is already open
  aetheros-windows.txt     Windows — uses Run dialog (Win+R)
```

---

## Installation

1. Copy the `badusb/` folder to the root of your Flipper Zero's SD card.
2. On the Flipper, navigate to **BadUSB** and select the script for your target platform.
3. Plug into any computer and run.

---

## Script overview

### macOS (warm start)
Browser is already open and frontmost. Focuses the address bar with `Cmd+L` and navigates.

### macOS (cold start)
Opens Spotlight (`Cmd+Space`), types the URL directly, and lets macOS launch it in the default browser.
> Tune the `DELAY` after `GUI SPACE` if Spotlight is slow on your machine (try 1000–1200 ms).

### Linux (warm start)
Focuses the address bar with `Ctrl+L`. Works with Chrome, Firefox, Brave, and most browsers.

### Linux (cold start)
Opens a terminal with `Ctrl+Alt+T` (default on Ubuntu, Pop!\_OS, Mint, and most GNOME/KDE distros), then uses `xdg-open` to launch the URL in the default browser.
> Tune the `DELAY` after `CTRL ALT t` if your terminal opens slowly (try 2000–2500 ms).

### Windows
Uses the Run dialog (`Win+R`) to launch the URL directly — works regardless of browser state.

---

## Tier 2: Login automation (future goal)

A future script variant could automate the Bluesky login flow inside Aether OS using `MOUSEMOVE` and `LEFTCLICK`. This is feasible but fragile — mouse coordinates depend on screen resolution, browser window size, and zoom level, and Aether OS is actively in development (UI may change).

**If building this:** way to use a [Bluesky App Password](https://bsky.app/settings/app-passwords), not main password? App passwords are revocable independently and designed for third-party use. Avoids committing a script with credentials embedded.

---

## Compatibility notes

- Scripts use extended DuckyScript 1.0 syntax supported by Flipper Zero's stock firmware.
- Tested targets: macOS Ventura+, Windows 10/11, Ubuntu 22.04+.
- The `WAIT_FOR_BUTTON_PRESS` command can be inserted as a manual checkpoint (e.g., pause after page load to visually confirm before proceeding).

---

## License

MIT
