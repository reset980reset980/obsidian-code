# Claude Code for Windows

옵시디언(Obsidian)에서 Claude Code를 윈도우 기준으로 사용하기 위한 플러그인입니다.

이 저장소는 원작 [`reallygood83/obsidian-code`](https://github.com/reallygood83/obsidian-code)를 기반으로 내용을 가져와 윈도우 환경에 맞게 수정한 포크입니다. 그래서 이 README는 macOS/Linux가 아니라 Windows 사용만 기준으로 설명합니다.

## 소개

- 옵시디언 사이드바에서 Claude와 대화
- 볼트 안 파일 읽기와 수정
- Claude Code 도구와 에이전트 워크플로우 실행
- 노트와 폴더를 컨텍스트로 첨부
- 노트 안에서 inline edit 사용
- MCP 서버, 슬래시 커맨드, 안전 설정 구성

## 필요 사항

Windows에 Claude Code CLI가 설치되어 있어야 합니다.

```powershell
npm install -g @anthropic-ai/claude-code
```

설치 후 터미널에서 한 번 인증합니다.

```powershell
claude
```

구독형 토큰이 만료되면 다시 인증합니다.

```powershell
claude auth login
```

## 설치 방법

### BRAT 사용

1. Obsidian 커뮤니티 플러그인에서 `BRAT` 설치
2. `BRAT: Add a beta plugin for testing` 실행
3. 아래 주소 입력

```text
https://github.com/reset980reset980/obsidian-code
```

4. 최신 릴리스 선택
5. 커뮤니티 플러그인에서 `Claude Code for Windows` 활성화

### 수동 설치

볼트의 플러그인 폴더로 이동해서 직접 설치할 수 있습니다.

```powershell
cd "C:\path\to\your\vault\.obsidian\plugins"
git clone https://github.com/reset980reset980/obsidian-code.git claude-code-win
cd claude-code-win
npm install
npm run build
```

그 다음 Obsidian에서 `Claude Code for Windows`를 켜면 됩니다.

## 윈도우 기준 참고

- 플러그인은 일반적인 Windows 설치 위치에서 Claude CLI를 자동 감지합니다.
- 자동 감지가 실패하면 플러그인 설정의 `Claude Code CLI path`에 직접 경로를 넣으면 됩니다.
- `C:\Users\<you>\.local\bin\claude.exe` 같은 경로는 정상입니다.
- npm 방식 설치라면 `claude.cmd`가 아니라 실제 CLI 경로를 써야 합니다.

## 문제 해결

### `Claude Code CLI not found`

터미널에서 아래 명령으로 경로를 찾습니다.

```powershell
where.exe claude
```

출력된 경로를 `Settings -> Claude Code for Windows -> Claude Code CLI path`에 넣으면 됩니다.

### `401` 또는 `OAuth token has expired`

Claude CLI 로그인 토큰이 만료된 상태입니다. 다시 인증하면 됩니다.

```powershell
claude auth login
```

최근 버전에서는 플러그인 설정 안에서도 인증 실행 버튼을 사용할 수 있습니다.

## Credits

- 원작 프로젝트와 기본 콘텐츠: [`reallygood83/obsidian-code`](https://github.com/reallygood83/obsidian-code)
- 윈도우용 포크와 수정: [`reset980reset980/obsidian-code`](https://github.com/reset980reset980/obsidian-code)

이 윈도우 버전의 기반이 된 원작 플러그인을 공개해 준 원작자에게 감사드립니다.

## English

This repository is a Windows-adapted fork of the original `reallygood83/obsidian-code` project. The original plugin content and workflow were used as the base and changed for Windows usage.

## License

[MIT](LICENSE)
