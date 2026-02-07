# pactl — Audio Control (PipeWire / PulseAudio)
## Mental model

pactl talks to the audio server (PipeWire/PulseAudio), not directly to hardware.

Layers:

Apps → pactl → PipeWire → ALSA → Hardware

`pactl` is a command-line tool used to control audio devices.

Works with:

- PipeWire (modern Linux audio)
- PulseAudio
- Wayland and X11 environments

It does NOT depend on the window manager.

## Install and start pipewire
```bash
sudo apt update
sudo apt install pipewire wireplumber pipewire-pulse
```
then start them because minimal window manager setups (Sway, dwm, etc.) may not auto-start audio services.

```bash
systemctl --user start pipewire
systemctl --user start wireplumber
systemctl --user start pipewire-pulse
```

## Check audio server status

```bash
pactl info
```
Example output:
```bash
Server Name: PulseAudio (on PipeWire)
Default Sink: alsa_output.pci-0000_00_1f.3.analog-stereo
```

List audio outputs (sinks)
```bash
pactl list short sinks
```
Example:
```bash
61 alsa_output.pci-0000_00_1f.3.analog-stereo
```

Set default audio output
```bash
pactl set-default-sink NAME
```
Example:
```bash
pactl set-default-sink alsa_output.pci-0000_00_1f.3.analog-stereo
```

## Change Volume
Increase volume:
```bash
pactl set-sink-volume @DEFAULT_SINK@ +5%
```
Decrease volume:
```bash
pactl set-sink-volume @DEFAULT_SINK@ -5%
```
Toggle mute:
```bash
pactl set-sink-mute @DEFAULT_SINK@ toggle
```
## PipeWire troubleshooting
If pactl fails:
```text
Connection refused
```
Check services:
```bash
systemctl --user status pipewire wireplumber pipewire-pulse
```
Start manually:
```bash
systemctl --user start pipewire wireplumber pipewire-pulse
```
