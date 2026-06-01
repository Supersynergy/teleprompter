# Teleprompter

> Mac-native teleprompter that scrolls with your voice using a Rust core, SwiftUI shell, and local whisper.cpp speech recognition.

Teleprompter is for recording scripts, talks, demos, and sales videos without cloud transcription. The app should feel native on macOS, keep audio local, and make the first run obvious for contributors.

## Quick Start

```bash
git clone https://github.com/Supersynergy/teleprompter
cd teleprompter
git status --short
```

This repository was created as a public project shell. Add the app source before expecting a build command to exist.

## Intended Architecture

```text
SwiftUI app
  -> microphone permission + script editor + scroll controls
Rust core
  -> timing, transcript alignment, local state, testable logic
whisper.cpp
  -> local speech recognition, no cloud upload
```

## Product Shape

| Area | Requirement |
|---|---|
| Privacy | All speech recognition runs locally |
| UX | Script stays readable while scroll follows spoken pace |
| Controls | Start, pause, manual speed override, jump back |
| Import | Paste script or open Markdown/plain text |
| Export | Save session settings and script state |

## Development Notes

- Keep the Rust core independent from SwiftUI so timing logic can be tested without launching the app.
- Treat microphone permission, model path, and missing whisper binary as first-run states.
- Put architecture decisions in `docs/adr/` once source code is added.

## License

License is not declared yet. Add one before publishing binaries or accepting external contributions.
