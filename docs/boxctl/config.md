# boxctl config

## Usage

```
Usage: boxctl config <subcommand> [args]

Subcommands:
  get <key>           Read a config value
  set <key> <value>   Write a config value
  list                List all config keys
  apply               Apply hostname and timezone from config

Keys (common):
  hostname            Device hostname
  timezone            TZ name (e.g. Europe/Amsterdam)
```

## Library modules

Uses: [`interact`](../interact.md), [`config`](../config.md), [`system`](../system.md)
