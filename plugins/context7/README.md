# Context7

라이브러리의 최신 문서와 코드 예제를 실시간으로 검색하는 MCP 플러그인입니다.

## 기능

- 라이브러리 이름으로 Context7 호환 ID 검색
- 최신 공식 문서 및 코드 예제 조회
- 토픽별 문서 필터링 (hooks, routing 등)
- 페이지네이션 지원

## 요구사항

- Node.js >= v18.0.0

## 설치

### Claude Code CLI

```bash
claude mcp add context7 -- npx -y @upstash/context7-mcp
```

### 수동 설정

`~/.claude/settings.json` 또는 프로젝트의 `.claude/settings.json`에 추가:

```json
{
  "mcpServers": {
    "context7": {
      "command": "npx",
      "args": ["-y", "@upstash/context7-mcp"]
    }
  }
}
```

### HTTP Transport (대안)

```bash
claude mcp add --transport http context7 https://mcp.context7.com/mcp
```

## 사용 예시

프롬프트에 `use context7`를 추가하거나, 라이브러리 문서가 필요한 질문을 하면 자동으로 활용됩니다:

- "Next.js 14의 App Router 사용법 알려줘 use context7"
- "React hooks 최신 문서 보여줘"
- "Tailwind CSS의 grid 사용법"

## 도구

### resolve-library-id
라이브러리 이름을 Context7 호환 ID로 변환합니다.

```
입력: "react"
출력: "/facebook/react"
```

### get-library-docs
라이브러리의 문서를 가져옵니다.

| 파라미터 | 설명 |
|---------|------|
| `context7CompatibleLibraryID` | 라이브러리 ID (예: "/vercel/next.js") |
| `topic` | 문서 주제 필터 (선택) |
| `mode` | "code" (API/예제) 또는 "info" (개념 설명) |
| `page` | 페이지 번호 (1-10) |

## 참고

- [Context7 GitHub](https://github.com/upstash/context7)
- [npm 패키지](https://www.npmjs.com/package/@upstash/context7-mcp)
- [MCP 공식 문서](https://modelcontextprotocol.io/)
