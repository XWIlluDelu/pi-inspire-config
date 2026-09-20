# Inspire personal configuration

Personal presentation profiles for [Pi Inspire](https://github.com/XWIlluDelu/pi-inspire).
This repository contains configuration only, not a fork of the application.

## Profiles

- `profiles/personal.json`: FFF search, Intercom, web tools, and Magic Context presentations.
- `profiles/native.json`: shipped Pi-native presentations, with generic cards for other tools.

Both profiles use the same Inspire code. They do not enable or disable Pi extensions.
Keep credentials, session records, runtime state, logs, and backups out of this repository.

## Use

The local `../inspire` source checkout reads its ignored configuration path,
`.inspire/tool-presentations.json`, through a relative symlink to `profiles/personal.json`.
Edit this tracked profile and refresh the browser; no application rebuild is needed.

On another installation, select a profile in the environment that starts the Host:

```sh
export INSPIRE_TOOL_PRESENTATIONS_PATH=/absolute/path/to/inspire-config/profiles/personal.json
```

For native presentations, select `profiles/native.json` instead. Changing the Host's
configured path requires a restart after active work settles. Alternatively, point the
default configuration path at the chosen file with a symlink; back up any existing file
before replacing it. The selected file is read again on each authenticated browser bootstrap.

## Maintenance

1. Update Inspire from its ordinary `main` branch or release.
2. Edit only the profile needed for the current extension tool shapes.
3. Check the browser after refresh; invalid declarations produce a warning and retain native rules.
4. Commit and push profile changes here, separately from application changes.

The declaration format and limits are documented in Inspire's
[`docs/tool-presentations.md`](https://github.com/XWIlluDelu/pi-inspire/blob/main/docs/tool-presentations.md).
Missing mappings use generic cards; an explicit user mapping replaces the native mapping
for that exact tool name, so only override tools whose extension-provided shapes you use.
