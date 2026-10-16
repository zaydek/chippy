# Chippy privacy

Last updated: 2026-10-16. This covers Chippy 0.9.26, installed with `curl -fsSL https://chippy.fly.dev | sh`.

## In short

- While the mic is open, what it hears goes to xAI to be turned into words. The replies Chippy reads aloud go to xAI to
  be spoken. Both pass through Chippy's own server, which adds Chippy's xAI key and passes them on.
- Feedback goes only when you send it, and only its words.
- Everything else Chippy keeps stays on your computer, in the folders listed below.

## What it reads

- **Your microphone**: in Talk and in Talk + Listen, while it is not muted; in any mode while you hold the record
  button. In Listen alone, muted or off, the mic stays closed.
- **This chat in Claude Code**: Claude's replies, to read them aloud and show them above the chat bar, and your messages,
  to show them beside the replies.
- **The prompt box**: Chippy types what you said into it, and checks it is still as Chippy left it before sending it.
- **Your sound setup**: your list of microphones, the output device and the system volume.
- **What it runs inside**: your terminal app and its version, tmux or zellij, whether you are connected over ssh, how it
  presses Enter, and your OS, its version, and on Linux the distro and display.
- **Your settings** for Chippy.
- **Your SSH public keys**, only if Chippy on this computer has no sign-in of its own: it may sign in with an SSH key you
  already use with GitHub, the way `git push` does. It sends the public key and a one-time signature, never the private
  key.

It never reads your clipboard. It writes to it only when you ask it to copy something.

## What it keeps on this computer

| What | Where | How long, how big |
| --- | --- | --- |
| The last 10 minutes of your mic | Memory only, never on disk | Gone when Chippy turns off; paused while muted or in Listen; about 58 MB of memory |
| Clips you ask for ("clip the last minute") | `~/.cache/chippy/clips/` | Until you delete them; no limit |
| The audio of spoken feedback | `~/.cache/chippy/feedback/` | Until you delete it; it is never sent |
| Feedback that could not be sent yet | `~/.cache/chippy/feedback-queue.jsonl` | Until it is sent, at Chippy's next start |
| Spoken replies, their audio and words, so a repeat is not made twice | `~/.cache/chippy/tts/` | Each chat's last 200 sentences or 24 hours, at most 2,000 sentences |
| Replies made for the Play button | `~/.cache/chippy-reader/takes/` | Up to 500 MB; the least recently played go first |
| What you said with the record button, and its words | `~/.cache/chippy-reader/voice/` | Until you delete it; no limit |
| Settings | `~/.claude/plugins/store/` (the `chippy_` file) and `~/.cache/chippy/listener-settings.json` | Until you delete them |
| A full log, including what you and Claude said, word for word | `/tmp/jarvis-live/live.log` | Added to while Chippy runs; no limit; your computer's temporary folder |
| Start times, and a line for each copy (its time, size and first 20 characters) | `~/.cache/chippy/starts.log`, `~/.cache/chippy/copies.log` | Until you delete them |
| The app, its sign-in, an install id, and your GitHub name if you signed in | Chippy's app folder in your home folder | Until you uninstall (the uninstall below removes it) |
| The `chippy` command | `~/.local/bin/chippy` | Until you uninstall |
| The Claude Code plugin | `~/.claude/plugins/cache/zaydek/chippy/` | Until you uninstall |
| Node.js, only if your computer had no Node 18 or newer | A Node.js folder beside Chippy's app folder | Shared with other apps installed the same way |

## What it sends, to whom, and when

| What | To | When |
| --- | --- | --- |
| Your mic's audio, as it hears it | xAI's speech-to-text, through Chippy's own server | While the mic is open in Talk or Talk + Listen and not muted |
| A record-button recording | xAI's speech-to-text, through Chippy's own server | When you let go of the button |
| The text of each reply it reads aloud | xAI's text-to-speech, through Chippy's own server | In Listen and Talk + Listen, and when you press Play; a line it has made before is played from disk instead |
| An install id, when this computer had Chippy before | chippy.fly.dev | When you run the install line |
| A sign-in with GitHub, if you choose it (you can continue as a guest) | chippy.fly.dev and GitHub | Right after you install, or with `curl -fsSL https://chippy.fly.dev \| sh -s sign-in` |
| A check for a newer version: Chippy's version, your OS and CPU type, and this install's sign-in | Chippy's own server | Each time a Claude Code chat starts; a new version downloads only when you run `chippy update` |
| What it runs inside (the list under "What it reads") | Chippy's own server | Once per Claude Code chat |
| Your feedback's words, up to 4,000 characters | Chippy's own server, for Chippy's author | Only when you send feedback (`/chippy feedback <words>`, or saying "send feedback") |
| A check that the speech service answers | Chippy's own server | When you run `/chippy doctor` |
| Node.js, if your computer has no Node 18 or newer | nodejs.org | Once, when Chippy is first set up |

`/chippy off` closes the mic and stops all speech. The version check and the once-per-chat report go whenever a Claude
Code chat starts with Chippy installed; uninstalling stops them.

## What it never sends

- The clips, recordings, spoken-feedback audio and logs it keeps on your computer.
- Your typed prompts, and any reply it does not read aloud.
- Your microphone in Listen (unless you hold the record button), while muted, or while Chippy is off.
- Counts of which features you use: this install has nowhere to send them.

No key is kept on your computer, and Chippy never asks you for one.

## How to delete it

- In Claude Code: `/chippy uninstall`, answer Yes, then answer Yes to "Also delete your settings and saved mic clips?"
- Or in a terminal: `curl -fsSL https://chippy.fly.dev/uninstall | sh -s -- --all`

Uninstalling can leave some of these behind, so delete any that are still there:

```sh
rm -rf ~/.cache/chippy ~/.cache/chippy-reader /tmp/jarvis-live
rm -f ~/.claude/plugins/store/chippy_*.json ~/.local/bin/chippy
```

## Changes

A change to this page is published here, with a new date at the top, when a version that needs it ships.

## Contact

Open an issue at https://github.com/zaydek/chippy/issues.
