# boxctl service

## Usage

```
Usage: boxctl service <subcommand> [service]

Subcommands:
  list                List attached portable services and their state
  start <service>     Start a portable service
  stop <service>      Stop a portable service
  enable <service>    Enable a portable service (start on boot)
  disable <service>   Disable a portable service
```

## Library modules

Uses: [`interact`](../interact.md), [`depends`](../depends.md), [`system`](../system.md)
