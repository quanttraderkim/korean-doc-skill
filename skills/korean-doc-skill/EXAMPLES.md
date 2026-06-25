# Worked Examples

Prefer/avoid samples for the rules in SKILL.md. The first two cover the most common real-world failure: verbose label sections and scaffolded sections.

## Label-section bullet bloat

Avoid (6 bullets, restating each other and the heading):

#### 결론

- 이번 변경은 과금 정책을 단순화하는 것이 목적
- 과금 정책 단순화를 통해 고객 혼란을 줄일 수 있음
- 고객 혼란이 줄면 문의 대응 부담도 감소할 것으로 기대
- 운영 관점에서도 업무 중단을 완화하는 효과가 있음
- 따라서 이번 변경은 필요한 변경으로 판단됨
- 상세 일정은 별도 협의 필요

Prefer (3 bullets, one line each, no restatement):

#### 결론

- 목적은 과금 은폐가 아니라 고객-facing 단순화 / 문의 부담 감소
- 업무 중단 완화 효과가 부수적으로 따라옴
- 일정은 별도 협의 (다음 분기 내 적용 목표)

If a fourth point matters, it belongs in a body section, not in the label section.

## Scaffolded sections

Avoid: adding `시사점`, `리스크`, `보고 시 설명 포인트` with one generic bullet each because the preset lists them.

Prefer: omit the section. A preset is a menu. An empty-calorie section costs the reader more than a missing one.

## Headings

Prefer:

- `### 무료 유저 수익화는 필요하나 총매출 임팩트는 제한적`
- `### 초기 도입 타깃은 반복 고객 관리 업종이 적절`

Avoid:

- `### 사업성`
- `### 타깃`

The good examples carry a judgment in the heading itself. The bad ones are topic labels that force the reader into the body to find the message.

## Bullets

Good (parallel items):

- `후속 연락 누락`
- `재방문 고객 관리 부재`
- `매출 회수 근거 약함`

Bad (not parallel, causal chain split into bullets):

- `고객 관리가 중요함`
- `그래서 이 기능이 필요함`

The bad example mixes abstraction levels with a causal link between items. It should be a short paragraph or a heading-level judgment.

## Tone

Prefer:

- `초기 도입은 A안 우선`
- `후속 연락 누락이 거래 누락으로 이어짐`
- `무료 유저 수익화는 필요하나 총매출 임팩트는 제한적`
- `규제 리스크로 자동 권유 포지션은 비적합`

Avoid:

- `고객 경험을 보다 전략적으로 고도화할 수 있음`
- `본질적으로 중요한 의미를 갖는다고 판단됨`
- `결과적으로 여러 측면에서 유의미한 효과 기대 가능`
- `이 기능은 고객관리에 중요한 역할을 한다`

Also avoid bridge sentences (`핵심은 ~라는 점입니다`, `이번 건에서 가장 바꿀 가치가 큰 부분은 여기입니다`). Replace with a tighter heading or memo line:

- `판단 기준은 대응 속도와 운영 단순화`
- `우선 전환 대상은 전면 / 보상형 / 보상형 전면 preload API`

## Over-compression (간결과 알맹이 손실 구분)

간결은 빈말을 빼는 것이지 근거를 빼는 것이 아니다. 판단만 남기고 왜·무엇을 날리면 짧지만 쓸모가 준다.

Avoid (근거를 통째로 날린 과도 축약):

- `서비스마다 레버 다름`
- `비용 점검 후 제안 도출`

Prefer (dense, 판단과 근거를 한 줄에 함께):

- `서비스별 원가 구조·사용 양상 편차로 단일 잣대 판단 불가, 특성에 맞는 수익화 레버를 개별 식별`
- `상위 비용 구조를 먼저 진단(Top-down)해 재무 임팩트 큰 영역부터 딥다이브 후 실행안 도출`

## Business planning tone (대외·보고 문서 격상)

전략·기획·보고·제안은 비즈니스 기획서 문어체로 올린다. 정착된 프레임 용어는 여러 문장을 한 단어로 압축한다.

Prefer:

- `전사 P&L 관점에서 공통 인프라·고정비까지 포괄해 수익성 진단`
- `성장(Scale-up)·효율화·조정 영역을 식별하고 구체 Action Item으로 연결`
- `확정(실측)과 가설(추정·POC)을 분리해 의사결정 리스크 최소화`
- `Action-Oriented: 지표 분석에 그치지 않고 과금 정책·노출(UI/UX) 변경 등 실질 성과로 연결`

Avoid (구어·캐주얼·풀어쓴 설명):

- `회사 전체로 보면서 같이 쓰는 비용까지 넣어서 돈 되는지 봄`
- `어디를 키우고 줄이고 바꿀지 정해서 실제로 해볼 것`
- `확실한 거랑 아직 모르는 거 섞으면 위험하니까 나눠서 봄`

캐주얼체는 솔직하지만 대외·임원 문서에서 프로젝트를 작아 보이게 한다. 반대로 모든 용어를 영어로 박는 것도 역효과다. 정착된 용어만 골라 쓴다.

## Punctuation

Prefer:

- `완료 조건은 케이스별 상이 (각 섹션 참조)`
- `기본: 총 예산 내 분배`
- `방향성만. 세부는 미정`

Avoid:

- `완료 조건은 케이스별 상이 — 각 섹션 참조`
- `기본 — 총 예산 내 분배`

Em dash in Korean memos reads as translated English. Colon, parentheses, period, slash, and nested bullets cover the same roles.

## Tables

Use tables for:

- option comparison
- target segment comparison
- ownership / R&R
- repeated status, metric, policy, or question fields

Do not use tables for:

- one short claim or one example sentence
- label + explanation content (`항목 / 설명`, `항목 / 판단`)
- sequential reasoning
- two or three related bullets without shared columns
