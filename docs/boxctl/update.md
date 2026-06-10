# boxctl update

Apply a RAUC bundle.

## Usage

```
Usage: boxctl update [<bundle>]

Apply a RAUC bundle. If no path is given, searches /mnt for *.raucb files.
Prompts for confirmation before installing.

Arguments:
  <bundle>   Path to a .raucb file (optional — scans /mnt if omitted)
```

## Library modules

Uses: [`interact`](../interact.md), [`rauc`](../rauc.md), [`system`](../system.md)
