# Sequential Thinking

복잡한 문제를 단계별로 분석하고 해결하는 MCP 플러그인입니다.

## 기능

- 문제를 여러 단계로 분해하여 체계적으로 사고
- 이전 단계를 수정하거나 분기 가능
- 가설 생성 및 검증 지원
- 불확실성 표현 및 대안 탐색

## 설치

### 1. 패키지 설치

```bash
npx -y @anthropic-ai/create-mcp
# 또는
npm install -g @modelcontextprotocol/server-sequential-thinking
```

### 2. Claude Code 설정

`~/.claude/settings.json` 또는 프로젝트의 `.claude/settings.json`에 추가:

```json
{
  "mcpServers": {
    "sequential-thinking": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-sequential-thinking"]
    }
  }
}
```

## 사용 예시

Claude에게 복잡한 문제를 요청하면 자동으로 sequential thinking 도구를 활용합니다:

- "이 버그의 원인을 단계별로 분석해줘"
- "이 아키텍처 결정의 장단점을 체계적으로 검토해줘"
- "이 알고리즘을 최적화하는 방법을 단계별로 생각해줘"

## 파라미터

| 파라미터 | 설명 |
|---------|------|
| `thought` | 현재 사고 단계 |
| `thoughtNumber` | 현재 단계 번호 |
| `totalThoughts` | 예상 총 단계 수 (조정 가능) |
| `nextThoughtNeeded` | 추가 사고 필요 여부 |
| `isRevision` | 이전 사고 수정 여부 |
| `branchFromThought` | 분기 시작점 |

## 참고

- [MCP 공식 문서](https://modelcontextprotocol.io/)
- [Sequential Thinking GitHub](https://github.com/modelcontextprotocol/servers)
