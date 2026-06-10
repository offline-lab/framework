# boxctl logs

## Usage

```
Usage: boxctl logs [options]

Options:
  -u, --unit <unit>     Filter by systemd unit
  -p, --priority <p>    Min priority: emerg|alert|crit|err|warning|notice|info|debug
  -n, --lines <n>       Number of lines (default: 50)
  -f, --follow          Follow live output
  --boot                Show current boot only
```

## Library modules

Uses: [`depends`](../depends.md)
