# offline-lab-framework

Bash utility library and device management CLI for the [Offline Lab OS](https://offline-lab.com).

API reference: [framework.offline-lab.com](https://framework.offline-lab.com)

---

## What's here

| Directory | Contents |
|---|---|
| `library/` | 36 bash modules — core utilities, OS-specific helpers, CLI framework |
| `bin/` | `boxctl` CLI and subcommands, `framework` shebang interpreter, `chronic` |
| `etc/` | Runtime configuration files |
| `tests/` | BATS unit tests |
| `docs/` | Generated API reference |

### Library modules

**Utilities**

| Module | Purpose |
|---|---|
| `var` | Type and value checks |
| `string` | String manipulation |
| `array` | Array operations |
| `fs` | Filesystem checks |
| `files` | File merge and deduplication |
| `arguments` | CLI flag parsing |
| `depends` | Tool availability checks |
| `interact` | User prompts and input |
| `proc` | Process execution and output |
| `time` | Time formatting and timestamps |
| `cache` | Key/value store with TTL |
| `net` | IP, FQDN, email validation |
| `credentials` | Random username/password generation |
| `ssh` | SSH key generation and agent management |
| `ssl` | Certificate and key validation |
| `prettytable` | Unicode terminal table output |

**OS-specific**

| Module | Purpose |
|---|---|
| `system` | Privilege escalation and sudo keepalive |
| `config` | `/data/config` key/value store |
| `health` | System status checks |
| `rauc` | A/B OTA update operations |
| `wifi` | wpa_supplicant management |
| `clock` | Clock and RTC management |
| `resources` | CPU, memory, disk monitoring |
| `zram` | zram compression device management |
| `fw` | Firewall configuration helpers |
| `power` | Power management |

**Internals**

| Module | Purpose |
|---|---|
| `core` | Bootstrap and module loader entry point |
| `import` | Module loading, circular import prevention |
| `logging` | Leveled output to stderr |
| `exit` | Script termination helpers |
| `debug` | Stack traces and error handling |
| `sanity` | Pre-execution checks |

---

## Using the framework

Scripts on the device source the framework shebang interpreter or the library directly:

```bash
#!/usr/bin/env framework
source framework || exit 1
```

The framework is installed at `/usr/lib/framework/` and placed on `PATH` via `/etc/profile.d/framework.sh`.

---

## Build system

The framework is packaged via the Buildroot `offlinelab-framework` package in the
[builder repository](https://github.com/offline-lab/builder). It is fetched from this
repo at build time — no framework source is committed into the builder repo.

For local development, set the override in your builder's `local.mk`:

```makefile
OFFLINELAB_FRAMEWORK_OVERRIDE_SRCDIR = /path/to/this/repo
```

Then rebuild: `make offlinelab-framework-rebuild`.

---

## Development

```bash
# Clone the repo
git clone git@github.com:offline-lab/framework.git
cd framework

# Set FRAMEWORK_LIB_PATH for interactive use
source bin/dev-setup

# Run the full test suite
bin/test-framework

# Lint + tests
bin/test-framework --lint

# Run one module's tests
bin/test-framework --filter var

# Regenerate API docs
bin/generate-docs
```

---

## Adding a module

1. Create `library/<name>.sh` — functions use `namespace::function` naming, `log::trace "${FUNCNAME[0]}: ..."` in each function body
2. Add module name to `FRAMEWORK_INIT_MODULES` in `library/import.sh` if it should auto-load
3. Create `tests/unit/test_<name>.bats`
4. Run `bin/test-framework --lint`
5. Run `bin/generate-docs` to update the API reference

---

## License

AGPL-3.0-only. See [LICENSE](LICENSE).
