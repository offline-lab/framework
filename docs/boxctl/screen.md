# boxctl screen

Manage HDMI display configuration.

## Usage

```
Usage: boxctl screen <subcommand> [args]

Manage HDMI display configuration. Settings are stored in /data/config and
written to /boot/firmware/config.txt on apply. A reboot is required for
changes to take effect.

Subcommands:
  status                     Show stored screen configuration
  rotate <degrees>           Set display rotation: 0, 90, 180, 270
  resolution <group> <mode>  Set HDMI resolution (hdmi_group and hdmi_mode)
  apply                      Write stored settings to /boot/firmware/config.txt

Common HDMI groups and modes:
  Group 1 (CEA/TV):  mode 4 = 720p60,  mode 16 = 1080p60
  Group 2 (DMT/PC):  mode 35 = 1024x768@60, mode 82 = 1920x1080@60
```

## Library modules

Uses: [`interact`](../interact.md), [`config`](../config.md), [`system`](../system.md)
