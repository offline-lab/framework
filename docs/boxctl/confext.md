# boxctl confext

Manage configuration extension images in /data/extensions/confext/.

## Usage

```
Usage: boxctl confext <command>

Manage configuration extension images in /data/extensions/confext/.

Commands:
  list      List installed extensions and their merge status
  merge     Merge all extensions into /etc/
  unmerge   Remove merged extensions from /etc/
  refresh   Unmerge then re-merge (picks up new or removed images)
  status    Show current merge state

Extensions are .raw squashfs images stored in /data/extensions/confext/.
Drop files there and run 'boxctl confext refresh' to apply them.
```

## Library modules

Uses: [`confext`](../confext.md)
