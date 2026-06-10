# boxctl reboot

Reboot the device, optionally into a specific RAUC slot.

## Usage

```
Usage: boxctl reboot [<slot>]

Reboot the device, optionally into a specific RAUC slot.
If no slot is given, performs a normal reboot.

Arguments:
  <slot>   RAUC slot name (e.g. rootfs.0, rootfs.1)
```

## Library modules

Uses: [`interact`](../interact.md), [`rauc`](../rauc.md), [`system`](../system.md)
