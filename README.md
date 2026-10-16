# Chippy

<p align="center"><img src="icon.png" width="128" height="128" alt="Chippy's icon: a white sound wave on an aqua-to-green square"></p>

Talk to Claude Code out loud, and hear its answers read back to you.

## Getting started: macOS

- **You need:** a Mac with Apple silicon on macOS 13 or later, and Claude Code (`claude --version` prints its version).
- **Install:** paste this into Terminal. It asks once before it installs.

  ```
  curl -fsSL https://chippy.fly.dev | sh
  ```

- **First run:** in a Claude Code chat that was already open, type `/reload-plugins` once. The first time you turn
  Chippy on, macOS asks to let your terminal app use the microphone; click Allow. If you clicked Don't Allow, turn your
  terminal app on in System Settings > Privacy & Security > Microphone.
- **Keys:** none. Chippy needs no API key and no account.
- **Uninstall:** `curl -fsSL https://chippy.fly.dev/uninstall | sh`

## Getting started: Ubuntu

- **You need:** Ubuntu 24.04 or later with its standard desktop, and Claude Code (`claude --version` prints its
  version).
- **Install:** paste this into Terminal. It asks once before it installs.

  ```
  curl -fsSL https://chippy.fly.dev | sh
  ```

- **First run:** in a Claude Code chat that was already open, type `/reload-plugins` once. Ubuntu doesn't ask about the
  microphone: Chippy listens on the input chosen in Settings > Sound.
- **Keys:** none. Chippy needs no API key and no account.
- **Uninstall:** `curl -fsSL https://chippy.fly.dev/uninstall | sh`

## Use

- `/chippy` in a Claude Code chat turns Chippy on there.
- `/chippy off` turns it off.
- `/chippy help` to learn more.

## License

These docs are open source under the MIT license (see [LICENSE](LICENSE)). Chippy itself is not open source.
