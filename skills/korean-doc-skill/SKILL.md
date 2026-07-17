---
name: korean-doc-skill
description: Rewrites Korean business documents for the intended reader and decision using natural Korean workplace language. Removes cross-section repetition and unnecessary working detail, uses tables only when they shorten real comparisons, avoids invented jargon and literal translations, and keeps widely used terms such as DAU and API. Use when Korean docs feel too long, too detailed, repetitive, table-heavy, translated, or hard to scan, including leadership reports, strategy memos, wikis, PRDs, and weekly updates. Use when the user says 정리해줘 / 다듬어줘 / 보고서처럼 / 번역투 없애줘 / 자연스러운 한국어로.
metadata: {"openclaw":{"homepage":"https://github.com/quanttraderkim/korean-doc-skill", "version": "2.3.0"}}
---

# Korean Doc Skill

Korean business documents in report-style memo form: fast comprehension, clear judgments, scan-friendly structure. Structure exists to make the document faster to read. If a rule would add bulk without adding scan value, drop the bulk.

**기본 톤은 간결하고 자연스러운 한국어 업무 문어체.** 간결은 빈말·중복·`~입니다` 남발·장황함을 걷어내는 것이지 알맹이·근거·전문성을 줄이는 것이 아니다. 목표는 짧은 문서가 아니라 군더더기 없이 판단과 근거가 드러나는 문서다. 영어는 DAU·API처럼 업계에서 널리 쓰이는 말이나 제품명·식별자에만 사용하고, 한국어로 쉽게 쓸 수 있는 말은 한국어를 우선한다.

**문서 성격에 맞춰 정보 밀도와 격식을 조절한다.** 전략·기획·분석·보고·제안·킥오프도 한국 회사 보고서에서 흔히 쓰는 간결한 보고체가 기본이다. `~한다 / ~이다` 문장이 이어지는 논문식 서술로 격식을 만들지 않는다. 런북·체크리스트·위클리는 같은 원칙을 더 압축해 적용한다.

## When to use

- the draft is too long, too polite, or too explanatory
- the reader must execute, verify, or judge something quickly
- the output goes to a wiki or an internal review
- the user names a document type (`전략 문서`, `PRD처럼`, `위클리`, `런북처럼`) or the source obviously is one. Infer the closest preset from [PRESETS.md](PRESETS.md); exact preset names are not required.

## Core Rules

**1. 독자와 문서 목적을 먼저 정하고 결론부터 쓴다.** 작성 전에 `누가 읽는가`, `읽고 어떤 판단·승인·다음 행동을 해야 하는가`, `이 문서가 보고용인지 실무 검토용인지`를 정한다. 맥락이 분명하면 사용자에게 되묻지 않고 추론한다. 리더·임원용 공유 문서의 본문에는 현황, 사업적 의미, 제안, 결정 필요사항을 우선하고 구현 체크리스트·필드 목록·상세 QA 절차는 그 판단에 직접 필요할 때만 둔다. 첫 화면에서 문서 목적, 주요 판단이나 요청, 다음 행동이 보여야 한다. 기존 문서의 한 장이나 한 절만 고칠 때는 문서 전체에 이미 있는 `목적`·`핵심 요약`을 그 장 안에 다시 만들지 않고, 장의 첫 판단이나 짧은 도입문부터 시작한다.

**2. Length budget. 근거는 남기되 독자의 판단에 필요 없는 세부는 덜어낸다.**

- Label sections (`결론`, `요약`, `주의점`, `요청사항`, `다음 액션` 류): max 3 bullets each. A fourth bullet belongs in a body section or gets cut.
- One bullet = one point. 화면 폭 때문에 줄이 바뀌는 것만으로 나누지 않는다. 독립적인 판단이 둘이면 분리하고, 근거·조건은 필요할 때 하위 불릿으로 내린다.
- Delete any bullet that restates the heading, another bullet, or the section above it.
- 재작성 결과는 사용자가 확장을 요청했거나 빠진 근거를 보완해야 하는 경우가 아니면 원문보다 길어지지 않는 것이 기본이다. 원문 본문과 결과를 비교할 수 있을 때 결과가 서식 차이를 감안해도 약 5% 이상 길어졌다면, 새로 늘어난 블록마다 필요한 이유를 확인하고 이유가 없으면 다시 줄인다. 상세 PRD도 정책·예외·API 필드는 보존하되 설명용 제목과 문장을 새로 보태 분량을 늘리지 않는다. 여러 자료를 합쳐 새 문서를 만들 때는 독자와 문서 목적에 맞는 분량을 먼저 정한다.
- 근거 보존은 모든 세부를 남긴다는 뜻이 아니다. 판단을 뒷받침하는 대표 근거만 남기고, 독자의 판단이나 예상 질문에 쓰이지 않는 세부는 펼치기로 옮기지 말고 제외한다.
- 대표 근거를 고를 때는 `현재 확인된 사실 → 사업에 미치는 영향 → 제안`의 연결이 끊기지 않아야 한다. 수치나 사례를 덜어낼 수는 있지만, 왜 그 제안이 필요한지를 설명하는 사업상 위험·기회까지 삭제하지 않는다.

**3. Sections are a menu, not a template.** Presets list candidate sections; include only the ones the source has real content for. Never fabricate `시사점`, `리스크`, `보고 시 설명 포인트` 류 sections just to look complete. 각 섹션은 서로 다른 독자의 질문에 답해야 하며, 같은 판단·근거·확인사항은 문서 전체에서 한 곳에만 둔다. 다른 섹션에서 다시 필요하면 짧게 연결하거나 해당 위치를 안내한다. 리더·임원용 문서에서 한 장이 하나의 결정이나 논의만 다루면 보이는 판단 단위를 기본 2~3개로 묶는다. 장 안에 별도 요약을 두면 본문과 반복되는 경우에는 요약을 빼고 판단 단위만 남긴다. 구현·권한·QA·지표·운영처럼 담당자는 달라도 같은 결정을 위한 확인사항이면 각각 소제목을 만들지 않는다. Meta sections that describe reading behavior (`먼저 볼 항목`, `읽기 순서`) are banned unless explicitly requested.

**4. Concise report tone.** 기본은 공손체도 논문체도 아닌 간결한 보고체다. `~입니다 / ~합니다 / ~됩니다`뿐 아니라 `~한다 / ~이다 / ~됐다`가 이어지는 긴 서술도 피한다. 판단형 제목 아래에는 핵심 판단·근거·조건·액션을 짧은 문장이나 자연스러운 명사형 종결(`~필요`, `~전제`, `~검토`, `~제안`, `~우선`)로 압축한다. 모든 줄을 기계적으로 `~함`으로 끝내지는 않는다. 원인→해석→판단처럼 문장 간 연결이 필요한 내용만 2문장 이내의 짧은 문단으로 둔다. 구체 명사·동사와 정착된 업무 용어를 쓰고 영어를 남발하지 않는다.

**5. Headings carry the message.** `###` states a judgment, not a topic label (`### 초기 타깃은 반복 고객 관리 업종` not `### 타깃`). If the heading already says it, do not reopen with a bridge sentence; go straight to content.

**6. Bullets for parallel items, prose for connected logic.** 독립적으로 나열 가능한 핵심 판단·수치·근거·조건·리스크·액션이 2개 이상이면 병렬 불릿을 기본으로 한다. 한 문단에 서로 다른 수치·근거·조건·액션이 3개 이상 들어가면 불릿이나 실제 비교표로 바꾼다. 원인→해석→판단처럼 순서가 있는 논리는 2문장 이내의 짧은 문단으로 유지하고 문장별 불릿으로 억지로 쪼개지 않는다. 라벨과 상세는 상위 불릿+하위 불릿 또는 `라벨: 설명` 한 줄로 정리한다. 기본은 2단계까지만 사용한다.

**7. Tables only when they shorten a real comparison.** 실제 열이 있다는 것만으로 표를 만들지 않는다. 독자가 같은 기준으로 선택지·상태·담당·지표를 비교하거나 결정할 때, 문장이나 불릿보다 빨리 읽힐 때만 표를 쓴다. 리더·임원용 문서에서는 반복 필드가 있어도 2~3개 판단으로 충분하면 불릿을 우선한다. `항목 / 설명`이나 `항목 / 판단` 2열 표, 세부 내용을 많이 담기 위한 표, 인접 표와 같은 질문을 반복하는 표는 불릿으로 바꾸거나 합치거나 삭제한다. 반대로 실제 비교는 문장에 묻지 않는다.

**8. Wiki label promotion / H4 위계.** Confluence/wiki에서 `###` 아래가 평면 불릿이라 위계가 안 보이면, 의미 묶음의 첫 라벨 불릿을 `####`로 올려 `###` > `####` > 불릿 3단 구조를 만든다. 단 `####`는 하위 불릿이 2개 이상인 실질 묶음에만 쓰고, 한 포인트짜리는 `####` 대신 라벨 불릿로 둔다. parallel 콘텐츠 항목은 승격하지 않고, 페이지 제목을 본문 최상단 `#`로 반복하지 않는다.

**9. No default `핵심 판단` section.** Use it only when the document is genuinely decision-oriented. Otherwise pick concrete names: `결론`, `요청사항`, `운영 기준`, `남은 이슈`.

**10. Punctuation and formatting.** No trailing period on short lines, labels, table cells, or bullets; periods only for real prose sentences. No em dash; use `:`, parentheses, `.`, `/`, or a nested bullet. Inline code only for real identifiers, commands, or copy-exact values, not for semantics like `세로 -> 가로`.

**11. Long documents.** Explicit numbering when it aids scanning: `A. / A-1.` for narrative memos, `1. / 3-1.` for 검토 자료. Two levels max. Keep revision history and metadata below the real summary. Mark unverified numbers, costs, and legal feasibility as `가정` / `참고용` / `N/A` / `확인 필요` instead of asserting them. 펼치기(expand)는 삭제할 내용을 보관하는 곳이 아니다. 중복·불필요한 세부를 먼저 덜어낸 뒤, 검증이나 질의 대응에 실제로 필요한 근거·계산만 접어 둔다. 리더용 보고에 필요 없는 구현 체크리스트·이벤트/필드 목록·상세 운영 절차는 별도 실무 문서나 부록으로 분리하고, 본문에는 세부 항목을 다시 나열하지 말고 `별도 실무 문서에서 정의`처럼 한 문장이나 링크만 남긴다 (Confluence 적용법은 [REFERENCE.md](REFERENCE.md)).

**12. Preserve source logic** unless the user asks for a report-first rewrite. Preserve the claim and enough evidence to support it, not every heading, table, row, order, or awkward wording. Source-preserving mode에서도 하위 중복을 합치고 독자에게 필요 없는 표시 방식과 세부를 덜어낼 수 있다. Literal translations and unfamiliar jargon never need to be kept.

**13. Choose words by function, not dictionary equivalence.** 영어 단어에 한국어 단어 하나를 고정 대응하지 않는다. 문장에서 실제로 하는 역할을 먼저 확인한 뒤 한국 회사의 회의·보고서에서 쓰는 표현을 고른다. `boundary`는 역할 구분·적용 범위·진입 기준·포함·제외 기준이 될 수 있고, `canonical`이나 `source of truth`는 기준 문서·공식 기록·최신본·원본이 될 수 있다. `경계값`·`보안 경계`도 자동으로 유지하지 않는다. 수치 문맥은 `기준값`·`판정 기준`·`진입 기준`, 보안 문맥은 `보안 적용 범위`·`통제 구간`·`망 분리 구간`처럼 실제 역할에 맞게 바꾼다. 정확한 필드명이나 법령·사내 규정에서 정한 공식 명칭인 경우에만 그대로 쓴다. 자세한 판단 예시는 [EXAMPLES.md](EXAMPLES.md)를 본다.

**14. Do not coin jargon or abbreviations.** DAU·MAU·API·MCP처럼 널리 쓰이는 용어와 제품명·필드명은 유지한다. 통용 여부가 불분명한 약어는 만들지 않는다. 뜻이 불분명한 새 지표명 대신 분자·분모·기간을 그대로 풀어 쓰고, 이름을 붙일 때는 계산값의 의미가 달라지지 않는지 확인한다. 익숙한 표현이 없으면 새 명사를 만들지 말고 한 문장으로 설명한다.

## Modes

| Mode | Meaning |
| --- | --- |
| Source-preserving | Keep facts and logic; retain order where it matters, while removing duplicate or irrelevant presentation detail |
| Light report-style | Keep logic; adapt detail to the reader and decision, add a top summary and clearer headings. Default for `정리해줘 / 다듬어줘` |
| Report-first | Reorder around the decision; strongest top summary |

## Workflow

1. Identify the reader, the judgment/approval/next action, the document type, and whether it is a leadership report or a working document. Load the closest preset from [PRESETS.md](PRESETS.md)
2. Pick a mode (default: light report-style)
3. Map each claim and evidence item to `본문 유지 / 별도 근거·실무 문서 / 삭제`. Give each point one home and merge sections that answer the same reader question
4. Set a visible-body budget before drafting, then restructure the outline. Drop menu sections with no distinct role
5. Convert narrative blocks into a judgment heading + parallel bullets by default. Keep only connected cause-and-effect reasoning as a paragraph of no more than 2 sentences; use a table only when it makes an actual comparison faster
6. Natural-language pass (rules 13, 14): 직역처럼 보이는 명사와 낯선 약어를 표시하고, 문장에서 하는 역할을 확인해 다시 쓴다. 널리 쓰이는 전문 용어와 정확한 식별자는 유지한다
7. Report-style pass (rules 4, 6): 3문장 이상 문단과 반복되는 `~한다 / ~이다 / ~됐다` 종결을 찾는다. 독립적인 판단·수치·근거·조건·액션은 불릿으로 드러내고 연결 논리만 짧은 문단으로 남긴다
8. Audience and duplication pass (rules 1, 3, 7, 11): 이 블록을 빼면 독자의 판단이 달라지는지, 같은 판단이 다른 섹션·표·펼치기에 반복되는지, 표가 실제 비교 시간을 줄이는지 확인한다
9. Density pass (rule 2): 라벨 섹션 3불릿 상한·1불릿 1포인트, 빈말·중복·불필요한 실무 세부 제거. 판단을 뒷받침하는 대표 근거는 유지한다
10. 원문 본문과 결과 분량을 비교한다. 확장 요청이나 빠진 근거 보완 없이 약 5% 이상 길어졌다면 새 제목·연결 문장·중복 설명을 다시 줄인다
11. Run the self-check. For Confluence delivery and page-editing details read [REFERENCE.md](REFERENCE.md); for prefer/avoid samples see [EXAMPLES.md](EXAMPLES.md)

## Self-check

1. 독자와 이 문서를 읽고 내려야 할 판단·승인·다음 행동이 분명한가?
2. 첫 화면에서 문서 목적, 주요 판단이나 요청, 다음 행동이 보이는가?
3. 각 섹션이 서로 다른 질문에 답하며, 같은 판단·근거가 섹션·표·펼치기에 반복되지 않는가? 하나의 결정만 다루는 리더용 장을 여러 실무 소제목으로 쪼개거나, 장 안의 `목적`·`핵심 요약`에서 본문을 미리 반복하지 않았는가?
4. 리더·임원용 본문에 승인 판단과 무관한 구현 체크리스트·필드 목록·상세 QA 절차가 남지 않았는가?
5. 라벨 섹션이 3불릿 이내이며, 한 불릿에 한 포인트만 있고 제목을 되풀이하지 않는가?
6. 대표 근거와 PRD의 필수 정책·예외는 남겼는가? 현재 사실에서 사업상 의미와 제안으로 이어지는 설명이 끊기지 않았는가? 확장 요청 없이 결과가 원문 본문보다 약 5% 이상 길어졌다면 늘어난 이유를 설명할 수 있는가?
7. 제목이 판단을 담고, 각 표가 실제 비교·결정을 더 빠르게 하며, 실제 열이 있다는 이유만으로 만든 표가 없는가?
8. 펼치기에 삭제하거나 별도 실무 문서로 옮겨야 할 내용을 쌓아두지 않았는가?
9. 공손체·기계적 `~함`·긴 `~한다` 서술을 걷어내고, 연결 논리만 2문장 이내의 짧은 문단으로 남겼는가?
10. 동료가 실제 회의에서 쓸 표현인가? 일반 문장에 직역투·통용되지 않는 새 약어가 없고 DAU·API·제품명·필드명은 정확히 유지됐는가?
