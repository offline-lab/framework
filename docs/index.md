# Framework — API Reference

The offline-lab-framework is a bash utility library installed at `/usr/lib/framework/` on the Offline Lab OS. Scripts load it with `source framework || exit 1`.

See the [Builder documentation](https://offline-lab.com/docs/) for buildroot packaging details.

## CLI

`boxctl` is the device management CLI. Run `boxctl help` on the device for interactive help.

| Command | Description |
|---|---|
| [`boxctl confext`](boxctl/confext.md) | Manage configuration extension images in /data/extensions/confext/. |
| [`boxctl config`](boxctl/config.md) |  |
| [`boxctl diagnose`](boxctl/diagnose.md) | Collect diagnostics and write a tarball to /tmp (or <dir>). |
| [`boxctl firewall`](boxctl/firewall.md) | Manage the nftables firewall. |
| [`boxctl logs`](boxctl/logs.md) |  |
| [`boxctl net`](boxctl/net.md) |  |
| [`boxctl power`](boxctl/power.md) | Manage runtime power profile (cpufreq governor + USB autosuspend). |
| [`boxctl reboot`](boxctl/reboot.md) | Reboot the device, optionally into a specific RAUC slot. |
| [`boxctl rollback`](boxctl/rollback.md) | Roll back to the previously installed RAUC slot. |
| [`boxctl screen`](boxctl/screen.md) | Manage HDMI display configuration. |
| [`boxctl service`](boxctl/service.md) |  |
| [`boxctl status`](boxctl/status.md) | Show system health: RAUC slot info, AppArmor, dm-verity, failed units, disk and memory usage. |
| [`boxctl sysext`](boxctl/sysext.md) | Manage system extension images in /data/extensions/sysext/. |
| [`boxctl update`](boxctl/update.md) | Apply a RAUC bundle. |

## Utility modules

| Module | Description | Functions |
|---|---|---|
| [`arguments`](arguments.md) | CLI flag parsing | 3 |
| [`array`](array.md) | operations and predicates | 31 |
| [`cache`](cache.md) | key/value store with TTL | 8 |
| [`credentials`](credentials.md) | random username and password generation | 2 |
| [`depends`](depends.md) | tool availability checks | 7 |
| [`files`](files.md) | merge and deduplication | 2 |
| [`fs`](fs.md) | path and file checks | 16 |
| [`interact`](interact.md) | prompts and user input | 5 |
| [`net`](net.md) | IP, FQDN, email validation | 6 |
| [`prettytable`](prettytable.md) | Unicode terminal table output | 4 |
| [`proc`](proc.md) | command execution and output handling | 10 |
| [`ssh`](ssh.md) | key generation and agent management | 6 |
| [`ssl`](ssl.md) | certificate and key validation | 23 |
| [`string`](string.md) | manipulation and comparison | 17 |
| [`time`](time.md) | formatting and timestamps | 2 |
| [`var`](var.md) | type and value checks | 30 |

## OS-specific modules

| Module | Description | Functions |
|---|---|---|
| [`clock`](clock.md) | clock and RTC management | 2 |
| [`confext`](confext.md) | configuration extension management | 6 |
| [`config`](config.md) | /data/config key/value store | 7 |
| [`fw`](fw.md) | iptables helpers | 12 |
| [`health`](health.md) | system status checks | 7 |
| [`power`](power.md) | power management | 8 |
| [`rauc`](rauc.md) | A/B OTA update operations | 15 |
| [`resources`](resources.md) | CPU, memory, disk monitoring | 8 |
| [`sysext`](sysext.md) | systemd sysext operations | 6 |
| [`system`](system.md) | privilege escalation and sudo keepalive | 3 |
| [`wifi`](wifi.md) | wpa_supplicant management | 11 |
| [`zram`](zram.md) | zram compression device management | 5 |

## Framework internals

| Module | Description | Functions |
|---|---|---|
| [`core`](core.md) | bootstrap and module loader | 0 |
| [`debug`](debug.md) | stack trace and error handling | 5 |
| [`exit`](exit.md) | script termination helpers | 16 |
| [`import`](import.md) | module loading and circular import prevention | 4 |
| [`logging`](logging.md) | leveled output to stderr | 14 |
| [`sanity`](sanity.md) | pre-execution checks | 1 |
