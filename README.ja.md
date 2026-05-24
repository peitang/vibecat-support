<p align="center">
  <a href="https://vibecat.app">
    <img src="https://vibecat.app/assets/icons/cat_std_128.png" width="128" height="128" alt="VibeCat" />
  </a>
</p>

<h1 align="center">VibeCat</h1>

<p align="center">
  <em>すべてのコーディングエージェントを、一本のバーで。</em>
</p>

<p align="center">
  Claude Code、Codex、Cursor、Aider などのための、Windows 11 専用フローティング・コントロールバー。<br/>
  すべてのライブセッションを一箇所に集約——ピクセル猫ステータス、フック承認、ターミナルテレポート。
</p>

<p align="center">
  <a href="README.md">English</a> ·
  <a href="README.zh-TW.md">繁體中文</a> ·
  <a href="README.zh-CN.md">简体中文</a> ·
  <strong>日本語</strong> ·
  <a href="README.ko.md">한국어</a>
</p>

<p align="center">
  <a href="https://vibecat.app"><img alt="Website" src="https://img.shields.io/badge/%E5%85%AC%E5%BC%8F-vibecat.app-4DA8FF?style=flat-square&labelColor=15171c"></a>
  <a href="https://vibecat.app/#download"><img alt="Download" src="https://img.shields.io/badge/%E3%83%80%E3%82%A6%E3%83%B3%E3%83%AD%E3%83%BC%E3%83%89-Windows%2011-4DD9A8?style=flat-square&labelColor=15171c"></a>
  <a href="https://vibecat.app/transparency/"><img alt="Transparency" src="https://img.shields.io/badge/%E9%80%8F%E6%98%8E%E6%80%A7%E5%A0%B1%E5%91%8A-7B7BD1?style=flat-square&labelColor=15171c"></a>
</p>

---

## / 01 — ピクセル猫の 4 つのステート

<table align="center">
  <tr>
    <td align="center" width="160">
      <img src="https://vibecat.app/assets/icons/cat_std_128.png" width="72" height="72" alt="STD" /><br/>
      <strong>STD</strong><br/>
      <code>#4DD9A8</code><br/>
      <sub>アイドル、見守り中。</sub>
    </td>
    <td align="center" width="160">
      <img src="https://vibecat.app/assets/icons/cat_edit_128.png" width="72" height="72" alt="EDIT" /><br/>
      <strong>EDIT</strong><br/>
      <code>#4DA8FF</code><br/>
      <sub>肉球でキー打鍵中。</sub>
    </td>
    <td align="center" width="160">
      <img src="https://vibecat.app/assets/icons/cat_alert_128.png" width="72" height="72" alt="ALERT" /><br/>
      <strong>ALERT</strong><br/>
      <code>#FFB347</code><br/>
      <sub>耳を立てて、応答待ち。</sub>
    </td>
    <td align="center" width="160">
      <img src="https://vibecat.app/assets/icons/cat_wait_128.png" width="72" height="72" alt="COMPACT" /><br/>
      <strong>COMPACT</strong><br/>
      <code>#7B7BD1</code><br/>
      <sub>尻尾ひと振り、context 圧縮中。</sub>
    </td>
  </tr>
</table>

28×28 のプロシージャル生成ピクセル猫。バー上の各セッションは 1 つのステートにマップされ、デスク全体の状況を一目で把握できます。

## / 02 — VibeCat にできること

- **ひと目でステータス把握** — `STD` · `EDIT` · `ALERT` · `COMPACT` が、本当に気にすべきエージェント作業に対応。
- **50ms 以下の hook 判定** — `PreToolUse`、`PermissionRequest`、`AskUserQuestion` をセッション専用の Windows named pipe で往復。
- **エージェントごとのライブセッションカード** — Claude / Codex / Gemini の各会話に、タイトル・ターミナル・ステータスピル・経過時間つきのカード。
- **ネイティブなターミナルテレポート** — プロセスチェーンを辿り、対象の tab/pane を前面に持ち出します。Windows Terminal、WezTerm、VS Code、Cursor、ConEmu、JetBrains、conhost に対応。
- **Hook グレードの可観測性** — すべてのペイロードが `%LOCALAPPDATA%\VibeCat\logs\` に記録されます（`pid_chain`、`host_kind`、WezTerm pane、console HWND つき）。
- **自前 CLI も OK** — `VIBECAT_SESSION_ID` を設定し `SessionStart` を発火すれば、あなたのツールもカードを取得。
- **デフォルトでプライベート** — ソースコード、生ログ、プロンプト、ターミナル出力、ライセンスキー、決済データはこの公開 repo には載せません。

## / 03 — クイックスタート

1. [vibecat.app](https://vibecat.app/#download) から VibeCat をダウンロード。
2. Windows 11 にインストールして起動。
3. VibeCat の設定パネルから対応コーディングツールを接続。
4. いつも通りエージェントセッションを実行——各セッションがバー上のカードになります。
5. バグ報告：**Settings → About → Create and Upload Support Bundle** を開き、返却された `SUP-...` ID を [Bug Report](.github/ISSUE_TEMPLATE/bug_report.yml) フォームに貼り付け。

## / 04 — 実際に動くエージェント

<table>
  <tr>
    <td valign="top" width="50%">
      <strong>ファーストクラス</strong><br/>
      <sub>Hook を直結——Pre/Post tool use、権限プロンプト、AskUserQuestion、prompt-submit、stop すべてが、起動ごとの nonce つきで VibeCat 経由。</sub>
      <ul>
        <li>Claude Code CLI</li>
        <li>Codex TUI</li>
        <li>Gemini CLI</li>
      </ul>
    </td>
    <td valign="top" width="50%">
      <strong>持ち込み対応</strong><br/>
      <sub><code>vibecat-cli</code> 経由で起動すれば、エージェントのソースを触らずに、セッションカード・ステータスピル・ターミナルテレポートを取得。</sub>
      <ul>
        <li>Cursor Agent</li>
        <li>Aider CLI</li>
        <li>OpenCode · Qwen-Coder · Kimi-Code</li>
        <li>その他 generic CLI</li>
      </ul>
    </td>
  </tr>
</table>

**ターミナルと IDE** — Windows Terminal（tab 単位）· WezTerm（pane 単位）· VS Code · Cursor · ConEmu / Cmder · JetBrains IDE · conhost 直結。

## / 05 — 公開サポートのルール

このリポジトリは公開です。共有しても安全な、ハイレベルな情報のみ投稿してください。

> [!IMPORTANT]
> 以下は**アップロード・貼り付け禁止**:
> - プライベート repo のソースコード
> - プライベート repo のリンク
> - 生ログ、プロンプト、エージェントの返答、ターミナル出力、コマンドライン
> - ライセンスキー、API トークン、決済情報、メールアドレス、その他の機密
> - ローカルで確認していないクラッシュダンプや診断レポート

バグの場合は、VibeCat の **Create and Upload Support Bundle** を実行し、返却された Support ID のみを GitHub に貼り付け。サポートから明示的に依頼があり、ローカルで内容確認した場合を除き、生の診断ファイルは添付しないでください。

## / 06 — サポート窓口

| チャンネル | 用途 |
| --- | --- |
| 🐛 [バグ報告](https://github.com/peitang/vibecat-support/issues/new?template=bug_report.yml) | Support ID 付きの再現可能な不具合。 |
| ✨ [機能リクエスト](https://github.com/peitang/vibecat-support/issues/new?template=feature_request.yml) | アイデア、製品フィードバック、磨き込み案。 |
| 🔒 [support@vibecat.app](mailto:support@vibecat.app) | セキュリティ、ライセンス、請求、機密を含む内容。 |

---

<p align="center">
  複数のコーディングエージェントを同時に動かす Windows 開発者のために。
</p>
<p align="center">
  <sub><a href="https://vibecat.app">vibecat.app</a> · © 2026 VibeCat</sub>
</p>
