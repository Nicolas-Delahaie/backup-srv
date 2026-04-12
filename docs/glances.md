# Glances

Used for system monitoring, exposed via the Glances web UI so the Pi's health can be checked remotely.

## Install

Installed inside a Python virtualenv to avoid polluting the system Python:

```bash
sudo apt install python3-pip python3-dev gcc
python3 -m venv ~/.venv
source ~/.venv/bin/activate
pip install 'glances[web]'
```

## Service

Glances runs as a systemd service in web mode:

```bash
sudo systemctl daemon-reload
sudo systemctl enable --now glances
```

## Configuration

Set the refresh interval to 60 seconds (default is 2 s).

## Auth

Account creation was attempted but did not work out; the web UI currently runs without authentication. Worth revisiting.
