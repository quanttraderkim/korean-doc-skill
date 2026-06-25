---
name: korean-doc-skill
description: Rewrites Korean business documents into concise report-style memos. Conclusion first, judgment-carrying headings, bullets under a strict length budget, tables only for real comparisons. Use when Korean docs feel too long, too polite, too abstract, or too hard to scan. Covers strategy memos, business opportunity and market validation docs, upper-planning docs, PRDs, service planning docs, use cases, capability specs, execution guides, runbooks, script usage guides, weekly updates, response memos, issue histories, one-pagers, and hub pages. Use when user says 정리해줘 / 다듬어줘 / 간결하게 / 보고용 메모처럼 / 위키용으로 정리 / 전략 문서로 정리 / PRD처럼 / 위클리 정리 / 런북처럼 / 실행 가이드 / 점검 절차 / 이슈 대응 문서.
homepage: https://github.com/quanttraderkim/korean-doc-skill
user-invocable: true
metadata: {"openclaw":{"homepage":"https://github.com/quanttraderkim/korean-doc-skill"}}
---

# Korean Doc Skill

Korean business documents in report-style memo form: fast comprehension, clear judgments, scan-friendly structure. Structure exists to make the document faster to read. If a rule would add bulk without adding scan value, drop the bulk.

**기본 톤은 간결한 비즈니스 기획서 문어체.** 간결은 빈말·중복·`~입니다` 남발·장황을 걷어내는 것이지 알맹이·근거·전문성을 줄이는 것이 아니다. 목표는 "짧게"가 아니라 "군더더기 없이 dense하게". 비즈 프레임 용어(Top-down, Key Findings, Action-Oriented, 포트폴리오 조정, Quick-win)는 여러 문장을 한 단어로 압축해 간결과 전문성을 동시에 살리는 도구다. 단 영어 용어 남발은 금지(한글 우선, 정착된 용어만). 과도하게 솔직하거나 캐주얼하면 대외 문서에서 프로젝트가 작아 보인다.

**문서 등급으로 톤 강도를 조절한다.** 전략·기획·보고·제안·킥오프는 비즈니스 기획서 문어체로 격상한다. 런북·체크리스트·위클리 같은 순수 실행·상태 공유 문서만 더 압축한 메모체를 유지한다.

## When to use

- the draft is too long, too polite, or too explanatory
- the reader must execute, verify, or judge something quickly
- the output goes to a wiki or an internal review
- the user names a document type (`전략 문서`, `PRD처럼`, `위클리`, `런북처럼`) or the source obviously is one. Infer the closest preset from [PRESETS.md](PRESETS.md); exact preset names are not required.

## Core Rules

**1. Lead with the conclusion.** The first screen answers: why this document exists, the main takeaway or request, and the next action. If it cannot, compress before expanding.

**2. Length budget. 군더더기 절제이지 알맹이 축약이 아니다.**

- Label sections (`결론`, `요약`, `주의점`, `요청사항`, `다음 액션` 류): max 3 bullets each. A fourth bullet belongs in a body section or gets cut.
- One bullet = one line. A bullet that wraps is two thoughts: split it or demote the tail to a child bullet.
- Delete any bullet that restates the heading, another bullet, or the section above it.
- 줄여야 할 것은 분량이 아니라 군더더기다. 빈말·중복을 들어내는 게 목표이고, 근거·논리를 채우느라 길어지는 것은 허용된다.

**3. Sections are a menu, not a template.** Presets list candidate sections; include only the ones the source has real content for. Never fabricate `시사점`, `리스크`, `보고 시 설명 포인트` 류 sections just to look complete. Meta sections that describe reading behavior (`먼저 볼 항목`, `읽기 순서`) are banned unless explicitly requested.

**4. Memo tone.** 빈말과 `~입니다 / ~합니다 / ~됩니다` 남발, 추상적 수식어를 걷어낸다. 기본은 비즈니스 기획서 문어체이고, 명사형 종결(`~필요`, `~전제`, `~검토`, `~제안`, `~우선`)은 강제가 아니라 압축이 필요할 때 쓰는 옵션이다. 구체 명사·동사와 정착된 비즈 용어로 압축한다 (`후속 연락 누락이 거래 누락으로 이어짐`, not `고객 경험을 전략적으로 고도화`). 단 영어 용어 남발은 금지. 문단은 2~4줄.

**5. Headings carry the message.** `###` states a judgment, not a topic label (`### 초기 타깃은 반복 고객 관리 업종` not `### 타깃`). If the heading already says it, do not reopen with a bridge sentence; go straight to content.

**6. Bullets only for parallel items.** Label-and-detail content: parent bullet + child bullets, or a `라벨: 설명` one-liner when the detail fits one short line. Never split one sentence into fake bullets. Two nesting levels by default.

**7. Tables only for real columns.** Comparison, options, status, ownership, metrics, repeated fields. `항목 / 설명` or `항목 / 판단` 2-column content is label-and-detail in disguise: use bullets. The reverse also holds: do not bury a real comparison in prose.

**8. Wiki label promotion / H4 위계.** Confluence/wiki에서 `###` 아래가 평면 불릿이라 위계가 안 보이면, 의미 묶음의 첫 라벨 불릿을 `####`로 올려 `###` > `####` > 불릿 3단 구조를 만든다. 단 `####`는 하위 불릿이 2개 이상인 실질 묶음에만 쓰고, 한 포인트짜리는 `####` 대신 라벨 불릿로 둔다. parallel 콘텐츠 항목은 승격하지 않고, 페이지 제목을 본문 최상단 `#`로 반복하지 않는다.

**9. No default `핵심 판단` section.** Use it only when the document is genuinely decision-oriented. Otherwise pick concrete names: `결론`, `요청사항`, `운영 기준`, `남은 이슈`.

**10. Punctuation and formatting.** No trailing period on short lines, labels, table cells, or bullets; periods only for real prose sentences. No em dash; use `:`, parentheses, `.`, `/`, or a nested bullet. Inline code only for real identifiers, commands, or copy-exact values, not for semantics like `세로 -> 가로`.

**11. Long documents.** Explicit numbering when it aids scanning: `A. / A-1.` for narrative memos, `1. / 3-1.` for 검토 자료. Two levels max. Keep revision history and metadata below the real summary. Mark unverified numbers, costs, and legal feasibility as `가정` / `참고용` / `N/A` / `확인 필요` instead of asserting them. 보고·제안 문서는 본문을 핵심 주장으로 간결히 두고, 상세 근거·배경은 펼치기(expand)로 접어 본문 가독성과 근거 깊이를 동시에 확보한다 (Confluence 적용법은 [REFERENCE.md](REFERENCE.md)).

**12. Preserve source logic** unless the user asks for a report-first rewrite. Add structure first; rewrite substance only when it clearly improves clarity.

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
4. Convert narrative blocks into: judgment heading + short paragraph, nested bullets, or a table only when columns truly compare
5. Density pass (rule 2): 라벨 섹션 3불릿 상한·1불릿 1줄, 빈말·중복·filler 제거. 단 근거·전문성은 깎지 말 것 (간결 ≠ 알맹이 축약)
6. Run the self-check. For Confluence delivery and page-editing details read [REFERENCE.md](REFERENCE.md); for prefer/avoid samples see [EXAMPLES.md](EXAMPLES.md)

## Self-check

1. First screen shows purpose, takeaway, next action?
2. Any label section over 3 bullets? Any bullet over one line? Any restatement bullet?
3. Every section earns its place: nothing scaffolded, no meta sections?
4. 빈말·중복은 줄었나? (근거·전문성을 채우느라 분량이 는 것은 정상)
5. 빈말·`~입니다` 남발은 걷어냈고, 동시에 알맹이·근거·전문성은 살아 있나?
6. Headings carry judgments? Tables have real comparison columns? Wiki label bullets promoted to `####`, and only those?
7. No em dash, no trailing periods on short lines, no inline code on non-code?
