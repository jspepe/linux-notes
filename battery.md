# Check thinkpad t490 battery

```bash
cat /sys/class/power_supply/BAT0/capacity
```

You'll get something like: 73
If BAT0 doesn't exist, list first:

```bash
ls /sys/class/power_supply/
```

