# Zigbee2MQTT (snap)

Snap (Snapcraft.yaml) recipe for Zigbee2MQTT that allows you to use your Zigbee devices without the vendors bridge or gateway.

This page will only include specific information about this unofficial snap-version of Zigbee2MQTT. For general Zigbee2MQTT information, see [zigbee2mqtt.io](https://www.zigbee2mqtt.io/)

[![Get it from the Snap Store](https://snapcraft.io/static/images/badges/en/snap-store-black.svg)](https://snapcraft.io/janlochi-zigbee2mqtt)

## Looking for feedback

This snap recipe is in early stages of development, your feedback would be appreciated. Just open an issue on GitHub.

## Versioning

The snap version consists of the zigbee2mqtt release tag and an additional ascending number (e.g. 0.15.0-1).

## Installation
### Install from The Snap Store

Make sure you have snapd installed on your system. See [Installing snapd](https://snapcraft.io/docs/installing-snapd) for a list of distributions with and without snap pre-installed, including installation instructions for those that have not.

```bash
$ snap install epi-zigbee2mqtt
```

### Setup

It's required to manually connect the serial port to the snap and enable the experimental hotplug support in snapd (at least 2.39). For additional information see [Hotplug support | Snapcraft documentation](https://snapcraft.io/docs/hotplug-support).

```bash
$ snap set system experimental.hotplug=true
$ systemctl restart snapd.service
$ snap interface serial-port
# Connect the serial-port plug in the epi-zibbee2mqtt to whatever the hotplugged slot name is
# Example here for the Sonoff Zigbee Dongle
$ snap connect epi-zigbee2mqtt:serial-port snapd:sonoffzigbee30usbdo
```

### Configuration

The `configuration.yaml` is located in `/var/snap/epi-zigbee2mqtt/current` and initially populated with a default configuration suitable for the snap.

Use `snap restart janlochi-zigbee2mqtt` after editing the yaml file.
