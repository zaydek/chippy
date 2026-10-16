# Chippy

<p align="center"><img src="icon.png" width="128" height="128" alt="Chippy's icon: a white sound wave on an aqua-to-green square"></p>

Talk to Claude Code out loud, and hear its answers read back to you.

## Getting started

- **You need:** Claude Code (`claude --version` prints its version). Chippy needs no API key and no account.
- **Install:** paste this into a terminal. It asks once before it installs.

  ```
  curl -fsSL https://chippy.fly.dev | sh
  ```

- **First run:** in a Claude Code chat that was already open, type `/reload-plugins` once, then `/chippy`.
- **Uninstall:** `curl -fsSL https://chippy.fly.dev/uninstall | sh`

**macOS:** Apple silicon, macOS 13 or later. The first time you turn Chippy on, macOS asks to let your terminal app use
the microphone; click Allow. If you clicked Don't Allow, turn your terminal app on in System Settings > Privacy &
Security > Microphone.

**Ubuntu:** 24.04 or later with its standard desktop. Ubuntu doesn't ask about the microphone: Chippy listens on the
input chosen in Settings > Sound.

## Use

- `/chippy`: Chippy works in this chat; choose Talk, Listen or both.
- `/chippy off`: Chippy stops in this chat.
- `/chippy help` to learn more.

## Privacy

Chippy keeps your settings and logs on your computer, and sends what your mic hears and the replies it reads aloud to xAI for speech. [PRIVACY.md](PRIVACY.md) has the details.

## License

These docs are open source under the MIT license (see [LICENSE](LICENSE)). Chippy itself is not open source.
