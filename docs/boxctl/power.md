# boxctl power

Manage runtime power profile (cpufreq governor + USB autosuspend).

## Usage

```
Usage: boxctl power [<subcommand>]

Manage runtime power profile (cpufreq governor + USB autosuspend).

Subcommands:
  get           Show the active profile (default)
  set <name>    Persist and apply a profile
  apply         Re-apply the persisted profile — called at boot by power-profile.service
  list          List available profiles

Profiles:
  performance   CPU governor: performance, USB autosuspend: disabled
  balanced      CPU governor: schedutil,   USB autosuspend: 2000ms  (default)
  saver         CPU governor: powersave,   USB autosuspend: 500ms
```

## Library modules

Uses: [`config`](../config.md), [`power`](../power.md), [`system`](../system.md)
