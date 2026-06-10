# boxctl firewall

Manage the nftables firewall.

## Usage

```
Usage: boxctl firewall <command>

Manage the nftables firewall.

Commands:
  list      Show the current ruleset (nft list ruleset)
  reload    Reload static rules and per-app fragments
  reset     Flush all rules and remove firewall state
  up        Load rules (same as reload; used after down)
  down      Flush all rules and mark firewall inactive
```

## Library modules

Uses: [`fw`](../fw.md)
