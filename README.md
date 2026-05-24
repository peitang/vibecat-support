<p align="center">
  <a href="https://vibecat.app">
    <img src="https://vibecat.app/assets/icons/cat_std_128.png" width="96" height="96" alt="VibeCat" />
  </a>
</p>

<h1 align="center">VibeCat</h1>

<p align="center">
  A Windows control bar for AI coding agents — one pixel cat per live session.
</p>

<p align="center">
  <a href="https://vibecat.app">Website</a>
  ·
  <a href="https://vibecat.app/#download">Download</a>
  ·
  <a href="https://vibecat.app/transparency/">Transparency</a>
  ·
  <a href="https://github.com/peitang/vibecat-support/issues/new?template=bug_report.yml">Report a Bug</a>
  ·
  <a href="https://github.com/peitang/vibecat-support/issues/new?template=feature_request.yml">Request a Feature</a>
</p>

<p align="center">
  <img src="https://vibecat.app/assets/icons/cat_std_128.png" width="54" height="54" alt="STD" />
  <img src="https://vibecat.app/assets/icons/cat_edit_128.png" width="54" height="54" alt="EDIT" />
  <img src="https://vibecat.app/assets/icons/cat_alert_128.png" width="54" height="54" alt="ALERT" />
  <img src="https://vibecat.app/assets/icons/cat_wait_128.png" width="54" height="54" alt="COMPACT" />
</p>

---

## What is VibeCat

VibeCat sits above your Windows terminals and gives every AI coding agent a visible state: idle, editing, waiting for permission, or compacting context. It is built for developers running multiple agent sessions at once and needing to approve, answer, and jump back to the exact terminal without losing flow.

- **One glance status** — STD, EDIT, ALERT, and COMPACT states map to the agent work you actually care about.
- **Permission flow** — approve tool calls and answer agent questions from the VibeCat surface.
- **Terminal jump** — return to the matching Windows Terminal, WezTerm, VS Code, Cursor, or IDE terminal session.
- **Windows native** — designed for Windows 11 workflows and local developer machines.
- **Private by default** — source code, raw logs, prompts, terminal output, license keys, and payment data do not belong in this public repo.

## Quick Start

1. Download VibeCat from [vibecat.app](https://vibecat.app/#download).
2. Install and open the Windows app.
3. Connect your supported coding tools from the VibeCat integrations/settings surface.
4. Run your agent sessions as usual.
5. For bug reports, first create and upload a support bundle in VibeCat, then paste the returned `SUP-...` Support ID into the GitHub issue form.

## Repositories

| Repository | Purpose |
| --- | --- |
| [`peitang/vibecat-support`](https://github.com/peitang/vibecat-support) | Public bug reports, feature requests, and support intake. |

## Supported Tools

VibeCat is designed around agent-heavy coding sessions, including:

Claude Code · Codex · Gemini CLI · Aider · Cursor Agent · generic CLI wrappers

## Supported Terminals & IDEs

Windows Terminal · WezTerm · VS Code · Cursor · ConEmu · JetBrains terminals · generic Windows console hosts

## Public Support Rules

This repository is public. Keep reports high-level and safe to share.

Do **not** upload or paste:

- Source code from private repositories
- Private repository links
- Raw logs, prompts, agent replies, terminal output, or command lines
- License keys, API tokens, payment details, email addresses, or other secrets
- Crash dumps or diagnostic reports you have not reviewed locally

For bugs, use VibeCat's **Create and Upload Support Bundle** action and paste only the returned Support ID into GitHub. Do not attach raw diagnostic files unless support explicitly asks and you have reviewed them locally.

## Issue Templates

- [Bug report](https://github.com/peitang/vibecat-support/issues/new?template=bug_report.yml)
- [Feature request](https://github.com/peitang/vibecat-support/issues/new?template=feature_request.yml)
- Private/security support: [support@vibecat.app](mailto:support@vibecat.app)

---

Made for Windows developers who run more than one coding agent at a time.
