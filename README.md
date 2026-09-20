# Inspire personal configuration

Personal presentation profiles for [Pi Inspire](https://github.com/XWIlluDelu/pi-inspire).
Shared as examples to adapt to your own tools. This repository contains configuration
only, not a fork of the application.

## Profiles

- `profiles/personal.json`: FFF search, Intercom, web tools, and Magic Context presentations.
- `profiles/native.json`: shipped Pi-native presentations, with generic cards for other tools.

Both profiles use the same Inspire code. They do not enable or disable Pi extensions.
Keep credentials, session records, runtime state, logs, and backups out of this repository.

## Use

Clone this repository, then select a profile in the environment that starts the Host:

```sh
git clone https://github.com/XWIlluDelu/pi-inspire-config.git
export INSPIRE_TOOL_PRESENTATIONS_PATH=/absolute/path/to/pi-inspire-config/profiles/personal.json
```

Replace the example path with the absolute path to your clone. Edit the selected profile
and refresh the browser; no application rebuild is needed.

The personal profile maps `grep` and `find` to FFF-specific presentations. If you use Pi's
native tools instead, remove those two mappings or start with `profiles/native.json`.
Only retain mappings that match your installed tools.

For native presentations, select `profiles/native.json` instead. Changing the Host's
configured path requires a restart after active work settles. Alternatively, point the
default configuration path at the chosen file with a symlink; back up any existing file
before replacing it. The selected file is read again on each authenticated browser bootstrap.

## Maintenance

1. Update Inspire from its ordinary `main` branch or release.
2. Edit only the profile needed for the current extension tool shapes.
3. Check the browser after refresh; invalid declarations produce a warning and retain native rules.
4. Keep your profile changes versioned separately from application changes.

The declaration format and limits are documented in Inspire's
[`docs/tool-presentations.md`](https://github.com/XWIlluDelu/pi-inspire/blob/main/docs/tool-presentations.md).
Tools without a user mapping keep Inspire's native rule when one exists; otherwise they
use a generic card. An explicit user mapping replaces the native mapping for that exact
tool name, so only override tools whose extension-provided shapes you use.
