# AGENTS.md

이 레포는 `문서 작성 스킬` 레포입니다. 에이전트가 이 레포를 읽을 때는 아래 원칙만 먼저 따르면 됩니다.

## 1. SKILL 중심

기준 파일은 [`skills/korean-doc-skill/SKILL.md`](./skills/korean-doc-skill/SKILL.md)입니다. 문서 타입 프리셋, 예시, Confluence 세부는 같은 폴더의 `PRESETS.md` / `EXAMPLES.md` / `REFERENCE.md`로 분리돼 있고, SKILL.md가 언제 무엇을 읽을지 안내합니다.

## 2. 사용자 README 우선

공개 사용자는 [`README.md`](./README.md)를 먼저 읽습니다. README에는 사용자 기준 설치와 사용만 둡니다.

## 3. tracked 영역 익명화

git tracked 파일에는 실제 문서 제목, 제품명, 프로젝트명, URL, page id를 남기지 않습니다. 관련 기준은 [`PRIVACY.md`](./PRIVACY.md)를 따릅니다.

## 4. README와 SKILL의 일관성 유지

사용자용 설명은 README에 맞추고, 스킬 규칙의 기준은 [`skills/korean-doc-skill/SKILL.md`](./skills/korean-doc-skill/SKILL.md)에 둡니다. Git에 올리는 영역에서는 방법론만 공유하고 실제 회귀 결과는 로컬에서만 관리합니다.

## 5. 기본 checkout과 공용 스킬 보호

`~/.agents/skills/korean-doc-skill`과 `~/.claude/skills/korean-doc-skill`이 기본 checkout을 직접 가리킬 수 있으므로, 기본 checkout은 항상 `main`에 두고 다른 브랜치로 전환하지 않습니다. Feature branch와 PR 작업은 반드시 별도 git worktree에서 진행합니다.

병합과 공용 스킬 갱신은 분리합니다. PR을 `main`에 병합한 뒤, 별도 배포 단계에서만 기본 checkout을 최신 `main`으로 갱신합니다.
