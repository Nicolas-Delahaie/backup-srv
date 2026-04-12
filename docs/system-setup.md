# Base system setup

OS-level tweaks applied to the Pi before installing any of the services.

## Shell

Zsh with Oh My Zsh is installed and set as the default shell for the main user.

## Wi-Fi power save

The Wi-Fi adapter's power save mode is disabled so the AirPlay receiver stays reachable at all times:

```bash
iw dev wlan0 set power_save off
```

This needs to be made persistent across reboots (currently applied at runtime only).
