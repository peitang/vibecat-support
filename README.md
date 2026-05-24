<p align="center">
  <a href="https://vibecat.app">
    <img src="https://vibecat.app/assets/icons/cat_std_128.png" width="128" height="128" alt="VibeCat" />
  </a>
</p>

<h1 align="center">VibeCat</h1>

<p align="center">
  <em>One bar for every coding agent.</em>
</p>

<p align="center">
  A floating Windows 11 control surface for Claude Code, Codex, Cursor, Aider and friends.<br/>
  Every live session in one place — pixel-status, hook approvals, terminal teleports.
</p>

<p align="center">
  <strong>English</strong> ·
  <a href="README.zh-TW.md">繁體中文</a> ·
  <a href="README.zh-CN.md">简体中文</a> ·
  <a href="README.ja.md">日本語</a> ·
  <a href="README.ko.md">한국어</a>
</p>

<p align="center">
  <a href="https://vibecat.app"><img alt="Website" src="https://img.shields.io/badge/website-vibecat.app-4DA8FF?style=flat-square&labelColor=15171c"></a>
  <a href="https://vibecat.app/#download"><img alt="Download" src="https://img.shields.io/badge/download-Windows%2011-4DD9A8?style=flat-square&labelColor=15171c"></a>
  <a href="https://vibecat.app/#pricing"><img alt="License" src="https://img.shields.io/badge/one--time-USD%2021.99-FFB347?style=flat-square&labelColor=15171c"></a>
  <a href="https://vibecat.app/transparency/"><img alt="Transparency" src="https://img.shields.io/badge/transparency-report-7B7BD1?style=flat-square&labelColor=15171c"></a>
</p>

---

## / 01 — Four states the cat can hold.

<table align="center">
  <tr>
    <td align="center" width="160">
      <img src="https://vibecat.app/assets/icons/cat_std_128.png" width="72" height="72" alt="STD" /><br/>
      <strong>STD</strong><br/>
      <code>#4DD9A8</code><br/>
      <sub>Idle, watching, fed.</sub>
    </td>
    <td align="center" width="160">
      <img src="https://vibecat.app/assets/icons/cat_edit_128.png" width="72" height="72" alt="EDIT" /><br/>
      <strong>EDIT</strong><br/>
      <code>#4DA8FF</code><br/>
      <sub>Paws on keys, shipping.</sub>
    </td>
    <td align="center" width="160">
      <img src="https://vibecat.app/assets/icons/cat_alert_128.png" width="72" height="72" alt="ALERT" /><br/>
      <strong>ALERT</strong><br/>
      <code>#FFB347</code><br/>
      <sub>Ear up, needs you.</sub>
    </td>
    <td align="center" width="160">
      <img src="https://vibecat.app/assets/icons/cat_wait_128.png" width="72" height="72" alt="COMPACT" /><br/>
      <strong>COMPACT</strong><br/>
      <code>#7B7BD1</code><br/>
      <sub>Tail flick, compacting context.</sub>
    </td>
  </tr>
</table>

A 28×28 procedural pixel cat. Every session in the bar maps to exactly one state — so you read the whole desk in one glance.

## / 02 — What VibeCat does

- **One-glance status** — `STD` · `EDIT` · `ALERT` · `COMPACT` map to the agent work you actually care about.
- **Sub-50 ms hook decisions** — `PreToolUse`, `PermissionRequest`, and `AskUserQuestion` round-trip through a per-session Windows named pipe.
- **Live session card per agent** — every Claude / Codex / Gemini conversation gets a card with title, terminal, status pill, and elapsed time.
- **Native terminal teleport** — VibeCat walks the process chain and brings the exact tab/pane forward in Windows Terminal, WezTerm, VS Code, Cursor, ConEmu, JetBrains, or conhost.
- **Hook-grade observability** — every payload is logged to `%LOCALAPPDATA%\VibeCat\logs\` with `pid_chain`, `host_kind`, WezTerm pane, console HWND.
- **Bring-your-own CLI** — set `VIBECAT_SESSION_ID`, fire `SessionStart`, your tool gets a card too.
- **Private by default** — source code, raw logs, prompts, terminal output, license keys, and payment data do not belong in this public repo.

## / 03 — Quick start

1. Download VibeCat from [vibecat.app](https://vibecat.app/#download).
2. Install and launch on Windows 11.
3. Connect supported coding tools from the VibeCat integrations panel.
4. Run your agent sessions as usual — each one becomes a card in the bar.
5. For bugs: open **Settings → About → Create and Upload Support Bundle**, then paste the returned `SUP-...` ID into the [Bug Report](.github/ISSUE_TEMPLATE/bug_report.yml) form.

## / 04 — Tested with the agents that actually ship.

<table>
  <tr>
    <td valign="top" width="50%">
      <strong>First-class</strong><br/>
      <sub>Hooks bound directly — Pre/Post tool use, permission prompts, AskUserQuestion, prompt-submit, and stop are all routed through VibeCat with a per-launch nonce.</sub>
      <ul>
        <li>Claude Code CLI</li>
        <li>Codex TUI</li>
        <li>Gemini CLI</li>
      </ul>
    </td>
    <td valign="top" width="50%">
      <strong>Bring-your-own</strong><br/>
      <sub>Anything launched through <code>vibecat-cli</code> gets a session card, status pill, and terminal teleport — without touching the agent's source.</sub>
      <ul>
        <li>Cursor Agent</li>
        <li>Aider CLI</li>
        <li>OpenCode · Qwen-Coder · Kimi-Code</li>
        <li>Generic any</li>
      </ul>
    </td>
  </tr>
</table>

**Terminals & IDEs** — Windows Terminal (tab-precise) · WezTerm (pane-precise) · VS Code · Cursor · ConEmu / Cmder · JetBrains IDEs · conhost direct.

## / 05 — Public support rules

This repository is public. Keep reports high-level and safe to share.

> [!IMPORTANT]
> Do **not** upload or paste:
> - Source code from private repositories
> - Private repository links
> - Raw logs, prompts, agent replies, terminal output, or command lines
> - License keys, API tokens, payment details, email addresses, or other secrets
> - Crash dumps or diagnostic reports you have not reviewed locally

For bugs, use VibeCat's **Create and Upload Support Bundle** action and paste only the returned Support ID into GitHub. Do not attach raw diagnostic files unless support explicitly asks and you have reviewed them locally.

## / 06 — Get help

| Channel | Use it for |
| --- | --- |
| 🐛 [Bug report](https://github.com/peitang/vibecat-support/issues/new?template=bug_report.yml) | Reproducible defects with a Support ID. |
| ✨ [Feature request](https://github.com/peitang/vibecat-support/issues/new?template=feature_request.yml) | Ideas, product feedback, polish. |
| 🔒 [support@vibecat.app](mailto:support@vibecat.app) | Security, license, billing, anything containing secrets. |

---

<p align="center">
  Made for Windows developers who run more than one coding agent at a time.
</p>
<p align="center">
  <sub><a href="https://vibecat.app">vibecat.app</a> · 3-day local trial · one-time USD 21.99 · © 2026 VibeCat</sub>
</p>
