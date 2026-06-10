# boxctl diagnose

Collect diagnostics and write a tarball to /tmp (or <dir>).

## Usage

```
Usage: boxctl diagnose [--output <dir>]

Collect diagnostics and write a tarball to /tmp (or <dir>).

Collects:
  - RAUC slot status
  - Failed systemd units + their journals
  - AppArmor denials (dmesg)
  - Last boot log
  - Current boot log
  - WiFi status
  - Disk and memory usage

Options:
  --output <dir>   Write tarball to this directory (default: /tmp)
```

## Library modules

Uses: [`interact`](../interact.md), [`rauc`](../rauc.md), [`health`](../health.md), [`wifi`](../wifi.md), [`system`](../system.md)
