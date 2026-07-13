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

- 목적은 과금 은폐가 아니라 고객 안내 단순화 / 문의 부담 감소
- 업무 중단 완화 효과가 부수적으로 따라옴
- 일정은 별도 협의 (다음 분기 내 적용 목표)

If a fourth point matters, it belongs in a body section, not in the label section.

## Scaffolded sections

Avoid: adding `시사점`, `리스크`, `보고 시 설명 포인트` with one generic bullet each because the preset lists them.

Prefer: omit the section. A preset is a menu. An empty-calorie section costs the reader more than a missing one.

## Headings

Prefer:

- `### 무료 사용자 수익화는 필요하나 총매출 영향은 제한적`
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
- `무료 사용자 수익화는 필요하나 총매출 영향은 제한적`
- `규제 위험이 있어 자동 권유 방식은 적합하지 않음`

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

- `서비스마다 개선 수단 다름`
- `비용 점검 후 제안 도출`

Prefer (dense, 판단과 근거를 한 줄에 함께):

- `서비스별 원가 구조와 사용 양상이 달라 하나의 기준으로 판단하기 어려움. 서비스별 수익화 수단을 따로 정해야 함`
- `비용이 큰 영역부터 원인을 상세 분석하고 재무 영향이 큰 순서로 실행안 도출`

## Business planning tone (대외·보고 문서 격상)

전략·기획·보고·제안은 비즈니스 기획서 문어체로 정리한다. 전문성을 보여주기 위해 영어 표현을 덧붙이지 말고, 판단과 근거의 정확성으로 문서의 무게를 만든다.

Prefer:

- `전사 손익 관점에서 공통 인프라와 고정비까지 포함해 수익성 진단`
- `확대·효율화·조정 영역을 구분하고 구체적인 실행 과제로 연결`
- `확정값과 추정값을 분리해 잘못된 의사결정 위험을 줄임`
- `지표 분석에 그치지 않고 과금 정책과 화면 변경 등 실제 개선으로 연결`

Avoid (구어·캐주얼·풀어쓴 설명):

- `회사 전체로 보면서 같이 쓰는 비용까지 넣어서 돈 되는지 봄`
- `어디를 키우고 줄이고 바꿀지 정해서 실제로 해볼 것`
- `확실한 거랑 아직 모르는 거 섞으면 위험하니까 나눠서 봄`

캐주얼체는 솔직하지만 대외·임원 문서에서 프로젝트를 작아 보이게 한다. 반대로 모든 용어를 영어로 박는 것도 역효과다. 정착된 용어만 골라 쓴다.

## Literal translation

Avoid: 영어 단어마다 한국어 단어 하나를 고정해 문맥과 관계없이 반복

- `저장소 경계를 정의`
- `문서의 경계를 확정`
- `상위 10% 경계`
- `이 문서가 진실 소스`

Prefer: 문장에서 실제로 뜻하는 기능을 바로 표현

- `두 저장소의 역할을 구분`
- `문서의 적용 범위와 제외 대상을 확정`
- `상위 10% 진입 기준`
- `이 문서를 공식 기준으로 사용`

`경계값`, `보안 경계`처럼 원래 자연스러운 표현까지 금지하지 않는다. 단어 목록으로 기계적으로 바꾸지 말고 문맥을 판단한다.

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
