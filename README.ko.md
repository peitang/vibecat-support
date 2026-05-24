<p align="center">
  <a href="https://vibecat.app">
    <img src="https://vibecat.app/assets/icons/cat_std_128.png" width="128" height="128" alt="VibeCat" />
  </a>
</p>

<h1 align="center">VibeCat</h1>

<p align="center">
  <em>모든 코딩 에이전트를, 하나의 바로.</em>
</p>

<p align="center">
  Claude Code, Codex, Cursor, Aider 등을 위한 Windows 11 전용 플로팅 컨트롤 바.<br/>
  진행 중인 모든 세션을 한곳에 — 픽셀 고양이 상태, 훅 승인, 터미널 텔레포트.
</p>

<p align="center">
  <a href="README.md">English</a> ·
  <a href="README.zh-TW.md">繁體中文</a> ·
  <a href="README.zh-CN.md">简体中文</a> ·
  <a href="README.ja.md">日本語</a> ·
  <strong>한국어</strong>
</p>

<p align="center">
  <a href="https://vibecat.app"><img alt="Website" src="https://img.shields.io/badge/%EA%B3%B5%EC%8B%9D-vibecat.app-4DA8FF?style=flat-square&labelColor=15171c"></a>
  <a href="https://vibecat.app/#download"><img alt="Download" src="https://img.shields.io/badge/%EB%8B%A4%EC%9A%B4%EB%A1%9C%EB%93%9C-Windows%2011-4DD9A8?style=flat-square&labelColor=15171c"></a>
  <a href="https://vibecat.app/#pricing"><img alt="License" src="https://img.shields.io/badge/%EC%9D%BC%ED%9A%8C%EC%84%B1-USD%2021.99-FFB347?style=flat-square&labelColor=15171c"></a>
  <a href="https://vibecat.app/transparency/"><img alt="Transparency" src="https://img.shields.io/badge/%ED%88%AC%EB%AA%85%EC%84%B1%20%EB%B3%B4%EA%B3%A0%EC%84%9C-7B7BD1?style=flat-square&labelColor=15171c"></a>
</p>

---

## / 01 — 픽셀 고양이의 네 가지 상태

<table align="center">
  <tr>
    <td align="center" width="160">
      <img src="https://vibecat.app/assets/icons/cat_std_128.png" width="72" height="72" alt="STD" /><br/>
      <strong>STD</strong><br/>
      <code>#4DD9A8</code><br/>
      <sub>대기 중, 조용히 지켜보는 중.</sub>
    </td>
    <td align="center" width="160">
      <img src="https://vibecat.app/assets/icons/cat_edit_128.png" width="72" height="72" alt="EDIT" /><br/>
      <strong>EDIT</strong><br/>
      <code>#4DA8FF</code><br/>
      <sub>발로 키보드 두드리며 작업 중.</sub>
    </td>
    <td align="center" width="160">
      <img src="https://vibecat.app/assets/icons/cat_alert_128.png" width="72" height="72" alt="ALERT" /><br/>
      <strong>ALERT</strong><br/>
      <code>#FFB347</code><br/>
      <sub>귀를 쫑긋, 응답이 필요해요.</sub>
    </td>
    <td align="center" width="160">
      <img src="https://vibecat.app/assets/icons/cat_wait_128.png" width="72" height="72" alt="COMPACT" /><br/>
      <strong>COMPACT</strong><br/>
      <code>#7B7BD1</code><br/>
      <sub>꼬리를 흔들며 컨텍스트 압축 중.</sub>
    </td>
  </tr>
</table>

28×28 절차적 픽셀 고양이. 바의 각 세션은 정확히 하나의 상태에 매핑되어, 책상 전체를 한눈에 파악할 수 있습니다.

## / 02 — VibeCat이 하는 일

- **한눈에 상태 확인** — `STD` · `EDIT` · `ALERT` · `COMPACT` 가 실제로 신경 써야 할 에이전트 작업과 대응.
- **50ms 이내의 hook 결정** — `PreToolUse`, `PermissionRequest`, `AskUserQuestion` 이 세션별 Windows named pipe 로 왕복.
- **에이전트별 라이브 세션 카드** — Claude / Codex / Gemini 각 대화마다 제목, 터미널, 상태 필, 경과 시간이 담긴 카드.
- **네이티브 터미널 텔레포트** — 프로세스 체인을 따라가 정확한 tab/pane 을 전면으로. Windows Terminal, WezTerm, VS Code, Cursor, ConEmu, JetBrains, conhost 지원.
- **Hook 급 옵저버빌리티** — 모든 페이로드가 `%LOCALAPPDATA%\VibeCat\logs\` 에 기록 (`pid_chain`, `host_kind`, WezTerm pane, console HWND 포함).
- **자체 CLI 도 가능** — `VIBECAT_SESSION_ID` 설정 후 `SessionStart` 발사하면, 당신의 도구도 카드를 받습니다.
- **기본은 비공개** — 소스 코드, 원본 로그, 프롬프트, 터미널 출력, 라이선스 키, 결제 데이터는 이 공개 repo 에 올라가면 안 됩니다.

## / 03 — 빠른 시작

1. [vibecat.app](https://vibecat.app/#download) 에서 VibeCat 다운로드.
2. Windows 11 에 설치하고 실행.
3. VibeCat 통합 패널에서 사용할 코딩 도구를 연결.
4. 평소처럼 에이전트 세션 실행 — 각 세션이 바의 카드가 됩니다.
5. 버그 신고: **Settings → About → Create and Upload Support Bundle** 을 열어, 반환된 `SUP-...` ID 를 [Bug Report](.github/ISSUE_TEMPLATE/bug_report.yml) 폼에 붙여넣기.

## / 04 — 실제로 동작하는 에이전트

<table>
  <tr>
    <td valign="top" width="50%">
      <strong>퍼스트클래스</strong><br/>
      <sub>Hook 직접 연결 — Pre/Post tool use, 권한 프롬프트, AskUserQuestion, prompt-submit, stop 이 실행마다 nonce 와 함께 VibeCat 을 거칩니다.</sub>
      <ul>
        <li>Claude Code CLI</li>
        <li>Codex TUI</li>
        <li>Gemini CLI</li>
      </ul>
    </td>
    <td valign="top" width="50%">
      <strong>가져오기 (BYO)</strong><br/>
      <sub><code>vibecat-cli</code> 를 통해 실행되는 모든 도구는 에이전트 소스를 건드리지 않고도 세션 카드, 상태 필, 터미널 텔레포트를 얻습니다.</sub>
      <ul>
        <li>Cursor Agent</li>
        <li>Aider CLI</li>
        <li>OpenCode · Qwen-Coder · Kimi-Code</li>
        <li>기타 generic CLI</li>
      </ul>
    </td>
  </tr>
</table>

**터미널 & IDE** — Windows Terminal (tab 단위) · WezTerm (pane 단위) · VS Code · Cursor · ConEmu / Cmder · JetBrains IDE · conhost 직결.

## / 05 — 공개 서포트 규칙

이 저장소는 공개입니다. 신고 내용은 공유해도 안전한 수준으로 유지해 주세요.

> [!IMPORTANT]
> 다음은 **업로드·붙여넣기 금지**:
> - 비공개 repo 의 소스 코드
> - 비공개 repo 링크
> - 원본 로그, 프롬프트, 에이전트 응답, 터미널 출력 또는 명령어
> - 라이선스 키, API 토큰, 결제 정보, 이메일 주소 또는 기타 기밀
> - 로컬에서 확인하지 않은 크래시 덤프 또는 진단 리포트

버그 신고 시, VibeCat 의 **Create and Upload Support Bundle** 작업을 사용하고 반환된 Support ID 만 GitHub 에 붙여넣으세요. 서포트 측에서 명시적으로 요청하지 않고 로컬에서 확인하지 않은 진단 파일은 첨부하지 마세요.

## / 06 — 도움 받기

| 채널 | 용도 |
| --- | --- |
| 🐛 [버그 신고](https://github.com/peitang/vibecat-support/issues/new?template=bug_report.yml) | Support ID 가 있는 재현 가능한 결함. |
| ✨ [기능 요청](https://github.com/peitang/vibecat-support/issues/new?template=feature_request.yml) | 아이디어, 제품 피드백, 다듬기 제안. |
| 🔒 [support@vibecat.app](mailto:support@vibecat.app) | 보안, 라이선스, 결제, 또는 기밀이 포함된 모든 내용. |

---

<p align="center">
  여러 개의 코딩 에이전트를 동시에 돌리는 Windows 개발자를 위해.
</p>
<p align="center">
  <sub><a href="https://vibecat.app">vibecat.app</a> · 3 일 로컬 평가판 · 일회성 USD 21.99 · © 2026 VibeCat</sub>
</p>
