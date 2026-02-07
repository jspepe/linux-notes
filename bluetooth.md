# install required packages
```bash
sudo apt install bluez bluez-tools blueman pipewire-audio wireplumber
```
If Debian asks about audio backend → PipeWire is what you want (modern Linux audio).

## Enable Bluetooth service
```bash
sudo systemctl enable bluetooth
sudo systemctl start bluetooth
```
Check status:
```bash
systemctl status bluetooth
```
You want:
```text
active (running)
```
## Connect via terminal (fastest way)
Open bluetoothctl:
```bash
bluetoothctl
```
Inside the prompt:
```bash
power on
agent on
default-agent
scan on
```
You'll see something like:
```text
Device XX:XX:XX:XX:XX:XX Jose-AirPods
```
Copy Mac address.
Then:
```bash
pair XX:XX:XX:XX:XX:XX
trust XX:XX:XX:XX:XX:XX
connect XX:XX:XX:XX:XX:XX
```
Then:
```bash
exit
```

## Set audio output
Check devices:
```bash
wpctl status
```
Set AirPods as output:
```bash
wpctl set-default <ID>
```
