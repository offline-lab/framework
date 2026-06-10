# boxctl sysext

Manage system extension images in /data/extensions/sysext/.

## Usage

```
Usage: boxctl sysext <command>

Manage system extension images in /data/extensions/sysext/.

Commands:
  list      List installed extensions and their merge status
  merge     Merge all extensions into /usr/
  unmerge   Remove merged extensions from /usr/
  refresh   Unmerge then re-merge (picks up new or removed images)
  status    Show current merge state

Extensions are .raw squashfs images stored in /data/extensions/sysext/.
Drop files there and run 'boxctl sysext refresh' to apply them.
```

## Library modules

Uses: [`sysext`](../sysext.md)
