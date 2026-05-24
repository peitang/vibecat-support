<p align="center">
  <a href="https://vibecat.app">
    <img src="https://vibecat.app/assets/icons/cat_std_128.png" width="128" height="128" alt="VibeCat" />
  </a>
</p>

<h1 align="center">VibeCat</h1>

<p align="center">
  <em>一條 bar，管好所有的 AI 編碼代理。</em>
</p>

<p align="center">
  專為 Windows 11 打造的浮動控制列，整合 Claude Code、Codex、Cursor、Aider 等工具。<br/>
  每個進行中的 session 都一目了然——像素貓狀態、權限審批、終端機跳轉，一站搞定。
</p>

<p align="center">
  <a href="README.md">English</a> ·
  <strong>繁體中文</strong> ·
  <a href="README.zh-CN.md">简体中文</a> ·
  <a href="README.ja.md">日本語</a> ·
  <a href="README.ko.md">한국어</a>
</p>

<p align="center">
  <a href="https://vibecat.app"><img alt="Website" src="https://img.shields.io/badge/%E5%AE%98%E7%B6%B2-vibecat.app-4DA8FF?style=flat-square&labelColor=15171c"></a>
  <a href="https://vibecat.app/#download"><img alt="Download" src="https://img.shields.io/badge/%E4%B8%8B%E8%BC%89-Windows%2011-4DD9A8?style=flat-square&labelColor=15171c"></a>
  <a href="https://vibecat.app/transparency/"><img alt="Transparency" src="https://img.shields.io/badge/%E9%80%8F%E6%98%8E%E5%A0%B1%E5%91%8A-7B7BD1?style=flat-square&labelColor=15171c"></a>
</p>

---

## / 01 — 像素貓的四種狀態

<table align="center">
  <tr>
    <td align="center" width="160">
      <img src="https://vibecat.app/assets/icons/cat_std_128.png" width="72" height="72" alt="STD" /><br/>
      <strong>STD</strong><br/>
      <code>#4DD9A8</code><br/>
      <sub>閒置中，靜靜看著你。</sub>
    </td>
    <td align="center" width="160">
      <img src="https://vibecat.app/assets/icons/cat_edit_128.png" width="72" height="72" alt="EDIT" /><br/>
      <strong>EDIT</strong><br/>
      <code>#4DA8FF</code><br/>
      <sub>貓爪敲鍵盤，正在出貨。</sub>
    </td>
    <td align="center" width="160">
      <img src="https://vibecat.app/assets/icons/cat_alert_128.png" width="72" height="72" alt="ALERT" /><br/>
      <strong>ALERT</strong><br/>
      <code>#FFB347</code><br/>
      <sub>耳朵豎起，需要你回應。</sub>
    </td>
    <td align="center" width="160">
      <img src="https://vibecat.app/assets/icons/cat_wait_128.png" width="72" height="72" alt="COMPACT" /><br/>
      <strong>COMPACT</strong><br/>
      <code>#7B7BD1</code><br/>
      <sub>尾巴擺動，正在壓縮 context。</sub>
    </td>
  </tr>
</table>

28×28 程序生成的像素貓。bar 上每個 session 都對應一個狀態——一眼掃過整張桌面就知道狀況。

## / 02 — VibeCat 能做什麼

- **一眼看狀態** — `STD` · `EDIT` · `ALERT` · `COMPACT` 對應你真正在意的 agent 工作階段。
- **50 毫秒內的 hook 決策** — `PreToolUse`、`PermissionRequest`、`AskUserQuestion` 走每個 session 專屬的 Windows named pipe。
- **每個 agent 一張卡片** — 每個 Claude / Codex / Gemini 對話都會有卡片，顯示標題、終端機、狀態徽章和經過時間。
- **原生終端機跳轉** — VibeCat 解析 process chain，把對應的 tab/pane 帶到前景，支援 Windows Terminal、WezTerm、VS Code、Cursor、ConEmu、JetBrains、conhost。
- **Hook 級的可觀測性** — 所有 payload 都會記到 `%LOCALAPPDATA%\VibeCat\logs\`，包含 `pid_chain`、`host_kind`、WezTerm pane、console HWND。
- **自帶 CLI 也能用** — 設定 `VIBECAT_SESSION_ID`、發出 `SessionStart`，你的工具也會有卡片。
- **預設保密** — 原始碼、原始 log、提示詞、終端機輸出、授權金鑰、付款資料——這些都不該出現在這個公開 repo。

## / 03 — 快速上手

1. 從 [vibecat.app](https://vibecat.app/#download) 下載 VibeCat。
2. 在 Windows 11 安裝並啟動。
3. 在 VibeCat 設定面板連接你要整合的編碼工具。
4. 照平常方式跑 agent session——每個 session 都會變成 bar 上的一張卡片。
5. 回報 bug：打開 **Settings → About → Create and Upload Support Bundle**，把回傳的 `SUP-...` ID 貼到 [Bug Report](.github/ISSUE_TEMPLATE/bug_report.yml) 表單。

## / 04 — 實際支援的 agent

<table>
  <tr>
    <td valign="top" width="50%">
      <strong>原生整合</strong><br/>
      <sub>Hook 直接綁定——Pre/Post tool use、權限提示、AskUserQuestion、prompt-submit、stop 全部走 VibeCat，附帶每次啟動的 nonce。</sub>
      <ul>
        <li>Claude Code CLI</li>
        <li>Codex TUI</li>
        <li>Gemini CLI</li>
      </ul>
    </td>
    <td valign="top" width="50%">
      <strong>自帶接入</strong><br/>
      <sub>任何透過 <code>vibecat-cli</code> 啟動的工具，都會自動取得 session 卡片、狀態徽章與終端機跳轉——完全不用改 agent 的原始碼。</sub>
      <ul>
        <li>Cursor Agent</li>
        <li>Aider CLI</li>
        <li>OpenCode · Qwen-Coder · Kimi-Code</li>
        <li>任何 generic CLI</li>
      </ul>
    </td>
  </tr>
</table>

**終端機與 IDE** — Windows Terminal（tab 精度）· WezTerm（pane 精度）· VS Code · Cursor · ConEmu / Cmder · JetBrains IDEs · conhost 直連。

## / 05 — 公開支援規範

本 repo 為公開倉庫，請把回報內容保持在高層次、可分享的範圍內。

> [!IMPORTANT]
> **請勿**上傳或貼上：
> - 私人 repo 的原始碼
> - 私人 repo 連結
> - 原始 log、提示詞、agent 回應、終端機輸出或命令列
> - 授權金鑰、API token、付款資料、email 或任何機密
> - 沒在本機檢視過的 crash dump 或診斷檔

回報 bug 時，請使用 VibeCat 的 **Create and Upload Support Bundle** 動作，只貼回傳的 Support ID 到 GitHub。除非客服明確要求，否則不要附上未經本機檢視的原始診斷檔。

## / 06 — 取得協助

| 管道 | 用途 |
| --- | --- |
| 🐛 [Bug 回報](https://github.com/peitang/vibecat-support/issues/new?template=bug_report.yml) | 有 Support ID 的可重現缺陷。 |
| ✨ [功能建議](https://github.com/peitang/vibecat-support/issues/new?template=feature_request.yml) | 點子、產品回饋、打磨建議。 |
| 🔒 [support@vibecat.app](mailto:support@vibecat.app) | 安全性、授權、帳務，或任何包含機密的內容。 |

---

<p align="center">
  為「同時跑多個編碼 agent」的 Windows 開發者打造。
</p>
<p align="center">
  <sub><a href="https://vibecat.app">vibecat.app</a> · © 2026 VibeCat</sub>
</p>
