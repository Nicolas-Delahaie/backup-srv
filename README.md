# Backup server

A Raspberry Pi 2B running in the living room, primarily used as a backup target for the main home server (see the `home-srv` repo). Since the hardware is always on, it has also been put to work as an AirPlay 2 audio receiver for the living-room speakers, reporting playback metadata to Home Assistant.

This repository holds the setup documentation for the machine and will host the update and configuration scripts that drive its services as they get written.

## Why "backup"

The Pi's primary purpose is to back up the home server. The AirPlay receiver is a bonus use of otherwise-idle hardware.

## What the Pi runs

- **Backup target** — the main reason it exists, driven from the `home-srv` side.
- **AirPlay 2 audio receiver** — streams sound to the living-room speakers, and publishes the currently-playing track metadata to Home Assistant over MQTT. The MQTT client only exists to back this AirPlay metadata pipeline.
- **System monitoring** — Glances is exposed over HTTP so the machine's health can be checked remotely.
- **Base OS tweaks** — shell customizations and a few networking tweaks to keep the receiver reachable at all times.

## Documentation

Per-topic setup notes live in [docs/](docs/):

- [docs/shairport-sync.md](docs/shairport-sync.md) — AirPlay 2 receiver and MQTT metadata bridge.
- [docs/glances.md](docs/glances.md) — system monitoring web UI.
- [docs/system-setup.md](docs/system-setup.md) — base OS tweaks (shell, Wi-Fi).

## Long-term goal

Turn the manual setup steps into reproducible install and update scripts, living alongside the docs in this repo.
