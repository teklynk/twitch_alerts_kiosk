# Twitch Alerts Kiosk

## What is this?
This project will launch a chromium browser in kiosk mode and display Twitch emotes, cheers, subs, resubs from Twitch chat. It can also display a random gif from Giphy when someone in chat uses:`!giphy IT Crowd`. 

## Instructions

Clone or download this repo to the desktop

Open the default terminal program

Make a autostart directory
```bash
mkdir /home/$USER/.config/autostart
```
Make a kiosk.desktop file
```bash
nano /home/$USER/.config/autostart/kiosk.desktop
```
Add this to the kiosk.desktop file
```bash
[Desktop Entry]
Type=Application
Name=Kiosk
Exec=/usr/bin/bash /home/<your_username>/Desktop/twitch_alerts_kiosk/kiosk.sh
```

### Raspberry Pi 3 with composite video out
```bash
sudo nano /boot/firmware/config.txt
```
Add this to the last line or update this value if it already exists.
`dtoverlay=vc4-kms-v3d,composite`