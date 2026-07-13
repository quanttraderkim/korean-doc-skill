# korean-doc-skill

한국어 비즈니스 문서를 AI 에이전트가 더 짧고, 더 구조적으로, 더 보고용 메모답게 쓰도록 돕는 문서 작성 스킬 레포입니다.

문제의식은 단순합니다. AI가 한국어 업무 문서를 만들면 대체로 말이 많고, `~입니다 / ~합니다`가 반복되고, 추상 수식어가 많아지고, 줄글이 길어집니다. 이 킷은 그 반대로 밀어줍니다. 결론 우선, 짧은 판단형 문장, 의미가 있는 제목, 필요한 곳에만 불릿과 표, 긴 문서에서는 `A. / A-1.` 또는 `1. / 3-1.` 넘버링, 그리고 분량 상한입니다. 구조를 만들더라도 결과물은 원문보다 길어지지 않는 것이 기본값입니다.

## 왜 쓰나

이 레포는 아래 같은 문제를 줄이기 위한 것입니다.

- 문서가 너무 길어서 첫 화면에서 결론, 요청사항, 다음 액션이 안 보임
- `결론`, `시사점` 같은 라벨 섹션마다 불릿이 5~6개씩 쌓여 정작 판단이 묻힘
- 프리셋 섹션을 채우려고 내용 없는 `시사점`, `리스크` 섹션이 만들어짐
- `~입니다 / ~합니다` 설명문이 반복돼 보고용 문서 느낌이 약함
- 표로 정리해야 할 내용을 줄글로 길게 풂
- 표가 필요하지 않은 라벨+설명 내용까지 과하게 표로 만듦
- 제목이 메시지 역할을 못 하고 단순 라벨로 끝남
- 에이전트마다 결과 스타일이 달라 문서 품질이 들쭉날쭉함
- 첫 화면에 판단이나 요청사항이 안 보이고, 비교 정보가 줄글에 묻힘

목표는 문장을 예쁘게 꾸미는 것이 아닙니다. 더 빨리 읽히고, 더 빨리 판단되고, 더 일관되게 수정되는 문서를 만드는 것입니다.

## 30초 이해

이 레포를 적용하면 문서가 대략 아래 방향으로 바뀝니다.

Before:

> 이 기능은 사용자에게 여러 가지 의미 있는 가치가 있을 것으로 보이며, 장기적으로 긍정적인 효과가 기대됩니다.

After:

> 핵심 문제는 실행 누락.
>
> 초기 포지션은 범용 AI가 아니라 업무 보조 도구.

즉 긴 설명문을 짧은 판단형 문장, 의미 있는 제목, 필요한 불릿과 표로 바꾸는 킷입니다. 표는 비교 축이 있을 때만 쓰고, Confluence/wiki에서 라벨+설명 구조는 보통 `####` 제목과 일반 불릿으로 둡니다.

단 간결은 알맹이를 깎는 것이 아니라 군더더기를 걷는 것입니다. 전략·기획·보고처럼 대외·임원용 문서는 캐주얼하게 줄이기보다 비즈니스 기획서 문어체로 격상합니다.

## 빠르게 써보기

이 레포의 중심은 [`skills/korean-doc-skill/SKILL.md`](./skills/korean-doc-skill/SKILL.md)입니다. 실제 사용은 훨씬 단순합니다. 보통은 스킬을 먼저 읽게 한 뒤, 문서 성격만 자연어로 말하면 됩니다.

기본 원칙은 두 가지입니다. 첫째, 사용자는 `전략 문서`, `PRD`, `위클리`, `이슈 대응`, `허브 문서`처럼 대략적인 문서 성격만 말하면 됩니다. 둘째, mode는 특별한 이유가 없으면 생략합니다. mode를 생략하면 스킬은 기본적으로 `원문 논리는 유지하고 구조만 더 읽히게 만드는 쪽`으로 해석합니다.

### 실제 사용은 이렇게 생각하면 됩니다

Codex, Claude, OpenClaw, 다른 셸 에이전트 모두 아래 두 방식 중 하나로 쓰면 충분합니다.

1. 사용자가 문서 성격을 말함  
예: `전략 문서로 정리해줘`, `사업 기회 검토처럼 써줘`, `이건 PRD처럼 써줘`, `이건 위클리 위키야`

2. 에이전트가 문서 내용을 보고 추론함  
예: 문서가 이미 논의안·방향성 검토·옵션 비교 중심이면 전략 문서로, 범위·정책·오픈 이슈 중심이면 PRD로 해석

즉 사용자가 정확한 preset 이름을 외울 필요는 없습니다. 스킬을 먼저 읽게 하고, 문서 성격을 말하거나 원문을 같이 주면 대부분 충분합니다.

### 권장 방식: 모든 에이전트에서 SKILL.md를 기준으로 사용

1. 에이전트에게 이 레포의 [`skills/korean-doc-skill/SKILL.md`](./skills/korean-doc-skill/SKILL.md)를 읽게 함
2. 원문 초안을 함께 줌
3. `전략 문서`, `PRD`, `위클리`, `이슈 대응`, `허브 문서`처럼 대략적인 문서 성격만 말함
4. 정말 필요할 때만 mode를 따로 지정함

예시 요청:

> 이 레포의 `skills/korean-doc-skill/SKILL.md`를 기준으로 이 문서를 전략 문서로 다시 써줘. 원문 논리는 유지하고, 첫 화면에 결론과 요청사항이 보이게 해줘.

또는 더 짧게:

> 이거 위키에 올릴 전략 문서인데, 너무 설명형이라 보고용 메모처럼 다시 정리해줘.

> 이 문서는 PRD에 가까워. 범위, 정책, 오픈 이슈가 바로 보이게 정리해줘.

> 이건 위클리 위키야. 한 화면에서 이번 주 핵심 변화와 리스크가 보이게 바꿔줘.

> 이건 상태판이 큰 위클리야. 회의용으로 먼저 읽히게 정리해줘.

> 이건 이슈 대응 문서야. 예상 질문, 권고 답변, 리스크를 먼저 보이게 정리해줘.

### 실제 요청은 보통 이 정도면 충분합니다

아래처럼만 말해도 대부분의 에이전트가 적절한 프리셋을 추론할 수 있습니다.

| 이렇게 말하면 됨 | 내부적으로는 대략 이렇게 해석 |
| --- | --- |
| 전략 문서로 정리해줘 | `strategy memo` |
| 사업 기회 검토처럼 써줘 | `business opportunity / market validation` |
| 상위기획 문서처럼 써줘 | `upper planning` |
| PRD처럼 정리해줘 | `PRD / service planning` |
| 유즈케이스 문서로 바꿔줘 | `use case` |
| 위키 허브 문서처럼 만들어줘 | `hub page` |
| 위클리처럼 정리해줘 | 기본은 `weekly update`, 상태판이 크면 `team weekly board` 변형 |
| 이슈 대응 문서처럼 정리해줘 | `response memo` |
| 이슈 히스토리 위키처럼 정리해줘 | `issue history / incident log` |

즉, 실제 사용에서는 `정확한 스킬 이름 + 정확한 mode`를 매번 외워서 말하는 것보다, 문서 성격을 자연어로 말하는 편이 더 현실적입니다. 더 나아가 문서 원문 자체가 이미 전략 문서, PRD, 위클리, 허브 문서처럼 보인다면 에이전트가 그 성격을 보고 추론해도 됩니다.

### Codex에서 쓸 때

[`skills/korean-doc-skill`](./skills/korean-doc-skill) 폴더를 로컬 Codex skills 디렉터리에 두고, 문서 요청 시 `$korean-doc-skill`을 같이 호출하면 됩니다.

### Claude나 다른 에이전트에서 쓸 때

Claude Code는 공식적으로 personal / project scope skill을 지원합니다. 이 레포의 스킬을 Claude에서 실제 skill처럼 쓰려면, Claude 공식 문서가 안내하는 위치인 `~/.claude/skills/<skill-name>/SKILL.md` 또는 프로젝트의 `.claude/skills/<skill-name>/SKILL.md`로 설치하면 됩니다. 스킬 이름은 `korean-doc-skill` 기준으로 쓰는 편이 일관됩니다. 설치 후에는 자동 로드되거나 `/korean-doc-skill`로 직접 호출할 수 있습니다.

예시:

```bash
mkdir -p ~/.claude/skills
cp -R skills/korean-doc-skill ~/.claude/skills/
```

프로젝트 전용으로 두고 싶다면:

```bash
mkdir -p .claude/skills
cp -R skills/korean-doc-skill .claude/skills/
```

이 레포의 root [`CLAUDE.md`](./CLAUDE.md)에는 Claude 기준 사용 방식을 따로 짧게 정리해두었습니다.

### OpenClaw / ClawHub에서 쓸 때

현재 [`SKILL.md`](./skills/korean-doc-skill/SKILL.md)는 `name`, `description`, `homepage`, `metadata.openclaw`를 포함한 OpenClaw-friendly frontmatter로 정리돼 있어서, OpenClaw workspace skill이나 ClawHub 배포용 skill로 쓰기 좋은 상태입니다.

OpenClaw 로컬 workspace에서는 `skills/korean-doc-skill/`를 `<workspace>/skills/korean-doc-skill/` 아래에 두고 쓰면 됩니다. 설치와 sync 흐름 자체는 OpenClaw / ClawHub 공식 문서를 따르는 편이 가장 안전합니다.

## Confluence 운영 원칙

Confluence 문서는 모두 같은 방식으로 다루면 오히려 품질이 떨어질 수 있습니다. 이 레포에서는 아래 두 유형으로 나눠서 보는 편이 더 안전합니다.

### Plain Page

- 처음 만드는 초안 문서
- 표 색상, 셀 병합, 스마트 링크, 이미지 배치 같은 native polish가 거의 없는 페이지
- 이런 문서는 markdown 중심 작성과 전체 재업로드가 잘 맞음

### Native-Managed Page

- 사람이 Confluence 화면에서 직접 다듬은 페이지
- 첫 열 강조, 색상, 병합 셀, 이미지 표 삽입, smart link, 수동 배치가 들어간 페이지
- 이런 문서는 markdown 전체 치환보다 section patch나 storage HTML 수정이 더 안전함

실무 원칙은 단순합니다. 내용 초안과 구조 설계는 markdown으로 관리하고, Confluence 고유 서식을 적용한 뒤에는 표현 형식을 Confluence storage에서 관리합니다. 즉 `내용 기준은 markdown`, `표현 형식 기준은 Confluence native structure`로 나눕니다.

## 문서 타입별 추천 해석

실제 사용에서는 위 표처럼 자연어로 말해도 충분하지만, 더 명시적으로 쓰고 싶을 때는 아래 표를 참고하면 됩니다.

| 문서 타입 | 언제 쓰나 | 입력 힌트 |
| --- | --- | --- |
| 전략 메모 | 왜 중요한지, 어떤 판단이 필요한지 먼저 보여줘야 할 때 | `strategy memo` + `light report-style` |
| 추진 보고 / 킥오프 | 프로젝트 추진 틀·방향·현황을 임원에게 공유할 때 (핵심 요약·일정·주요 판단·요청 사항) | `executive kickoff` + `light report-style` |
| 사업 기회 / 시장 검증 | 파트너 연계, 1차 시장, MVP, 과금, 법무/개인정보보호 검토를 한 문서에 묶어 사업화 가능성을 확인할 때 | `business opportunity / market validation` + `light report-style` |
| 상위기획 / 컨셉 기획 | 방향, 우선순위, 1차 범위를 먼저 보여줘야 할 때 | `upper planning` + `light report-style` |
| PRD / 서비스기획 | 문제 정의, 범위, 흐름, 정책, 오픈 이슈를 분리해야 할 때 | `PRD / service planning` + `light report-style` |
| Skill / Capability Spec | 입력, 출력, 예외, 평가 기준을 명확히 써야 할 때 | `skill spec` + `source-preserving` |
| 유즈케이스 / 버티컬 워크플로 | `상황 / 동작 / 가치 / 제한` 구조로 정리해야 할 때 | `use case` + `light report-style` |
| 허브 / 인덱스 페이지 | 문서 묶음의 역할, 핵심 문서, 카테고리를 정리해야 할 때 | `hub page` + `source-preserving` |
| 위클리 | 짧은 weekly summary, 대시보드 업데이트, 상태판 중심 팀 위클리까지 포함하는 문서군. 기본은 `weekly update`로 보고, 큰 상태판이면 보드형 변형으로 해석 | `weekly update` + `light report-style` 기본, 큰 상태판이면 `team weekly board` 변형 |
| 의사결정 원페이저 | 선택지 비교와 요청 결정사항을 한 장으로 정리할 때 | `decision one-pager` + `light report-style` |
| 트래킹 / 옵스 보드 | 살아 있는 이슈 보드, 확인 필요사항, 운영 현황, 상태 추적 문서를 빠르게 읽히게 정리할 때 | `tracking / ops board` + `source-preserving` 또는 `light report-style` |
| 이슈 히스토리 / 인시던트 로그 | 닫힌 이슈, 장애, 대응 이력을 누적 참조용으로 남길 때 | `issue history / incident log` + `source-preserving` |
| 대응 문서 / Q&A 메모 | 대외·대내 답변, 예상 질문, 모범 답변, 리스크, 추가 확인사항을 정리할 때 | `response memo` + `light report-style` |

## 무엇이 들어 있나

스킬은 진입점 하나와 필요할 때만 읽는 참조 파일 셋으로 구성됩니다.

- 진입점이자 핵심 규칙: [`skills/korean-doc-skill/SKILL.md`](./skills/korean-doc-skill/SKILL.md)
- 문서 타입별 프리셋: [`skills/korean-doc-skill/PRESETS.md`](./skills/korean-doc-skill/PRESETS.md)
- prefer / avoid 예시 모음: [`skills/korean-doc-skill/EXAMPLES.md`](./skills/korean-doc-skill/EXAMPLES.md)
- Confluence / wiki 전달 세부: [`skills/korean-doc-skill/REFERENCE.md`](./skills/korean-doc-skill/REFERENCE.md)
- Codex / Claude / 다른 에이전트에서 스킬을 적용하는 방법
- 스타일 차이를 바로 볼 수 있는 before / after 예시
- 스킬을 실제 문서로 점검하고 개선할 수 있는 evaluation 루프

## 기본 방향

- 간결의 정의: 빈말·중복·`~입니다` 남발·장황을 걷어내는 것이지 알맹이·근거·전문성을 줄이는 것이 아님 (짧게가 아니라 군더더기 없이 dense하게)
- 문서 등급으로 톤 조절: 전략·기획·보고·제안·킥오프는 비즈니스 기획서 문어체로 격상, 런북·체크리스트·위클리만 더 압축한 메모체
- 라벨 섹션(`결론`, `요약`, `주의점`, `다음 액션` 류)은 불릿 3개 이내
- 불릿 한 개는 한 줄. 길어지면 분리하거나 하위 불릿으로
- 섹션은 메뉴. 내용 없는 섹션은 템플릿 채우기식으로 만들지 않음
- 줄일 것은 분량이 아니라 군더더기. 빈말·중복은 덜어내되 근거·논리를 채우느라 길어지는 것은 허용
- 에세이형 설명보다 보고용 메모체 우선
- `~입니다 / ~합니다 / ~됩니다` 최소화
- 모든 문장을 기계적으로 `~함`으로 끝내지는 않음
- 긴 설명형 `~한다`체도 기본값으로 두지 않음
- 명사형, 짧은 판단형 끝맺음 우선
- 결론, 요청사항, 다음 액션을 앞에 배치
- 사업 기회 검토 문서는 억지 요약표보다 `추진 목적 및 사업 비전`과 `단기 목적 / 장기 목적 / 핵심 방향` 우선
- 제목은 주제 라벨이 아니라 메시지 역할로 사용
- 헤딩 아래 설명형 연결문장 최소화
- 섹션 사이 줄바꿈과 블록 간 여백을 충분히 둠
- 불릿은 병렬 항목에만 사용
- 라벨과 설명이 있는 항목은 `라벨: 설명` 한 줄보다 구조화 우선
- Confluence/wiki에서 `###` 아래가 평면 불릿이라 위계가 안 보이면 의미 묶음의 첫 라벨 불릿을 `####`로 승격해 3단 구조를 만들되, `####`는 하위 불릿 2개 이상 실질 묶음에만 (한 포인트는 라벨 불릿로 유지)
- `항목 / 판단`, `구분 / 내용` 2열 요약표가 라벨+설명만 담고 있으면 `####` 제목 + 일반 불릿 우선
- 기본 규칙, 예외 처리, override, 변경 이력은 한 문장으로 합치지 않고 불릿 계층으로 분리
- 표는 비교 축, 반복 필드, 소유자, 리스크, 옵션 정리가 있을 때만 사용
- `항목 / 설명`만 있는 표는 불릿으로 바꿀 수 있는지 먼저 확인
- Confluence에 올릴 문서는 inline code와 underscore가 깨지지 않는지 확인하고, 꼭 필요한 필드명이 아니면 읽히는 라벨 우선
- Confluence에서 리스트 뒤 표/다음 제목이 붙어 보일 수 있으면, 빈 줄만 믿지 말고 다음 블록의 역할을 한 줄로 명시
- 비용, 법무, 개인정보보호는 단정하지 않고 `가정`, `참고용`, `N/A`, `재검토`, `확인 필요`를 명확히 표시
- 긴 문서는 `A.`, `A-1.` 넘버링 권장
- Confluence 검토 문서나 사업 검토 자료는 `1.`, `3-1.` 같은 숫자형 섹션도 유지 가능
- 비교와 카테고리는 문단보다 작은 표가 나을 수 있으나, 단순 요약은 불릿 우선
- `먼저 볼 항목`, `지금 먼저 볼 것`, `읽기 순서`, `권장 읽기 순서` 같은 메타 제목은 기본값으로 쓰지 않음
- 병렬 항목 자체가 내용인 단순 리스트는 불릿으로 유지하고, 모든 불릿을 제목으로 승격하지 않음

## 예시

- [`examples/before-strategy-memo.md`](./examples/before-strategy-memo.md)
- [`examples/after-strategy-memo.md`](./examples/after-strategy-memo.md)

## 이 스킬을 어떻게 진화시키나

이 레포는 정답 고정형이 아니라 피드백 루프를 전제로 합니다. 핵심은 `느낌상 좋아졌다`가 아니라, 같은 문서를 기준으로 `Skill Off / Skill On`을 비교하고, 반복 실패를 코드화해서 다시 스킬 규칙으로 환원하는 것입니다.

권장 루프는 아래 순서입니다.

1. 고정된 regression case 하나 선택
2. 스킬 없이 한 번, 스킬을 켜고 한 번 결과 생성
3. 같은 문서를 [`evaluation/rubric.md`](./evaluation/rubric.md)와 [`evaluation/review-checklist.md`](./evaluation/review-checklist.md)로 비교
4. 반복 실패를 [`evaluation/failure-taxonomy.md`](./evaluation/failure-taxonomy.md) 코드로 기록
5. 결과를 로컬 전용 `evaluation/results/*.local.md` 로그로 남김
6. 반복되는 실패만 스킬 규칙과 예시에 반영

관련 파일:

- [`evaluation/README.md`](./evaluation/README.md)
- [`evaluation/rubric.md`](./evaluation/rubric.md)
- [`evaluation/failure-taxonomy.md`](./evaluation/failure-taxonomy.md)
- [`evaluation/review-checklist.md`](./evaluation/review-checklist.md)
- [`evaluation/feedback-template.md`](./evaluation/feedback-template.md)
- [`evaluation/cases/README.md`](./evaluation/cases/README.md)
- [`evaluation/cases/case.template.md`](./evaluation/cases/case.template.md)
- [`evaluation/scoreboard.template.md`](./evaluation/scoreboard.template.md)
- [`evaluation/results/README.md`](./evaluation/results/README.md)
- [`PRIVACY.md`](./PRIVACY.md)

목표는 문장을 예쁘게 만드는 것이 아닙니다. 더 빨리 읽히고, 더 빨리 판단되고, 더 일관되게 개선되는 문서를 만드는 것입니다.

## 익명화 원칙

이 레포의 git tracked 파일은 항상 일반화·익명화 상태를 유지합니다. 실제 문서 제목, 제품명, 프로젝트명, URL, page id는 넣지 않습니다. 실제 회귀 결과, scorecard, 날짜별 평가 로그도 git에 두지 않고 로컬 전용 `.local.md` 파일로만 관리합니다. 관련 기준은 [`PRIVACY.md`](./PRIVACY.md)를 따릅니다.
