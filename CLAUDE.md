# CLAUDE.md

이 레포를 Claude에서 사용할 때의 기본 원칙은 단순합니다.

기준 파일은 [`skills/korean-doc-skill/SKILL.md`](./skills/korean-doc-skill/SKILL.md)입니다. 스킬 이름은 `korean-doc-skill`입니다. Claude Code는 공식적으로 `~/.claude/skills/<skill-name>/SKILL.md` 또는 프로젝트 `.claude/skills/<skill-name>/SKILL.md` 위치의 스킬을 지원하므로, 가능하면 이 경로에 설치해서 실제 skill처럼 쓰는 방식을 권장합니다.

예시:

```bash
mkdir -p ~/.claude/skills
ln -sfn "$(pwd)/skills/korean-doc-skill" ~/.claude/skills/korean-doc-skill
```

설치 후에는 자동으로 관련 문서에서 로드되거나 `/korean-doc-skill`로 직접 호출할 수 있습니다.

권장 순서:

1. `skills/korean-doc-skill/SKILL.md`를 읽게 함
2. 문서 타입과 독자, 문서가 도울 일(판단·분석·정의·실행·추적·참고) 지정
3. 필요할 때만 `source-preserving`, `light report-style`, `report-first` 중 mode 지정. 생략하면 문서 타입에 맞춰 선택
4. 원문 초안을 함께 제공

예시:

> 이 레포의 `skills/korean-doc-skill/SKILL.md`를 기준으로 이 문서를 리더용 upper planning 문서로 다시 써줘. mode는 light report-style. 방향, 우선순위, 1차 범위가 첫 화면에서 보이고 구현 상세는 결정에 필요한 내용만 남겨줘.

이 레포는 스킬 중심 레포입니다. `SKILL.md`는 핵심 규칙과 워크플로만 담은 진입점이고, 문서 타입별 세부 구조는 같은 폴더의 `PRESETS.md`, prefer/avoid 예시는 `EXAMPLES.md`, Confluence 전달 세부는 `REFERENCE.md`에서 필요할 때 읽습니다.
