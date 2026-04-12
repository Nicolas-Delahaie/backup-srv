# Notes for Claude

See [README.md](README.md) for what this project is and what the machine does.

## Conventions

- **Everything in English.** Code, docs, comments, commit messages. This project is intended to be published. **Exception:** files under `todo/` are written in French — they are the user's personal notes.
- **Keep the README high-level.** No commands, flags, or config snippets in it. Technical details go into per-topic files under [docs/](docs/).
- **Do not touch the `todo/` directory.** It holds the user's personal draft notes, is gitignored, and is not ready to be worked on unless the user explicitly asks.
- **Sensitive information is split across two gitignored files:** [confidential.md](docs/confidential.md) holds operational notes (how to reach the Pi, what lives where), while `.env` at the repo root holds the raw secret _values_ (passwords, tokens, broker credentials). Read them when you need real hostnames, credentials, or tokens — and never copy their contents into README, CLAUDE.md, or anything under `docs/`.
- No application code lives here — actions actually happen on the Pi, not in this repo. This repo is the memory of how the Pi was set up, plus (eventually) the scripts that configure and update it.
