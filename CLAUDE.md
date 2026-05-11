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

- **재설치 필수**: `skills/research-en/` 를 직접 편집한 후 `cp -r skills/research-en/* ~/.claude/skills/` 재실행 안 하면 변경이 적용되지 않음.
- **EXA 키 미설정 시**: `agents/web-search-agent.md` 의 웹 검색 에이전트가 작동 안 함 — `export EXA_API_KEY=<key>` 필수.
- **스킬 설치 경로 혼동**: Claude Code 는 `~/.claude/skills/`, Codex 는 `~/.codex/agents/` — 설치 대상 플랫폼 확인 후 cp.
- **research vs research-deep**: `/research` 는 1단계 outline 생성, `/research-deep` 는 outline 기반 심층 조사 — 순서 의존성 있음 (outline 없이 deep 실행 불가).
- **중문 스킬 호환**: `skills/research-zh/` 는 Claude Code 전용, Codex 용은 `research-codex-zh/` 별도 — 혼용 금지.
