---
name: sublime-text
description: "Use when customizing or extending Sublime Text (ST) — writing plugins, editing settings/keymaps, or installing packages. Aliases: ST, Sublime, subl."
---

# Sublime Text

Customize and extend Sublime Text via the `subl` CLI and by editing its package/config files. Use it to:

- Write or fix a plugin (a Python package)
- Edit settings, keybindings, or snippets
- Install, disable, or override a package without the GUI
- Open a file at a specific line/column for review

Don't use for: Git workflows (that's Sublime Merge) or Sublime Text 2 (different paths/API).

## Where things live

| Platform | Data dir | Note |
|---|---|---|
| macOS | `~/Library/Application Support/Sublime Text/` | `subl` at `/Applications/Sublime Text.app/Contents/SharedSupport/bin/subl` (symlink onto PATH) |
| Linux | `~/.config/sublime-text/` | `sublime-text-3` for ST3 |
| Windows | `%APPDATA%\Sublime Text\` | |

Inside the data dir:
- `Packages/` — user packages as **folders**; overrides live here (highest precedence).
- `Packages/User/` — your settings, keymaps, snippets, and overrides. User prefs = `Preferences.sublime-settings`.
- `Installed Packages/` — installed packages as **zips** (`.sublime-package`). Don't hand-edit; override via `Packages/` instead.
- `User/Preferences.sublime-settings` → `ignored_packages` list disables/enables a package (applies on save).

Precedence, low → high: `Packages/Default` → shipped → installed → other user packages → `Packages/User`.

## The `subl` CLI

How an agent drives ST. `subl --help` lists flags (they vary per OS).
- `subl file.py:42:10` — open at line 42, column 10 (`:line` or `:line:column` suffix)
- `subl -n file` / `--new-window` — new window; `subl --add file` — add to the open window
- `subl --background file` — open without stealing focus; `subl -w file` — wait for close
- `subl --command save_all` — run a named Sublime/package command headlessly
- `subl --project My.sublime-project` — Open the named project
- `subl --safe-mode` — clean sandboxed instance

macOS, if `subl` isn't on PATH: `ln -s "/Applications/Sublime Text.app/Contents/SharedSupport/bin/subl" ~/bin/subl`

## Writing a plugin

1. Make `Packages/<MyPlugin>/` (or work in a git repo and symlink it there).
2. Add `.py` files using `sublime` + `sublime_plugin` (commands subclass `sublime_plugin.Command`; listeners subclass `sublime_plugin.Plugin`/`Listener`).
3. ST watches `Packages/` and reloads changed Python plugins automatically — some changes still need a restart.
4. Debug from the Sublime console (`View → Show Console`, `Cmd/Ctrl+): `print` to log, `view.run_command(...)` to test in place.
5. Confirm the build supports the API — newer plugin APIs need ST build ≥4050 (Python 3.8+); `subl -v` shows the build.

Install **Package Reloader** for auto-reload on save during dev.

## Install / override (no GUI)

- Install: `git clone <repo> <Packages>/<PackageName>` (folder name = package name) or drop a `.sublime-package` into `Installed Packages/`.
- Override one file from an installed package: create `Packages/<Name>/` (folder name = the `.sublime-package` name minus the extension) with only the changed files.
- Enable/disable: add/remove the name in `ignored_packages` in `User/Preferences.sublime-settings`.

## Verification

- `subl -v` for the build/version.
- Open the console and confirm no red tracebacks after a plugin change.
- For settings, re-read the on-disk file to confirm the value; some changes apply only on save or restart.

## References

- Official docs: https://www.sublimetext.com/docs/
- CLI reference: https://www.sublimetext.com/docs/command_line.html
- Community guide (packages/extensibility): https://docs.sublimetext.io/guide/
- List of default commands: https://docs.sublimetext.io/reference/commands.html
- Package Control: https://packagecontrol.io/ · Sublime-LSP: https://lsp.sublimetext.io/
