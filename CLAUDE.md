# deep-research-skills

연구 워크플로우 스킬 라이브러리 (Claude Code / OpenCode / Codex 지원).

## 명령어

```bash
# 스킬 설치 (Claude Code)
cp -r skills/research-en/* ~/.claude/skills/

# 스킬 설치 (Codex)
cp -r agents-codex/* ~/.codex/agents/

# 설치 검증
bash tests/test_install_codex.sh
```

## 구조

```
skills/
  research-en/          # Claude Code 영문 스킬 (research, research-deep 등)
  research-zh/          # Claude Code 중문 스킬
  research-codex-en/    # Codex 영문 스킬
  research-codex-zh/    # Codex 중문 스킬
agents/
  web-search-agent.md   # Claude Code 웹 검색 에이전트
  web-search-opencode.md
agents-codex/           # Codex 에이전트
```

## 워크플로우

2단계: (1) outline 생성 → (2) deep investigation. Human-in-the-loop 설계.

## Gotchas

- `skills/research-en/` 파일을 직접 편집하면 `~/.claude/skills/` 에 재설치 필요.
- EXA 웹 검색: `agents/web-search-agent.md` 참고 (`EXA_API_KEY` 환경변수 필요).
