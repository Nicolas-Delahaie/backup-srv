# Shairport Sync

Acts as the AirPlay 2 audio receiver and publishes playback metadata to Home Assistant over MQTT. NQPTP is required for AirPlay 2 and must be installed and running alongside it.

## Build

Shairport Sync must be built with AirPlay 2 support and with the MQTT metadata client enabled.

```bash
./configure \
  --sysconfdir=/etc \
  --with-alsa \
  --with-soxr \
  --with-avahi \
  --with-ssl=openssl \
  --with-systemd-startup \
  --with-airplay-2 \
  --with-metadata \
  --with-mqtt-client

make clean
make
sudo make install
sudo systemctl restart shairport-sync
```

Note: `--with-metadata` is implied by `--with-mqtt-client`, but it is kept explicit for clarity.

## Configuration

Configuration lives in `/etc/shairport-sync.conf`:

- The MQTT client block points at the broker running on Home Assistant.
- The audio `range` setting has been lowered from the default `60` to `40`.

## Related

- NQPTP is a separate daemon; follow its upstream install instructions.
- The Mosquitto broker and the Home Assistant integration are configured on the HA side to receive and ingest the metadata published by this client.
