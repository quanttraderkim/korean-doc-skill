# korean-doc-skill

한국어 비즈니스 문서를 독자와 용도에 맞게 더 자연스럽고 찾기 쉽게 다듬는 문서 작성 스킬 레포입니다.

문제의식은 단순합니다. AI가 한국어 업무 문서를 만들면 말이 많아지고, 추상적인 표현과 줄글이 늘며, 반대로 형식을 강하게 주면 모든 문서가 같은 보고서 모양이 되기 쉽습니다. 이 스킬은 전략 문서에서는 판단, 데이터 분석에서는 확인된 결과, PRD에서는 정책과 예외, 런북에서는 실행 순서, 참고 위키에서는 정의와 조회 기준이 먼저 보이게 합니다.

## 왜 쓰나

이 레포는 아래 같은 문제를 줄이기 위한 것입니다.

- 문서가 너무 길어서 해당 문서에서 먼저 봐야 할 결론·결과·절차·조회 기준이 안 보임
- `결론`, `시사점` 같은 라벨 섹션마다 불릿이 5~6개씩 쌓여 정작 판단이 묻힘
- 프리셋 섹션을 채우려고 내용 없는 `시사점`, `리스크` 섹션이 만들어짐
- `~입니다 / ~합니다` 설명문이 반복돼 보고용 문서 느낌이 약함
- 표로 정리해야 할 내용을 줄글로 길게 풂
- 표가 필요하지 않은 라벨+설명 내용까지 과하게 표로 만듦
- 열 구성은 맞지만 같은 판단을 여러 표에서 반복해 문서가 불필요하게 길어짐
- 리더·임원용 보고에 구현 체크리스트·필드 목록·상세 QA·운영 절차가 그대로 들어감
- 펼치기가 삭제하거나 별도 실무 문서로 옮길 내용을 보관하는 곳으로 쓰임
- 분석 결과 제목이 방법·집계 조건·한계에 머물거나, 반대로 PRD·런북·참고 위키의 제목까지 판단형으로 바뀜
- 에이전트마다 결과 스타일이 달라 문서 품질이 들쭉날쭉함
- 첫 화면에 판단이나 요청사항이 안 보이고, 비교 정보가 줄글에 묻힘
- `boundary`, `source of truth`, `owner`를 문맥과 무관하게 `경계`, `정본`, `오너`로 옮겨 한국 업무 문서답지 않게 읽힘
- 검색되지 않는 새 약어를 만들거나, 반대로 DAU·API처럼 널리 쓰이는 용어까지 억지로 번역함

목표는 문장을 예쁘게 꾸미는 것이 아닙니다. 판단·이해·실행·조회 중 문서가 맡은 일을 더 빠르고 정확하게 끝내게 하는 것입니다.

## 30초 이해

이 레포를 적용하면 문서가 대략 아래 방향으로 바뀝니다.

Before:

> 이 기능은 사용자에게 여러 가지 의미 있는 가치가 있을 것으로 보이며, 장기적으로 긍정적인 효과가 기대됩니다.

After:

> 핵심 문제는 실행 누락.
>
> 초기 포지션은 범용 AI가 아니라 업무 보조 도구.

즉 긴 설명문을 용도에 맞는 제목과 내용 구조로 바꾸는 킷입니다. 전략·분석 결과는 확인된 판단과 결과를 제목에서 보여주고, PRD·런북·참고 위키는 정책·행동·정의를 찾기 쉬운 제목을 유지합니다. 불릿과 표는 정보 형태에 맞을 때만 씁니다.

단 간결은 알맹이를 깎는 것이 아니라 군더더기를 걷는 것입니다. 전략·기획·분석·보고처럼 대외·임원용 문서도 캐주얼체나 논문식 줄글 대신, 판단과 근거가 바로 보이는 간결한 보고체로 정리합니다.

## 빠르게 써보기

이 레포의 중심은 [`skills/korean-doc-skill/SKILL.md`](./skills/korean-doc-skill/SKILL.md)입니다. 실제 사용은 훨씬 단순합니다. 보통은 스킬을 먼저 읽게 한 뒤, 문서 성격만 자연어로 말하면 됩니다.

기본 원칙은 세 가지입니다. 첫째, 사용자는 `전략 문서`, `데이터 분석`, `PRD`, `런북`, `위클리`, `참고 위키`처럼 대략적인 문서 성격만 말하면 됩니다. 둘째, 에이전트는 독자와 문서 용도를 보고 무엇을 앞에 둘지 정합니다. 셋째, mode는 특별한 이유가 없으면 생략하며, 스킬이 문서 유형에 맞춰 source-preserving·light report-style·report-first 중 하나를 고릅니다.

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
3. `전략 문서`, `데이터 분석`, `PRD`, `런북`, `위클리`, `참고 위키`처럼 대략적인 문서 성격과 독자를 말함
4. 이 문서로 판단·이해·실행·조회할 내용이 있으면 함께 말함
5. 정말 필요할 때만 mode를 따로 지정함

예시 요청:

> 이 레포의 `skills/korean-doc-skill/SKILL.md`를 기준으로 이 문서를 전략 문서로 다시 써줘. 원문 논리는 유지하고, 첫 화면에 결론과 요청사항이 보이게 해줘.

> 리더에게 분석과 제안을 공유하는 문서야. 구현 검토사항을 모두 나열하지 말고, 리더가 알아야 할 판단과 논의 필요사항만 본문에 남겨줘.

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
| 데이터 분석 결과로 정리해줘 | `data analysis / research result` |
| 사업 기회 검토처럼 써줘 | `business opportunity / market validation` |
| 상위기획 문서처럼 써줘 | `upper planning` |
| PRD처럼 정리해줘 | `PRD / service planning` |
| 당직 런북으로 정리해줘 | `execution guide / runbook` |
| 유즈케이스 문서로 바꿔줘 | `use case` |
| 위키 허브 문서처럼 만들어줘 | `hub page` |
| 데이터 카탈로그 위키로 정리해줘 | `knowledge / reference wiki / data catalog` |
| 위클리처럼 정리해줘 | 기본은 `weekly update`, 상태판이 크면 `team weekly board` 변형 |
| 이슈 대응 문서처럼 정리해줘 | `response memo` |
| 이슈 히스토리 위키처럼 정리해줘 | `issue history / incident log` |

즉, 실제 사용에서는 `정확한 스킬 이름 + 정확한 mode`를 매번 외워서 말하는 것보다, 문서 성격을 자연어로 말하는 편이 더 현실적입니다. 더 나아가 문서 원문 자체가 이미 전략 문서, PRD, 위클리, 허브 문서처럼 보인다면 에이전트가 그 성격을 보고 추론해도 됩니다.

### Codex에서 쓸 때

저장소를 한 곳에 clone한 뒤 [`skills/korean-doc-skill`](./skills/korean-doc-skill) 폴더를 Codex skills 디렉터리에 symlink하면, 저장소를 `git pull`할 때 복사본을 다시 만들지 않아도 됩니다. 같은 스킬을 여러 경로에 중복 설치하지 않습니다.

```bash
mkdir -p ~/.codex/skills
ln -sfn "$(pwd)/skills/korean-doc-skill" ~/.codex/skills/korean-doc-skill
```

문서 요청 시 `$korean-doc-skill`을 같이 호출하면 됩니다.

### Claude나 다른 에이전트에서 쓸 때

Claude Code는 공식적으로 personal / project scope skill을 지원합니다. 이 레포의 스킬을 Claude에서 실제 skill처럼 쓰려면, Claude 공식 문서가 안내하는 위치인 `~/.claude/skills/<skill-name>/SKILL.md` 또는 프로젝트의 `.claude/skills/<skill-name>/SKILL.md`로 설치하면 됩니다. 스킬 이름은 `korean-doc-skill` 기준으로 쓰는 편이 일관됩니다. 설치 후에는 자동 로드되거나 `/korean-doc-skill`로 직접 호출할 수 있습니다.

저장소 갱신을 자동으로 반영하려면 복사보다 symlink를 권장합니다.

```bash
mkdir -p ~/.claude/skills
ln -sfn "$(pwd)/skills/korean-doc-skill" ~/.claude/skills/korean-doc-skill
```

프로젝트 전용으로 두고 싶다면:

```bash
mkdir -p .claude/skills
cp -R skills/korean-doc-skill .claude/skills/
```

이 레포의 root [`CLAUDE.md`](./CLAUDE.md)에는 Claude 기준 사용 방식을 따로 짧게 정리해두었습니다.

### OpenClaw / ClawHub에서 쓸 때

현재 [`SKILL.md`](./skills/korean-doc-skill/SKILL.md)는 `name`, `description`, `metadata.openclaw.homepage`와 버전 정보를 포함해 OpenClaw workspace skill이나 ClawHub 배포용 skill로 쓰기 좋은 상태입니다.

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
| 전략 메모 | 왜 중요한지, 어떤 판단이 필요한지 먼저 보여줘야 할 때 | `strategy memo` + `report-first` 또는 `light report-style` |
| 데이터 분석 | 확인된 결과와 해석 조건을 함께 보여줘야 할 때 | `data analysis` + `light report-style` |
| 추진 보고 / 킥오프 | 프로젝트 추진 틀·방향·현황을 임원에게 공유할 때 (핵심 요약·일정·주요 판단·요청 사항) | `executive kickoff` + `light report-style` |
| 사업 기회 / 시장 검증 | 파트너 연계, 1차 시장, MVP, 과금, 법무/개인정보보호 검토를 한 문서에 묶어 사업화 가능성을 확인할 때 | `business opportunity / market validation` + `light report-style` |
| 상위기획 / 컨셉 기획 | 방향, 우선순위, 1차 범위를 먼저 보여줘야 할 때 | `upper planning` + `light report-style` |
| PRD / 서비스기획 | 문제 정의, 범위, 흐름, 정책, 오픈 이슈를 정확히 분리해야 할 때 | `PRD / service planning` + `source-preserving` |
| 런북 / 체크리스트 | 순서, 명령, 판정값, 중단 조건을 보존해야 할 때 | `execution guide / runbook` + `source-preserving` |
| Skill / Capability Spec | 입력, 출력, 예외, 평가 기준을 명확히 써야 할 때 | `skill spec` + `source-preserving` |
| 유즈케이스 / 버티컬 워크플로 | `상황 / 동작 / 가치 / 제한` 구조로 정리해야 할 때 | `use case` + `light report-style` |
| 허브 / 인덱스 페이지 | 문서 묶음의 역할, 핵심 문서, 카테고리를 정리해야 할 때 | `hub page` + `source-preserving` |
| 지식·참고 위키 / 데이터 카탈로그 | 출처, 정의, 필드, 조인·적용 기준을 반복 조회할 때 | `knowledge / reference wiki / data catalog` + `source-preserving` |
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

- 독자와 문서 용도를 먼저 정하고, 판단·분석·정의·실행·추적·참고 중 필요한 구조를 선택
- 전략·분석 결과 제목은 확인된 판단과 결과를 보여주고, 방법·분모·한계는 관련 결과 아래에 배치
- PRD·정책·런북·참고 위키는 주제·행동·조회 제목을 유지하고 필요한 정책·예외·순서·필드·정의를 삭제하지 않음
- 같은 내용은 문서 전체에서 한 곳에만 두고, 내용 없는 프리셋 섹션은 만들지 않음
- 연결 논리는 문단, 병렬 항목은 불릿, 실행 순서는 번호 목록, 반복 필드·실제 비교는 표로 표현
- 불릿 수·소제목 수·원문 대비 증가율을 맞추기 위해 내용을 합치거나 쪼개지 않음
- 분량이 늘었다면 정확성·실행 안전성·탐색성 개선에 실제로 필요한지 확인
- `~입니다 / ~합니다` 설명문, 기계적인 `~함`, 긴 `~한다` 서술을 줄이고 자연스러운 한국어 업무 문어체 사용
- 영어를 한 단어씩 번역하지 않고 문장에서 하는 역할에 맞게 표현
- DAU·MAU·API·MCP·제품명·필드명·명령어는 유지하고 통용되지 않는 새 약어는 만들지 않음
- 표·펼치기·번호·H4 승격은 문서 유형과 Confluence 전달 방식에 맞을 때만 사용
- 비용·법무·개인정보보호와 검증 전 숫자는 `가정`, `참고용`, `확인 필요`로 구분

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
