# Serena

시맨틱 코드 분석 및 편집 기능을 제공하는 강력한 코딩 에이전트 MCP 플러그인입니다.

## 기능

- 시맨틱 코드 검색 및 심볼 탐색
- 심볼 수준의 코드 편집 (클래스, 함수, 메서드)
- 다중 언어 지원 (Python, TypeScript, Java, Go, Rust 등)
- LSP (Language Server Protocol) 통합
- 프로젝트 메모리 기능

## 요구사항

- Python 3.10+
- uv (Python 패키지 매니저)

### uv 설치

**macOS/Linux:**
```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
# 또는
brew install uv
```

**Windows:**
```powershell
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

## 설치

### Claude Code CLI

```bash
claude mcp add-json "serena" '{"command":"uvx","args":["--from","git+https://github.com/oraios/serena","serena","start-mcp-server"]}'
```

### 수동 설정

`~/.claude/settings.json` 또는 프로젝트의 `.claude/settings.json`에 추가:

```json
{
  "mcpServers": {
    "serena": {
      "command": "uvx",
      "args": ["--from", "git+https://github.com/oraios/serena", "serena", "start-mcp-server"]
    }
  }
}
```

## 주요 도구

### 심볼 탐색
- `get_symbols_overview` - 파일의 심볼 개요 조회
- `find_symbol` - 이름으로 심볼 검색
- `find_referencing_symbols` - 참조하는 심볼 찾기

### 코드 편집
- `replace_symbol_body` - 심볼 본문 교체
- `insert_after_symbol` - 심볼 뒤에 코드 삽입
- `insert_before_symbol` - 심볼 앞에 코드 삽입
- `rename_symbol` - 심볼 이름 변경 (전체 코드베이스)

### 파일 작업
- `read_file` - 파일 읽기
- `create_text_file` - 파일 생성
- `replace_content` - 정규식 기반 내용 교체
- `search_for_pattern` - 패턴 검색

### 프로젝트 관리
- `activate_project` - 프로젝트 활성화
- `write_memory` / `read_memory` - 프로젝트 메모리
- `execute_shell_command` - 셸 명령 실행

## 지원 언어

Python, TypeScript, JavaScript, Java, Kotlin, Go, Rust, Ruby, C++, C#, PHP, Swift, Dart, Scala 등 30개 이상

## 참고

- [Serena GitHub](https://github.com/oraios/serena)
- [설치 가이드](https://sangdon-park.github.io/articles/serena-mcp-guide-en.html)
- [MCP 공식 문서](https://modelcontextprotocol.io/)
