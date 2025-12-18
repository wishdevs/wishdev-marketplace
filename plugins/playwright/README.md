# Playwright

브라우저 자동화 기능을 제공하는 공식 Microsoft MCP 플러그인입니다.

## 기능

- 웹 페이지 탐색 및 상호작용
- 접근성 스냅샷 기반 (스크린샷 불필요)
- 폼 입력, 클릭, 드래그 앤 드롭
- 파일 업로드
- JavaScript 실행
- 네트워크 요청 모니터링
- 다중 탭 관리

## 요구사항

- Node.js >= 18.0.0

## 설치

### Claude Code CLI

```bash
claude mcp add playwright -- npx @playwright/mcp@latest
```

### 수동 설정

`~/.claude/settings.json` 또는 프로젝트의 `.claude/settings.json`에 추가:

```json
{
  "mcpServers": {
    "playwright": {
      "command": "npx",
      "args": ["@playwright/mcp@latest"]
    }
  }
}
```

### 헤드리스 모드 (브라우저 창 숨김)

```json
{
  "mcpServers": {
    "playwright": {
      "command": "npx",
      "args": ["@playwright/mcp@latest", "--headless"]
    }
  }
}
```

## 브라우저 모드

### Persistent (기본)
- 로그인 정보 유지
- 일반 브라우저처럼 작동

### Isolated
- 매 세션마다 깨끗한 상태
- 테스트에 적합

```json
{
  "args": ["@playwright/mcp@latest", "--isolated"]
}
```

## 주요 도구

### 탐색
- `browser_navigate` - URL로 이동
- `browser_navigate_back` - 뒤로 가기
- `browser_tabs` - 탭 관리 (목록/생성/닫기/선택)

### 상호작용
- `browser_click` - 요소 클릭
- `browser_type` - 텍스트 입력
- `browser_fill_form` - 폼 필드 채우기
- `browser_select_option` - 드롭다운 선택
- `browser_hover` - 마우스 호버
- `browser_drag` - 드래그 앤 드롭
- `browser_press_key` - 키보드 입력
- `browser_file_upload` - 파일 업로드

### 정보 수집
- `browser_snapshot` - 접근성 스냅샷 (권장)
- `browser_take_screenshot` - 스크린샷 캡처
- `browser_console_messages` - 콘솔 메시지 조회
- `browser_network_requests` - 네트워크 요청 조회

### 고급
- `browser_evaluate` - JavaScript 실행
- `browser_handle_dialog` - 다이얼로그 처리
- `browser_wait_for` - 대기 (텍스트/시간)
- `browser_run_code` - Playwright 코드 실행

## 사용 예시

Claude에게 웹 작업을 요청하면 자동으로 활용됩니다:

- "구글에서 'MCP server'를 검색해줘"
- "이 웹페이지의 로그인 폼을 작성해줘"
- "현재 페이지의 스크린샷을 찍어줘"

## 참고

- [Playwright MCP GitHub](https://github.com/microsoft/playwright-mcp)
- [npm 패키지](https://www.npmjs.com/package/@playwright/mcp)
- [MCP 공식 문서](https://modelcontextprotocol.io/)
