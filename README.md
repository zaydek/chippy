# Chippy Code

Chippy Code lets you talk to Claude Code out loud and hear it answer. It is a Claude Code plugin: you speak or type,
and Claude's answer is read aloud while Claude is still writing it.

<!-- Screenshot: Z to choose -->

This repo holds the docs: how to install Chippy, use it and fix it. You can also point your own Claude Code at this repo
(it reads [llms.txt](llms.txt)) and ask it to install Chippy or help you troubleshoot. The plugin's source is not
here.

## What you need

- Linux: Ubuntu 22.04 or later, on x86_64 or arm64, with a desktop session. macOS is coming.
- Claude Code 2.1.287 or later. Check with `claude --version`; update with `claude update`.
- An invite link. Chippy is invite-only for now, and your link is your own: keep it to yourself.
- A mic and speakers or headphones. Headphones work best in Talk.

You don't need an API key. Your invite link is all you need.

## Install

```sh
claude plugin marketplace add <your invite link>
claude plugin install chippy@chippy
```

Then start Claude Code (`claude`) and:

1. Run `/plugin`, go to **Marketplaces**, choose **chippy** and turn on **auto-update**.
2. Run `/chippy doctor`. Every line should start with `ok`. A line that starts with `fix:` says what to do.

That's it. If doctor shows a `fix:` line you can't solve, see Troubleshooting below.

## Your first five minutes

1. **Check your setup.** `/chippy doctor`. Fix anything it flags.
2. **Try Chat.** `/chippy chat`. Your mic stays off. Type a question as usual and press Enter. You'll hear the answer
   while it's written. Type again while it's speaking and it stops to hear you.
3. **Try Talk.** `/chippy` (or `/chippy talk`). Your mic is on. Just say what you want. What you say goes in as your
   prompt, and the answer is spoken. Talk over it to stop it, or say "stop".
   The first time you use Talk or Chat, Chippy sets up its listener. That can take 1 to 3 minutes.
4. **Turn it off.** `/chippy off` closes the mic and stops anything being spoken.
5. **See everything else.** `/chippy help`.

The two modes:

- **Talk**: your mic is on. You speak, it answers out loud.
- **Chat**: your mic is off. You type, it answers out loud.

Versions up to 0.8.3 call these modes **Chat** and **Cafe**. The old words still work for one more release.

## What else it can do

Say "Chippy help" or type `/chippy help` to see everything: playback, voices, speed and volume, and more.

## Updating

With auto-update on (see Install), a new version downloads during a session and loads the next time you start Claude
Code. To update right now:

```sh
claude plugin marketplace update chippy && claude plugin update chippy@chippy
```

Then restart Claude Code. [CHANGELOG.md](CHANGELOG.md) lists what changed.

## Troubleshooting

1. Run `/chippy doctor`. Each line starts with `ok` or `fix:`, and a `fix:` line says what to do.
2. If `/chippy` itself is missing, update Claude Code (`claude update`) and restart it.
3. Still stuck? Say "Chippy feedback:" and describe what happened, in your own words: what you did, what you expected,
   what you heard instead. Chippy sends your words with your last question and answer, its version, your OS and a short
   log with anything key-shaped removed. If you're offline, it's sent the next time you start Claude Code.

## Privacy

What leaves your computer, and where it goes:

- **In Talk:** your mic audio goes to xAI's speech-to-text, to turn it into words. In Chat your mic stays closed.
- **Spoken answers:** the text being read goes to xAI or ElevenLabs to be spoken.
- **Voice cloning:** only with the person present and agreeing out loud; their recording goes to ElevenLabs to make the
  voice, and a copy stays on your computer.
- **Feedback:** sent only when you send it, and only what's listed above.
- **Keys:** they come through your invite link. You never see or handle them.

## License

This repo is MIT licensed ([LICENSE](LICENSE)). The licence covers this repo only; the Chippy plugin, installed through
your invite link, is not covered by it.
