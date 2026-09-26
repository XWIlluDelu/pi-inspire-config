# INSΠRE customizations

User-owned presentation profiles for [INSΠRE](https://github.com/XWIlluDelu/pi-inspire),
adapted to the Pi extensions you use. INSΠRE provides the shared interface and
rendering engine; your profile supplies presentation rules and tool mappings.

## Profiles

- [`profiles/personal.json`](profiles/personal.json): FFF search, Intercom, web tools, and Magic Context presentations.
- [`profiles/native.json`](profiles/native.json): an empty starting profile that uses INSΠRE's built-in Pi presentations and generic cards for other tools.

Keep mappings that match your Pi setup. The personal profile maps `grep` and `find`
to FFF rules; remove those mappings if you use Pi's native tools instead.

## Set up

Keep this repository in your user configuration directory, separately from the
application checkout. On Linux:

```sh
customizations="${XDG_CONFIG_HOME:-$HOME/.config}/inspire/customizations"
git clone https://github.com/XWIlluDelu/pi-inspire-customizations.git "$customizations"
export INSPIRE_TOOL_PRESENTATIONS_PATH="$customizations/profiles/personal.json"
```

Set the variable in the environment that starts the INSΠRE Host. Changing the
configured path takes effect after a Host restart. Alternatively, link INSΠRE's
[default configuration file](https://github.com/XWIlluDelu/pi-inspire/blob/main/docs/tool-presentations.md#configuration-location)
to your chosen profile.

## Customize

Edit the selected JSON file and refresh the browser to apply it. The
[declaration reference](https://github.com/XWIlluDelu/pi-inspire/blob/main/docs/tool-presentations.md)
covers tool and Thinking presentations, field selectors, and supported blocks.

Version and share your profiles independently of INSΠRE releases. Keep credentials
and runtime data outside this repository.
