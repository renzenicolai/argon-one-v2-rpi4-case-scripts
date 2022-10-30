# Scripts for controlling the Argon ONE V2 RPi4 case

Argon provides a "proprietary" script to control the functions the case provides.

This repository contains some scripts and service files to replace that script with some simple bash scripting.

## How to install the fan control script

First copy the `argonfan`, `argonfan.service` and `argonfan.timer` files from this repository to your Pi. Then move the files to their final location and enable the Systemd timer to automatically run the script every 10 seconds.

```
sudo mv argonfan /usr/local/bin/argonfan
sudo chmod +x /usr/local/bin/argonfan
sudo mv argonfan.service /etc/systemd/system/argonfan.service
sudo mv argonfan.timer /etc/systemd/system/argonfan.timer
sudo systemctl enable --now argonfan.timer
```

## How to install the power cut signal script

```
sudo mv argonpowercut /usr/lib/systemd/system-shutdown/argonpowercut
sudo chmod +x /usr/lib/systemd/system-shutdown/argonpowercut
```

## License

CC0 / Public domain
