<p align="center">
  <a href="https://vibecat.app">
    <img src="https://vibecat.app/assets/icons/cat_std_128.png" width="128" height="128" alt="VibeCat" />
  </a>
</p>

<h1 align="center">VibeCat</h1>

<p align="center">
  <em>一条 bar，管好所有 AI 编码代理。</em>
</p>

<p align="center">
  专为 Windows 11 打造的悬浮控制条，集成 Claude Code、Codex、Cursor、Aider 等工具。<br/>
  每个进行中的 session 一目了然——像素猫状态、权限审批、终端跳转，一站搞定。
</p>

<p align="center">
  <a href="README.md">English</a> ·
  <a href="README.zh-TW.md">繁體中文</a> ·
  <strong>简体中文</strong> ·
  <a href="README.ja.md">日本語</a> ·
  <a href="README.ko.md">한국어</a>
</p>

<p align="center">
  <a href="https://vibecat.app"><img alt="Website" src="https://img.shields.io/badge/%E5%AE%98%E7%BD%91-vibecat.app-4DA8FF?style=flat-square&labelColor=15171c"></a>
  <a href="https://vibecat.app/#download"><img alt="Download" src="https://img.shields.io/badge/%E4%B8%8B%E8%BD%BD-Windows%2011-4DD9A8?style=flat-square&labelColor=15171c"></a>
  <a href="https://vibecat.app/#pricing"><img alt="License" src="https://img.shields.io/badge/%E4%B8%80%E6%AC%A1%E6%80%A7%E8%B4%AD%E4%B9%B0-USD%2021.99-FFB347?style=flat-square&labelColor=15171c"></a>
  <a href="https://vibecat.app/transparency/"><img alt="Transparency" src="https://img.shields.io/badge/%E9%80%8F%E6%98%8E%E6%8A%A5%E5%91%8A-7B7BD1?style=flat-square&labelColor=15171c"></a>
</p>

---

## / 01 — 像素猫的四种状态

<table align="center">
  <tr>
    <td align="center" width="160">
      <img src="https://vibecat.app/assets/icons/cat_std_128.png" width="72" height="72" alt="STD" /><br/>
      <strong>STD</strong><br/>
      <code>#4DD9A8</code><br/>
      <sub>空闲中，静静看着你。</sub>
    </td>
    <td align="center" width="160">
      <img src="https://vibecat.app/assets/icons/cat_edit_128.png" width="72" height="72" alt="EDIT" /><br/>
      <strong>EDIT</strong><br/>
      <code>#4DA8FF</code><br/>
      <sub>爪子敲键盘，正在出活。</sub>
    </td>
    <td align="center" width="160">
      <img src="https://vibecat.app/assets/icons/cat_alert_128.png" width="72" height="72" alt="ALERT" /><br/>
      <strong>ALERT</strong><br/>
      <code>#FFB347</code><br/>
      <sub>耳朵立起，等你回应。</sub>
    </td>
    <td align="center" width="160">
      <img src="https://vibecat.app/assets/icons/cat_wait_128.png" width="72" height="72" alt="COMPACT" /><br/>
      <strong>COMPACT</strong><br/>
      <code>#7B7BD1</code><br/>
      <sub>尾巴一甩，正在压缩 context。</sub>
    </td>
  </tr>
</table>

28×28 过程生成的像素猫。bar 上每个 session 都对应一个状态——一眼扫过整张桌面就知道状况。

## / 02 — VibeCat 能做什么

- **一眼看状态** — `STD` · `EDIT` · `ALERT` · `COMPACT` 对应你真正关心的 agent 工作阶段。
- **50 毫秒内的 hook 决策** — `PreToolUse`、`PermissionRequest`、`AskUserQuestion` 走每个 session 专属的 Windows named pipe。
- **每个 agent 一张卡片** — 每个 Claude / Codex / Gemini 会话都有卡片，显示标题、终端、状态徽章和耗时。
- **原生终端跳转** — VibeCat 解析进程链，把对应的 tab/pane 带到前台，支持 Windows Terminal、WezTerm、VS Code、Cursor、ConEmu、JetBrains、conhost。
- **Hook 级可观测性** — 所有 payload 都会写入 `%LOCALAPPDATA%\VibeCat\logs\`,包含 `pid_chain`、`host_kind`、WezTerm pane、console HWND。
- **自带 CLI 也能用** — 设置 `VIBECAT_SESSION_ID`、触发 `SessionStart`,你的工具也会有卡片。
- **默认保密** — 源代码、原始日志、提示词、终端输出、授权密钥、支付数据——这些都不该出现在这个公开 repo。

## / 03 — 快速上手

1. 从 [vibecat.app](https://vibecat.app/#download) 下载 VibeCat。
2. 在 Windows 11 安装并启动。
3. 在 VibeCat 设置面板里连接要集成的编码工具。
4. 按平时的方式跑 agent session——每个 session 都会变成 bar 上的一张卡片。
5. 报告 bug：打开 **Settings → About → Create and Upload Support Bundle**,把返回的 `SUP-...` ID 贴到 [Bug Report](.github/ISSUE_TEMPLATE/bug_report.yml) 表单。

## / 04 — 实测支持的 agent

<table>
  <tr>
    <td valign="top" width="50%">
      <strong>原生集成</strong><br/>
      <sub>Hook 直接绑定——Pre/Post tool use、权限提示、AskUserQuestion、prompt-submit、stop 全部走 VibeCat,带每次启动的 nonce。</sub>
      <ul>
        <li>Claude Code CLI</li>
        <li>Codex TUI</li>
        <li>Gemini CLI</li>
      </ul>
    </td>
    <td valign="top" width="50%">
      <strong>自带接入</strong><br/>
      <sub>任何通过 <code>vibecat-cli</code> 启动的工具,都会自动获得 session 卡片、状态徽章和终端跳转——完全不需要改 agent 源码。</sub>
      <ul>
        <li>Cursor Agent</li>
        <li>Aider CLI</li>
        <li>OpenCode · Qwen-Coder · Kimi-Code</li>
        <li>任何 generic CLI</li>
      </ul>
    </td>
  </tr>
</table>

**终端与 IDE** — Windows Terminal（tab 精度）· WezTerm（pane 精度）· VS Code · Cursor · ConEmu / Cmder · JetBrains IDEs · conhost 直连。

## / 05 — 公开支持规范

本 repo 为公开仓库，请把报告内容保持在高层次、可公开分享的范围。

> [!IMPORTANT]
> **请勿**上传或粘贴:
> - 私有 repo 的源代码
> - 私有 repo 链接
> - 原始日志、提示词、agent 回复、终端输出或命令行
> - 授权密钥、API token、支付数据、邮箱地址或任何机密
> - 没在本地查看过的 crash dump 或诊断文件

报告 bug 时,使用 VibeCat 的 **Create and Upload Support Bundle** 操作,只把返回的 Support ID 贴到 GitHub。除非客服明确要求,否则不要附上未经本地查看的原始诊断文件。

## / 06 — 获取帮助

| 渠道 | 用途 |
| --- | --- |
| 🐛 [Bug 报告](https://github.com/peitang/vibecat-support/issues/new?template=bug_report.yml) | 带 Support ID 的可复现缺陷。 |
| ✨ [功能建议](https://github.com/peitang/vibecat-support/issues/new?template=feature_request.yml) | 想法、产品反馈、打磨建议。 |
| 🔒 [support@vibecat.app](mailto:support@vibecat.app) | 安全、授权、账单,或任何包含机密的内容。 |

---

<p align="center">
  为「同时跑多个编码 agent」的 Windows 开发者打造。
</p>
<p align="center">
  <sub><a href="https://vibecat.app">vibecat.app</a> · 3 天本地试用 · 一次性购买 USD 21.99 · © 2026 VibeCat</sub>
</p>
