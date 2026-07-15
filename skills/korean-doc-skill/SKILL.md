---
name: korean-doc-skill
description: Rewrites Korean business documents into structured report-style memos using natural Korean workplace language. Avoids invented jargon and literal translations, keeps widely used terms such as DAU and API, and explains unfamiliar concepts in plain sentences. Conclusion first, judgment-carrying headings, concise sections, and tables only for real comparisons. Use when Korean docs feel too long, too polite, too abstract, translated, or hard to scan. Use when the user says 정리해줘 / 다듬어줘 / 보고서처럼 / 번역투 없애줘 / 자연스러운 한국어로.
metadata: {"openclaw":{"homepage":"https://github.com/quanttraderkim/korean-doc-skill", "version": "2.2.1"}}
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

**1. Lead with the conclusion.** The first screen answers: why this document exists, the main takeaway or request, and the next action. If it cannot, compress before expanding.

**2. Length budget. 군더더기 절제이지 알맹이 축약이 아니다.**

- Label sections (`결론`, `요약`, `주의점`, `요청사항`, `다음 액션` 류): max 3 bullets each. A fourth bullet belongs in a body section or gets cut.
- One bullet = one point. 화면 폭 때문에 줄이 바뀌는 것만으로 나누지 않는다. 독립적인 판단이 둘이면 분리하고, 근거·조건은 필요할 때 하위 불릿으로 내린다.
- Delete any bullet that restates the heading, another bullet, or the section above it.
- 줄여야 할 것은 분량이 아니라 군더더기다. 빈말·중복을 들어내는 게 목표이고, 근거·논리를 채우느라 길어지는 것은 허용된다.

**3. Sections are a menu, not a template.** Presets list candidate sections; include only the ones the source has real content for. Never fabricate `시사점`, `리스크`, `보고 시 설명 포인트` 류 sections just to look complete. Meta sections that describe reading behavior (`먼저 볼 항목`, `읽기 순서`) are banned unless explicitly requested.

**4. Concise report tone.** 기본은 공손체도 논문체도 아닌 간결한 보고체다. `~입니다 / ~합니다 / ~됩니다`뿐 아니라 `~한다 / ~이다 / ~됐다`가 이어지는 긴 서술도 피한다. 판단형 제목 아래에는 핵심 판단·근거·조건·액션을 짧은 문장이나 자연스러운 명사형 종결(`~필요`, `~전제`, `~검토`, `~제안`, `~우선`)로 압축한다. 모든 줄을 기계적으로 `~함`으로 끝내지는 않는다. 원인→해석→판단처럼 문장 간 연결이 필요한 내용만 2문장 이내의 짧은 문단으로 둔다. 구체 명사·동사와 정착된 업무 용어를 쓰고 영어를 남발하지 않는다.

**5. Headings carry the message.** `###` states a judgment, not a topic label (`### 초기 타깃은 반복 고객 관리 업종` not `### 타깃`). If the heading already says it, do not reopen with a bridge sentence; go straight to content.

**6. Bullets for parallel items, prose for connected logic.** 독립적으로 나열 가능한 핵심 판단·수치·근거·조건·리스크·액션이 2개 이상이면 병렬 불릿을 기본으로 한다. 한 문단에 서로 다른 수치·근거·조건·액션이 3개 이상 들어가면 불릿이나 실제 비교표로 바꾼다. 원인→해석→판단처럼 순서가 있는 논리는 2문장 이내의 짧은 문단으로 유지하고 문장별 불릿으로 억지로 쪼개지 않는다. 라벨과 상세는 상위 불릿+하위 불릿 또는 `라벨: 설명` 한 줄로 정리한다. 기본은 2단계까지만 사용한다.

**7. Tables only for real columns.** Comparison, options, status, ownership, metrics, repeated fields. `항목 / 설명` or `항목 / 판단` 2-column content is label-and-detail in disguise: use bullets. The reverse also holds: do not bury a real comparison in prose.

**8. Wiki label promotion / H4 위계.** Confluence/wiki에서 `###` 아래가 평면 불릿이라 위계가 안 보이면, 의미 묶음의 첫 라벨 불릿을 `####`로 올려 `###` > `####` > 불릿 3단 구조를 만든다. 단 `####`는 하위 불릿이 2개 이상인 실질 묶음에만 쓰고, 한 포인트짜리는 `####` 대신 라벨 불릿로 둔다. parallel 콘텐츠 항목은 승격하지 않고, 페이지 제목을 본문 최상단 `#`로 반복하지 않는다.

**9. No default `핵심 판단` section.** Use it only when the document is genuinely decision-oriented. Otherwise pick concrete names: `결론`, `요청사항`, `운영 기준`, `남은 이슈`.

**10. Punctuation and formatting.** No trailing period on short lines, labels, table cells, or bullets; periods only for real prose sentences. No em dash; use `:`, parentheses, `.`, `/`, or a nested bullet. Inline code only for real identifiers, commands, or copy-exact values, not for semantics like `세로 -> 가로`.

**11. Long documents.** Explicit numbering when it aids scanning: `A. / A-1.` for narrative memos, `1. / 3-1.` for 검토 자료. Two levels max. Keep revision history and metadata below the real summary. Mark unverified numbers, costs, and legal feasibility as `가정` / `참고용` / `N/A` / `확인 필요` instead of asserting them. 보고·제안 문서는 본문을 핵심 주장으로 간결히 두고, 상세 근거·배경은 펼치기(expand)로 접어 본문 가독성과 근거 깊이를 동시에 확보한다 (Confluence 적용법은 [REFERENCE.md](REFERENCE.md)).

**12. Preserve source logic** unless the user asks for a report-first rewrite. Preserve the claim and evidence, not awkward wording. Source-preserving mode never requires keeping literal translations or unfamiliar jargon.

**13. Choose words by function, not dictionary equivalence.** 영어 단어에 한국어 단어 하나를 고정 대응하지 않는다. 문장에서 실제로 하는 역할을 먼저 확인한 뒤 한국 회사의 회의·보고서에서 쓰는 표현을 고른다. `boundary`는 역할 구분·적용 범위·진입 기준·포함·제외 기준이 될 수 있고, `canonical`이나 `source of truth`는 기준 문서·공식 기록·최신본·원본이 될 수 있다. `경계값`·`보안 경계`도 자동으로 유지하지 않는다. 수치 문맥은 `기준값`·`판정 기준`·`진입 기준`, 보안 문맥은 `보안 적용 범위`·`통제 구간`·`망 분리 구간`처럼 실제 역할에 맞게 바꾼다. 정확한 필드명이나 법령·사내 규정에서 정한 공식 명칭인 경우에만 그대로 쓴다. 자세한 판단 예시는 [EXAMPLES.md](EXAMPLES.md)를 본다.

**14. Do not coin jargon or abbreviations.** DAU·MAU·API·MCP처럼 널리 쓰이는 용어와 제품명·필드명은 유지한다. 통용 여부가 불분명한 약어는 만들지 않는다. 뜻이 불분명한 새 지표명 대신 분자·분모·기간을 그대로 풀어 쓰고, 이름을 붙일 때는 계산값의 의미가 달라지지 않는지 확인한다. 익숙한 표현이 없으면 새 명사를 만들지 말고 한 문장으로 설명한다.

## Modes

| Mode | Meaning |
| --- | --- |
| Source-preserving | Keep original logic and order; improve wording and structure only |
| Light report-style | Keep logic; add top summary, clearer headings, numbering. Default for `정리해줘 / 다듬어줘` |
| Report-first | Reorder around the decision; strongest top summary |

## Workflow

1. Identify the document type and load its preset from [PRESETS.md](PRESETS.md)
2. Pick a mode (default: light report-style)
3. Restructure the outline first; drop menu sections that have no real content
4. Convert narrative blocks into a judgment heading + parallel bullets by default. Keep only connected cause-and-effect reasoning as a paragraph of no more than 2 sentences; use a table only when columns truly compare
5. Natural-language pass (rules 13, 14): 직역처럼 보이는 명사와 낯선 약어를 표시하고, 문장에서 하는 역할을 확인해 다시 쓴다. 널리 쓰이는 전문 용어와 정확한 식별자는 유지한다
6. Report-style pass (rules 4, 6): 3문장 이상 문단과 반복되는 `~한다 / ~이다 / ~됐다` 종결을 찾는다. 독립적인 판단·수치·근거·조건·액션은 불릿으로 드러내고 연결 논리만 짧은 문단으로 남긴다
7. Density pass (rule 2): 라벨 섹션 3불릿 상한·1불릿 1포인트, 빈말·중복·filler 제거. 단 근거·전문성은 깎지 말 것 (간결 ≠ 알맹이 축약)
8. Run the self-check. For Confluence delivery and page-editing details read [REFERENCE.md](REFERENCE.md); for prefer/avoid samples see [EXAMPLES.md](EXAMPLES.md)

## Self-check

1. First screen shows purpose, takeaway, next action?
2. Any label section over 3 bullets? Any bullet with more than one point? Any restatement bullet?
3. Every section earns its place: nothing scaffolded, no meta sections?
4. 빈말·중복은 줄었나? (근거·전문성을 채우느라 분량이 는 것은 정상)
5. 공손체뿐 아니라 `~한다 / ~이다 / ~됐다`가 이어지는 긴 서술을 걷어냈나? 독립적인 핵심은 불릿으로 드러나고, 연결 논리만 2문장 이내의 짧은 문단으로 남았나?
6. Headings carry judgments? Tables have real comparison columns? Wiki label bullets promoted to `####`, and only those?
7. No em dash, no trailing periods on short lines, no inline code on non-code?
8. 동료가 실제 회의에서 쓸 표현인가? 정확한 필드명·공식 명칭이 아닌 일반 문장에 `경계값`, `보안 경계`, `정본`, `오너`, `드라이버` 같은 직역투가 남지 않았나?
9. 영어 원문 없이도 뜻이 바로 보이는가? 널리 쓰이는 용어·제품명·필드명은 유지하고, 통용되지 않는 새 약어는 만들지 않았나?
