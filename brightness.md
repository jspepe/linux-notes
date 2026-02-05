# Find backlight device
```bash
ls /sys/class/backlight/
```
Likely: intel_backlight

## Read current values
```bash
cat /sys/class/backlight/intel_backlight/max_brightness
cat /sys/class/backlight/intel_backlight/brightness
```
## Example
```bash
cat /sys/class/backlight/intel_backlight/max_brightness
# Output: 24242
cat /sys/class/backlight/intel_backlight/brightness
# Output: 12000
```

## Don't rely on Xrandr for brightness
``bash
xrandr --brightness 0.8
```
This is fake brightness (gamma dimming).
Bad for eyes + doesn't save power. Only use as last resort.

# Lower brightness
```bash
echo 6000 | sudo tee /sys/class/backlight/intel_backlight/brightness
```
