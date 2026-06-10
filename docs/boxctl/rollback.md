# boxctl rollback

Roll back to the previously installed RAUC slot.

## Usage

```
Usage: boxctl rollback

Roll back to the previously installed RAUC slot.

Finds the inactive rootfs slot, marks it as the boot target, and offers
to reboot. The current slot is not modified — you can roll forward again
by running: boxctl update
```

## Library modules

Uses: [`interact`](../interact.md), [`rauc`](../rauc.md), [`system`](../system.md)
