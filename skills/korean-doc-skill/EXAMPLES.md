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

## The requester is usually not the audience

Avoid: writing a shared document as an assistant progress report to the requester.

> 요청하신 7월 자료를 검토했습니다. 데이터 파일 세 개를 대조했고 일부 값은 추가 확인 중입니다.

Prefer: start with what the document's actual audience needs to know.

### 7월 원가는 두 기능에 집중

- 두 기능이 단가 확인 원가의 82% 차지
- 단가 미확인 모델은 합계에서 제외

`어떤 파일을 열었는지`, `몇 차례 검토했는지`, `에이전트가 무엇을 확인했는지`는 공유 본문이 아니라 작업 기록에 둔다. 다만 단가 미확인처럼 결과 해석을 바꾸는 한계는 관련 결과 바로 아래에 남긴다. PRD의 미결 정책이나 런북의 중단 조건처럼 독자가 직접 사용해야 하는 제약도 삭제하지 않는다.

Avoid: `자료가 제한적이므로 추가 검토가 필요합니다. 필요하시면 세부 내용을 더 확인하겠습니다.`

Prefer: `사용자 식별값이 없어 개인별 재사용률은 계산할 수 없음.`

무엇이 부족한지와 어떤 판단이 불가능한지가 없으면 한계가 아니라 방어 문구다.

## Remove the unsupported proposal and its rebuttal together

Avoid: a report makes an unsupported proposal from one composition ratio, then keeps the rebuttal and a follow-up data list after the proposal is removed.

> 입력 비용 비중이 높으므로 입력량을 줄여야 함.
>
> 다만 이 서비스는 사용자 요청뿐 아니라 시스템 지시와 조회 문맥도 입력에 포함하므로, 이 비중만으로 입력량이 과도하다고 판단하지 않음.
>
> 추가로 필요한 자료: 요청 유형, 사용 모델, 결과 품질

Prefer: remove the unsupported proposal, the ratio that is not independently needed for the audience's understanding, judgment, or action, and its rebuttal together. Keep the separate finding that still has evidence.

### 비용은 고가 모델 두 개에 집중

- 고가 모델 두 개가 확인된 비용의 70% 이상을 차지
- 간단한 요청과 복잡한 요청에 같은 모델을 쓰는지 확인한 뒤 모델 선택 방식 검토

The preferred report does not mention the input-cost ratio because it is not independently needed for the audience's understanding, judgment, or action. The draft's own mistake does not prove that readers need a warning about it. Move the data needed for later analysis to the worklog. Keep an interpretation limit only when the audience would otherwise make a consequential misreading.

Do not apply this deletion rule to an official decision record that must explain why an option was excluded, or to a PRD whose reader must resolve an open policy. Those are required decision or implementation details, not drafting residue.

## Leadership-report detail bloat

Avoid: 후속 논의가 필요하다는 한 판단을 `후보 비교`, `논의 순서`, `출시 준비`, `향후 지표`, `필요한 기록`, `다음 결정` 표로 각각 풀어 같은 사용자 수요·권한·QA·측정 조건을 여러 번 반복한다. 열 구성이 맞아도 리더가 각 표를 비교해 별도 결정을 내리지 않는다면 보고 본문에는 필요하지 않다.

Prefer:

### 첫 적용 항목은 사용자 수요와 구현 여건을 확인한 뒤 결정

- 안내 경로와 업무 도구는 역할이 다르므로 각각 수요와 구현 가능성 확인 필요
- 이용 확대 방안은 대표 업무뿐 아니라 첫 사용 안내·속도·오류·권한 개선도 함께 검토
- 적용 대상·기간·확인 방법은 개발 범위를 정한 뒤 결정

검증에 필요한 구현 조건이나 지표 정의가 있으면 한 개의 펼치기나 별도 실무 문서에 모은다. 같은 판단을 뒷받침하지 않거나 예상 질문에도 쓰이지 않는 세부는 펼치기에 보관하지 않고 삭제한다.

리더용 한 장이 하나의 결정만 다룬다면 `사용자 수요`, `구현`, `권한`, `QA`, `운영`, `지표`를 각각 소제목으로 만들지 않는다. `제안`, `판단 기준`, `논의 필요사항`처럼 2~3개의 판단 단위로 묶고, 별도 실무 문서로 옮긴 세부 항목을 본문에서 다시 나열하지 않는다.

Avoid: 기존 전략 문서의 7장만 고치면서 장 안에 `목적`과 `핵심 요약`을 새로 만들고, 이어지는 소제목에서 같은 판단을 다시 설명한다.

Prefer: 문서 전체의 요약은 그대로 두고 7장에서는 2~3개의 판단형 소제목이나 판단 불릿부터 시작한다.

Avoid: `이용이 일부 사용자에게 집중돼 있음. 대표 업무를 검토.`처럼 현황과 제안 사이의 이유를 삭제한다.

Prefer: `이용이 일부 사용자에게 집중돼 전체 활성률이 낮으면 고객사가 계약 규모나 사용자별 한도를 줄일 수 있음. 신규·반복 사용을 늘릴 대표 업무를 검토할 필요.`처럼 현재 사실이 어떤 사업 위험·기회로 이어지고 왜 제안이 필요한지 한 번은 연결한다.

## One home per point

Avoid: `권한 확인 필요`를 후보 표, 출시 준비 표, 리스크, 다음 액션에서 반복한다.

Prefer: 권한이 실제 결정 조건인 섹션 한 곳에서만 설명하고, 다른 섹션에서는 반복하지 않거나 해당 섹션을 짧게 안내한다.

## Headings

전략 문서와 분석 결과 섹션은 제목에서 확인된 결과나 의미를 보여준다.

Prefer:

- `### 무료 사용자 수익화는 필요하나 총매출 영향은 제한적`
- `### 초기 도입 타깃은 반복 고객 관리 업종이 적절`

Avoid:

- `### 사업성`
- `### 타깃`

The good examples carry a judgment in the heading itself. The bad ones are topic labels that force the reader into the body to find the message.

다만 제목의 역할은 문서 유형에 따라 다르다. 아래 제목은 PRD·런북·참고 위키에서 그대로 사용할 수 있다.

- `### 예약 가능 조건과 적용 시간대`
- `### 큐 지연 여부 확인`
- `### 데이터셋과 적재 주기`
- `### 조인 및 집계 제한`

Avoid: 데이터 분석의 결과 섹션을 `### 분석 방법`, `### 집계 한계`, `### 비교 기준`만으로 구성해 확인된 결과가 제목에서 보이지 않게 만드는 것. 방법·분모·한계는 관련 결과 아래에 두되, 방법 검증이나 데이터 카탈로그가 문서 목적이면 주제형 제목을 유지한다.

## Bullets

Good (parallel items):

- `후속 연락 누락`
- `재방문 고객 관리 부재`
- `매출 회수 근거 약함`

Bad (not parallel, causal chain split into bullets):

- `고객 관리가 중요함`
- `그래서 이 기능이 필요함`

The bad example mixes abstraction levels with a causal link between items. It should be a short paragraph or a heading-level judgment.

## Analysis paragraphs

Avoid (판단·수치·조건이 한 문단에 묻힘):

> 전체 비용은 전월보다 늘었으며 특정 기능 두 개가 대부분을 차지한다. 다만 일부 모델은 단가가 확인되지 않아 실제 총비용은 더 클 수 있다. 따라서 비용이 큰 기능부터 사용 패턴을 확인하고 요금 정책을 검토한다.

Prefer (판단형 제목 아래 독립적인 핵심을 불릿으로 분리):

### 비용 증가는 두 기능에 집중, 단가 미확인분은 추가 확인 필요

- 비용: 특정 기능 두 개가 전체 증가분의 대부분을 차지
- 확인 필요: 단가가 없는 모델은 총비용에서 제외
- 다음 액션: 사용 패턴 확인 후 요금 정책 검토

원인과 해석이 직접 이어질 때만 짧은 문단을 쓴다.

> 필수 기능은 사용량 자체를 줄이기 어렵다. 따라서 요청 유형별로 모델을 나누는 방식이 단기 비용 절감에 더 적합하다.

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

전략·기획·분석·보고·제안도 간결한 보고체로 정리한다. 전문성을 보여주기 위해 긴 `~한다` 문단이나 영어 표현을 덧붙이지 말고, 판단과 근거의 정확성으로 문서의 무게를 만든다.

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

영어 단어마다 한국어 단어 하나를 고정하지 않는다. 원문 단어가 아니라 문장에서 하는 일을 옮긴다.

| 문맥 | 피할 표현 | 자연스러운 표현 |
| --- | --- | --- |
| 저장소별 담당 영역 | `저장소 경계를 정의` | `두 저장소의 역할을 구분` |
| 문서가 다루는 대상 | `문서의 경계를 확정` | `문서의 적용 범위와 제외 대상을 확정` |
| 지표 구간 | `상위 10% 경계` | `상위 10% 진입 기준` |
| 오류 판정 | `오류율 경계값 3%` | `오류율 기준 3%` 또는 `오류율 3% 초과 시 경고` |
| 망 분리 지점 | `외부망과 내부망의 보안 경계` | `외부망과 내부망 분리 구간` |
| 보안 통제 대상 | `보안 경계 설정` | `보안 적용 범위 설정` 또는 `접근 허용 범위 설정` |
| 협업 기준 문서 | `이 문서를 정본으로 관리` | `이 문서를 협업 기준으로 사용` |
| 현재 적용 정책 | `정책 정본` | `현재 적용 정책` 또는 `공식 정책 문서` |
| 집계에 사용할 데이터 | `데이터 정본` | `집계 기준 데이터` |
| 최신 파일 | `최신 정본` | `최신본` |
| 원래 파일 | `원천 정본` | `원본` 또는 `원천 파일` |
| 비용 변화의 주된 원인 | `비용 드라이버` | `주요 비용 요인` |
| 업무 책임 | `문서 오너` | `문서 담당자` 또는 `승인 책임자` |
| 진행 상황 공유 | `가시성을 확보` | `진행 상황을 한눈에 확인` 또는 `현황을 공유` |
| 대체 절차 | `fallback 경로` | `문제 시 사용할 방법` 또는 `대체 경로` |
| 정책상 제한 | `guardrail` | `필수 준수 조건`, `운영 원칙`, `안전 기준` |

`경계값`과 `보안 경계`도 자동으로 유지하지 않는다. 수치 판단에는 `기준값`·`판정 기준`·`진입 기준`, 보안 통제 대상에는 `보안 적용 범위`·`통제 구간`, 네트워크 분리 지점에는 `망 분리 구간`을 사용한다. `securityBoundary`처럼 정확한 필드명이거나 법령·사내 규정에서 정한 공식 명칭일 때만 그대로 쓴다. `API 호출 한도`, `DAU`, `user_id`처럼 널리 쓰이는 용어나 정확한 식별자는 유지한다. `fallback`·`guardrail`도 자동 보존하지 말고, 정확한 개념명·조직 표준 용어·필드명인지 확인한다.

## Invented jargon and abbreviations

Avoid:

- `평균 사용자 비용 효율(ACX)이 높음`
- `전략 임팩트를 높일 신규 레버 발굴`

Prefer:

- `기간 총원가를 같은 기간의 평균 DAU로 나눈 비교값이 높음` (분자·분모·기간 병기)
- `전략 효과를 높일 새로운 개선 수단 발굴`

DAU·MAU·API·MCP·PRD처럼 널리 쓰이는 용어는 억지로 번역하지 않는다. 새 약어가 검색되지 않거나 별도 설명 없이는 이해하기 어렵다면 약어를 만들지 말고 뜻을 풀어 쓴다.

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

Real columns are necessary but not sufficient. Use a table only when the reader must compare the rows on those columns and the table is faster than 2~3 bullets.

Do not use tables for:

- one short claim or one example sentence
- label + explanation content (`항목 / 설명`, `항목 / 판단`)
- sequential reasoning
- two or three related bullets without shared columns
- a working-level checklist that does not affect the report reader's decision
- multiple tables that answer the same question with different headings
