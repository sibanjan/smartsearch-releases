# SmartSearch for Windows

Search your files by meaning, keywords or name, and browse your pictures by what they show.
Search runs on your computer: after a one-time download of its search models, nothing from your
files is sent anywhere.

This repository only hosts the downloads. Get the latest version from
[Releases](https://github.com/sibanjan/smartsearch-releases/releases/latest).

## Install

**Setup program:** download `SmartSearch-Setup-<version>.exe` from the
[latest release](https://github.com/sibanjan/smartsearch-releases/releases/latest) and run it.
It installs for your account only (no admin). The installer is not code-signed, so Windows
SmartScreen asks first: choose **More info → Run anyway**.

**If Windows says "An Application Control policy has blocked this file"**, Smart App Control is
on, and it blocks unsigned programs with no override. Paste this into PowerShell instead:

```powershell
irm https://github.com/sibanjan/smartsearch-releases/releases/latest/download/install.ps1 | iex
```

It runs only the signed Python runtime and packages from PyPI, and sets up the same thing as the
setup program: a Start menu shortcut, an option to start at sign-in, and an entry in
Settings → Apps. Run the same command again to upgrade.

## Requirements

- 64-bit Windows 10 (1809 or later) or Windows 11
- Microsoft Edge WebView2 (Windows 11 already has it)
- About 300 MB of disk for the app, plus about 700 MB for the search models

## Privacy

Search and image grouping run on your computer. The optional **Ask** assistant can also run
locally (with [Ollama](https://ollama.com/download)), or with Claude, which sends your
question and the file excerpts it reads to Anthropic. Setup explains each choice.

## Uninstall

Settings → Apps → SmartSearch → Uninstall. Your index and settings in
`%USERPROFILE%\.smartsearch` and the models in `%USERPROFILE%\.cache\huggingface` are kept;
delete those folders to remove them too.

## Problems

Open an [issue](https://github.com/sibanjan/smartsearch-releases/issues). The logs are in
`%USERPROFILE%\.smartsearch\app.log` and `daemon.log`.
