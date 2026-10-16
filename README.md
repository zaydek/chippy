# Chippy

<p align="center"><img src="icon.png" width="128" height="128" alt="Chippy's icon: a white sound wave on an aqua-to-green square"></p>

Talk to Claude Code out loud, and hear its answers read back to you.

## What you need

- A Mac with Apple silicon, or Ubuntu with its standard GNOME desktop.
- Claude Code. In a terminal, `claude --version` prints its version.

## Install

Paste this into a terminal:

```
curl -fsSL https://chippy.fly.dev | sh
```

It asks once before it installs. In a Claude Code chat that was already open, type `/reload-plugins` once. The first
time you turn Chippy on, a Mac asks you to let your terminal app use the microphone; allow it.

## Use

- Type `/chippy` in a Claude Code chat and choose how you want to use it. That chat is the one Chippy speaks for.
- `/chippy both`: you talk, your words type into the prompt box and send when you pause, and replies are read aloud.
- `/chippy talk`: you talk, and replies stay as text. `/chippy listen`: you type, and replies are read aloud.
- `/chippy off` turns it off. `/chippy help` lists everything else.

To uninstall, run `chippy uninstall` in a terminal.

## License

These docs are open source under the MIT license (see [LICENSE](LICENSE)). Chippy itself is not open source.
