# Twitch Alerts Kiosk

## What is this?
This project will launch a chromium browser in kiosk mode and display Twitch emotes, cheers, subs, resubs from Twitch chat. It can also display a random gif from Giphy when someone in chat uses:`!giphy IT Crowd`. 

## Instructions

Take control of your project by hosting it on your own server and custom domain, or opt for a seamless experience on GitHub Pages or Cloudflare Pages. With this option, you can access your project from any device with a web browser - think Smart TVs, Fire Sticks, tablets, computers, Raspberry Pi and more. The possibilities are endless!

To unleash the full potential of your project, simply open it in your favorite browser and enjoy it in fullscreen mode. Or, for an immersive experience, launch it in kiosk mode with a single command:
```
chrome --kiosk --start-maximized https://www.example.com
```

And for those who prefer a more traditional approach, you can also double-click the alerts.html file to open it in your default browser. The choice is yours!

### Raspberry Pi Kiosk Setup - with autostart and kiosk mode

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

### Config options

Open alerts.html

You can edit the configuration values here:
```javascript
// Configuration - Settings
let twitchChannel = "";
let twitchChatCommand = "!giphy";
let defaultImage = "./images/glitch_flat_white.png";
let stingerImage = ""
let giphyApiKey = "";
let giphyRating = "pg";
let giphyLang = "en";
let timeOut = 15;
let fontSize = "14";
let fontColor = "white";
let bgColor = "#9146ff";
let raids = true;
let follows = true;
let cheers = true;
let subs = true;
let resubs = true;
let giphy = true;
let emotes = true;
```

Place images inside the images directory and update these values with your own images. Images can be animated gif, png, jpeg. Be sure to refrences to them with `./images/`
```
let defaultImage = "./images/glitch_flat_white.png";
let stingerImage = "./images/technology-twitch-wallpaper-preview.jpg"
```

Set your Twitch channel `let twitchChannel = "MrCoolStreamer";`

Set values to `false` to disable the feature.

### Giphy API
You will need to visit https://developers.giphy.com/ to generate a API key to use with `let giphyApiKey = "";` The Giphy API is limited to 100 requests per hour. 
