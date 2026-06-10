# offline-lab-framework — Agent Instructions

This repo is the bash utility library and device management CLI for Offline Lab OS.
The [builder repo](https://github.com/offline-lab/builder) packages it for Buildroot.

**Kanban board:** [Project 5](https://github.com/orgs/offline-lab/projects/5)

---

## Key constraints

- Never run `git commit`, `git push`, or `git amend` — user handles all git operations
- All library modules live in `library/` — no source outside that directory
- Every function must call `log::trace "${FUNCNAME[0]}: ..."` as its first log statement
- Every public function needs a test in `tests/unit/test_<module>.bats`
- Run `bin/test-framework --lint` before claiming any change is done
- No binaries or compiled artifacts committed

---

## Test and lint

```bash
source bin/dev-setup              # set FRAMEWORK_LIB_PATH for local dev
bin/test-framework --lint         # shellcheck + shfmt + full bats suite
bin/test-framework --filter var   # run one module's tests
```

---

## Doc generation

```bash
bin/generate-docs                  # regenerate docs/ from library source
bin/generate-docs --dry-run        # preview without writing
```

Output goes to `docs/`. Published at [framework.offline-lab.com](https://framework.offline-lab.com).
The builder repo also runs this generator to produce its own `docs/framework/` section.

---

## Module conventions

```bash
# Module file: library/<name>.sh
# Functions: <namespace>::<verb> — e.g. var::is_set, fs::exists

function var::is_set() {
    log::trace "${FUNCNAME[0]}: checking if variable is set"
    [[ "${#}" -ne 1 ]] && exit::error "${FUNCNAME[0]}: exactly 1 argument required"
    ...
}
```

- All variables use `FRAMEWORK_` prefix
- Non-init modules must be explicitly imported: `import var string array`
- Add module name to `FRAMEWORK_INIT_MODULES` in `library/import.sh` if it should auto-load
- Framework internals: `core`, `import`, `logging`, `exit`, `debug`, `sanity`

---

## Adding a module

1. Create `library/<name>.sh`
2. Add to `FRAMEWORK_INIT_MODULES` in `library/import.sh` (if auto-load)
3. Create `tests/unit/test_<name>.bats`
4. Run `bin/test-framework --lint`
5. Run `bin/generate-docs`
6. Add entry to README.md module table
