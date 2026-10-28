# kde-lockscreen-per-monitor

Different lock screen wallpaper on each monitor — KDE Plasma 5 (X11).

The script lists your monitors (via `xrandr`), asks for an image path for each one, and generates a small
Plasma wallpaper plugin (`org.kde.perscreenimage`) that picks the image by screen name.

## Usage

```bash
bash install.sh
```

- Tab completion works; you can also drag a file from Dolphin into the terminal.
- Leave a path empty to skip a monitor — it will use the first image you entered.

Then open **System Settings → Screen Locking → Appearance: Configure...** and set
**Wallpaper type** to **Image per screen**, then Apply.

Test without locking (close with your password):

```bash
/usr/lib/x86_64-linux-gnu/libexec/kscreenlocker_greet --testing
```

The path above is for Debian/Ubuntu; it differs on other distributions.

## Requirements

- KDE Plasma 5 on X11
- `xrandr`

## What it installs

`~/.local/share/plasma/wallpapers/org.kde.perscreenimage/` with `metadata.desktop` and `contents/ui/main.qml`.
Re-running the script regenerates the plugin. The monitor-to-image map in `main.qml` can be edited by hand.
