# How to screenshot on wayland
```bash
sudo apt install grim slurp wl-clipboard
```
## Fullscreen screenshot
```bash
grim screenshot.png
```

## Select region
```bash
grim -g "$(slurp)" screenshot.png
```

## Copy directly to clipboard
```bash
grim -g "$(slurp)" - | wl-copy
```

### Bind screenshot key in sway config
Open
```bash
~/.config/sway/config
```
Add:
```bash
bindsym Print exec grim -g "$(slurp)" ~/Pictures/screenshot-$(date +%s).png
```
Now: Press Print Screen and select region and it will save
to Pictures folder
