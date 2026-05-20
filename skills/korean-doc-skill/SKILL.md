---
name: korean-doc-skill
description: Use this skill when Korean business documents feel too long, too polite, too abstract, or too hard to scan. Apply it to strategy memos, business opportunity or market validation docs, upper-planning docs, PRDs, service planning docs, capability specs, execution guides, runbooks, script usage guides, weekly updates, one-pagers, and hub pages so they read like concise report-style memos with strong structure, purposeful bullets, tables only where useful, explicit numbering for long docs, and minimal filler.
homepage: https://github.com/quanttraderkim/korean-doc-skill
user-invocable: true
metadata: {"openclaw":{"homepage":"https://github.com/quanttraderkim/korean-doc-skill"}}
---

# Korean Doc Skill

## Overview

Use this skill when the target tone is a Korean business working document rather than an essay. The goal is fast comprehension, clear judgments, and scan-friendly structure.

This file is the canonical skill definition for Codex, Claude, OpenClaw, and other agents that can load a `SKILL.md` file directly.

Typical trigger signals:

- the draft is too long
- the writing is too polite or too explanatory
- the document has long prose but weak structure
- the reader should be able to skim it quickly
- the reader needs to execute, verify, or judge something quickly
- the output will be uploaded to a wiki or shared as an internal review document
- the user says things like `전략 문서로 정리`, `사업 기회 검토처럼`, `상위기획처럼`, `PRD처럼`, `위키 허브처럼`, `위클리처럼`, `이슈 대응 문서처럼`, `실행 가이드처럼`, `점검 절차처럼`, `런북처럼`

You do not need exact preset names from the user. If the user's natural-language intent is clear enough, infer the closest preset and proceed. If the user does not explicitly name the document type but the source itself clearly looks like a strategy memo, PRD, weekly, issue response memo, or hub page, infer from the source and continue.

## Core Rules

Write in short report-style memo Korean. Reduce repetitive `~입니다`, `~합니다`, `~됩니다`. Do not force every sentence into rigid `~함`. Also avoid drifting into long declarative prose such as repeated `~한다`, `~이다`, or `~다` sentence endings. Prefer noun phrases and short judgment-oriented wording such as `~필요`, `~전제`, `~검토`, `~제안`, `~가능`, `~우선`.

Lead with the conclusion. The first visible screen should answer why the document exists, what the main takeaway, request, decision, or next action is, and what needs to happen next.

If the first visible screen cannot answer those questions quickly, compress it first. Prefer a short lead block or bullet hierarchy. Use a table only when the content has real columns to compare or scan.

Top summaries are bullet-first by default. Do not keep or create a table just because it is compact. Use a top-summary table only when repeated columns create real horizontal scan value, such as `대상 / 판단 / 이유 / 다음 액션` or `안 / 장점 / 리스크 / 권고`.

A 2-column top summary such as `항목 / 판단`, `구분 / 내용`, or `항목 / 설명` is usually label-and-detail content disguised as a table. If it has only 3 to 5 rows and no real horizontal comparison, convert it to parent/child bullets:

- `결론`
    - `...`
- `적용 우선순위`
    - `...`
- `주의점`
    - `...`

Keep paragraphs short. Most paragraphs should be 2 to 4 lines. If a paragraph grows longer, split it with a stronger heading, a short list, or a table only when comparison axes are clear.

Use headings to carry meaning. `###` headings should state the message or judgment, not a vague topic label.

Use more visual breathing between sections. Leave clear blank lines after headings and between distinct blocks such as paragraph -> table, table -> bullets, bullets -> code block. If one section contains a summary sentence, a table, and a code sample, do not stack them densely without spacing.

If a heading already states the point, do not reopen the section with another explanatory bridge sentence. Go straight to bullets, a concrete memo line, or a table only when shared columns matter.

For Confluence markdown pipelines, exported markdown may collapse blank lines between adjacent blocks. If a bullet list is followed by a table or the next heading, make the boundary explicit with one short purposeful line only when needed, such as `아래 표는 pool 유형별 상세 우선순위다` or `이 기준을 기본 정책으로 두고, 상세 Flow는 다음 절에서 연결한다`. Do not add generic filler; the bridge must explain the role of the next block.

For longer strategy, planning, or report documents, prefer explicit outline numbering. Use top-level labels such as `A.`, `B.`, `C.` and second-level labels such as `A-1.`, `A-2.` when they materially improve scanability. Avoid going deeper than two levels unless the user explicitly wants a more formal tree.

Use bullets only for parallel items. Do not break a single sentence into fake bullets just to make the page look shorter.

For wiki, research, strategy, and interview-summary notes intended for Confluence or internal sharing, prefer a bullet-first body. After headings, avoid free-floating prose paragraphs unless a short lead sentence is truly needed. Put conclusions, rationale, caveats, signals, and next actions into a clear bullet hierarchy:

- parent bullets: labels or judgment lines such as `결론`, `요청사항`, `근거`, `주의사항`, `다음 액션`
- child bullets: supporting details, examples, constraints, or implications

Do not create a separate `핵심 판단` section by default. Use `핵심 판단` only when the document is explicitly decision-oriented and the source really contains a decision to make. Otherwise choose concrete section names such as `결론`, `이번에 정할 것`, `요청사항`, `운영 기준`, `남은 이슈`, or a message-carrying heading.

Use bullet hierarchy for label-and-detail content. Prefer a parent bullet for the label and child bullets for the explanation instead of a dense `label: explanation` line when the explanation is a full thought:

- `RETS API 부재`
  - `STT/요약 결과를 고객/매물 메모에 자동 적재하는 MVP 구현 난이도 상승`

This also applies to `A. 검토 요약`, `A. 핵심 요약`, and similar first-screen sections. A short summary with labels such as `결론`, `우선순위`, `주의점`, `반영 후보` usually reads better as nested bullets than as a table.

Do not over-nest. Use two levels by default, and add a third level only when it prevents a table cell or paragraph from becoming hard to scan. Keep flat bullets flat when the items are truly parallel.

Use tables for comparisons, metrics, option matrices, ownership, status, and other horizontal scans. Do not use a table just because the section is important or because there are three related ideas. If the content is label + explanation, cause + effect, or sequential reasoning, prefer nested bullets or short paragraphs. This rule does not override the parallel-bullet rule: bullets should group related ideas, not split one sentence into decorative line breaks.

Do not force sentence-final periods onto every short line. In headings, labels, table cells, bullets, one-line judgments, and memo-style fragments, omit the final period by default. Use a period only when writing a full prose sentence with multiple clauses, when two or more sentences appear in one paragraph, or when punctuation materially reduces ambiguity.

If a section starts reading like explanatory narration with many consecutive `~다.` endings, compress it. Convert narrative explanation into a short lead, a bullet hierarchy, or a table only when the reader needs column-by-column comparison.

Avoid conversational bridge sentences such as `이번 건에서 가장 바꿀 가치가 큰 부분은 여기입니다`, `핵심은 ~라는 점입니다`, `즉 ~ 것이 맞습니다` when the same message can be expressed by the heading itself, a tighter table label, or a short memo phrase.

If the output is intended to be pasted into a Confluence page body, do not repeat the page title as a top-level `#` heading. Confluence already renders the page title above the body, so start with a short lead sentence or the first real section.

Avoid meta section names that describe the reader's behavior rather than the document's content. Do not use fixed headings such as `먼저 볼 항목`, `지금 먼저 볼 것`, `읽기 순서`, or `권장 읽기 순서` unless the user explicitly asks for an onboarding guide. Prefer content-bearing headings such as `요약`, `결론`, `요청사항`, `문서 구성`, `주요 문서`, `바로 실행`, or a message-specific heading.

In top-summary sections such as `개요`, keep only the largest changes, purpose, target, or scope. Move edge cases, exception branches, empty-state handling, and implementation detail into lower sections such as `주요 변경 포인트`, `예외`, or `운영 포인트`.

When a top summary table is truly needed, prefer literal functional column labels. When possible, use labels such as `변경 항목`, `정책 적용 지면`, `이번 변경 범위`, `포함 정책 범위`, `유지 정책`, `예외`, `다음 액션` instead of vaguer labels such as `핵심 판단` or `주요 내용` that still require interpretation.

Before making a top summary table, ask whether the reader needs to compare columns horizontally. If each row is just a label plus one judgment line, use nested bullets.

If a label could refer to either the whole document scope or only the current change scope, qualify it explicitly. Prefer `26.4 변경 항목`, `정책 적용 지면`, `이번 현행화 범위`, `포함 정책 범위` over ambiguous shorthand such as `적용 대상` or `적용 범위`.

When the document is mainly about a UI, layout, or visible behavior change, prefer an `AS-IS / TO-BE` visual comparison near the top before detailed prose. For Confluence delivery, favor native-looking links and simple table emphasis when they materially improve scanability.

For short summary tables, definition tables, and policy tables in Confluence, first-column emphasis often improves scanability. If the tool can write Confluence-native table styling or post-edit the rendered page, prefer subtle first-column background shading on label columns such as `항목`, `구분`, `용어`, `화면군`. If the pipeline is markdown-only, treat this as optional post-processing rather than a required output rule.

If a document needs to mark changed rows or changed cells, prefer an explicit version tag such as `26.4 변경` over color alone. Color can support the cue, but the version meaning should remain readable without relying only on color.

Keep terminology aligned between summary tables, policy tables, and definition tables. If the policy table says `미노출`, do not define the same concept separately as `영역 사라짐` unless the distinction is intentional and explained.

For early business opportunity, market validation, partner review, or investment-hypothesis docs, do not overstate uncertain economics, legal feasibility, or operational cost. Separate rough market sizing from confirmed revenue. Mark reference-only scale as `참고용` or `N/A` instead of forcing a revenue estimate. If a cost item is likely negligible because of device capability, existing entitlement, or current free channel, say so plainly and move detailed unit economics to `확인 필요`.

Do not overuse inline code formatting for non-code concepts. Transition labels such as `세로 -> 가로`, `가로 -> 세로`, `popup -> full` are usually document semantics, not code. Reserve inline code for real identifiers, commands, fields, enum-like literals, or values that must be copied exactly.

In Confluence markdown pipelines, inline code around Korean text or identifiers with underscores can export poorly, for example missing spaces around code spans or turning underscores into emphasis. If the exact token does not need to be copied, prefer human-readable labels such as `Rate Card`, `priority override`, `feature scope`, or `campaign id`. If exact field names must be preserved, use a table column or code block that is known to render safely.

If a table cell or policy paragraph contains the default rule, exception handling, and audit/change-history requirement in one sentence, do not compress them together. Prefer a short bullet hierarchy such as `기본 차감 순서`, `예외 처리`, and `변경 이력` so the reader can scan the rule without reparsing the sentence.

When a policy rule is split into bullets and then followed by a table or a new numbered section in Confluence, check the exported markdown or rendered page. If the list appears glued to the following block, insert a short role-setting line before the table or next section instead of relying on blank lines alone.

When editing an existing Confluence page that already contains native formatting such as row-header first columns, colored change markers, merged cells, embedded images, or other hand-tuned visual polish, do not assume a full markdown rewrite is safe. Prefer a storage-aware HTML edit or a surgical section update so that existing formatting is preserved.

Use tables when the reader needs comparison, categorization, ownership, tradeoffs, options, targets, state transitions, or metric/status scanning.

Before creating a table, check whether each column has a distinct scanning purpose. If the table would become `항목 / 설명` only, prefer parent bullets with child bullets. Do not leave real comparison logic buried in prose, but do not turn simple explanation into a table.

If the table is only `항목 / 판단` and appears at the top of the document, be even stricter. `결론`, `적용 우선순위`, `주의점`, and `문서 반영 후보` are labels, not comparison axes; render them as bullets unless there is a third column that adds repeatable scan value.

Preserve the source logic unless the user explicitly asks for a report-first rewrite. Add structure first. Rewrite substance only when it materially improves clarity.

When documenting writing rules or guidance, avoid dense narrative explanation. Prefer short labeled blocks such as `A. 기본 방향`, `B. 문체`, `C. 구조`, `D. 표/불릿/제목`.

For long planning or policy documents, do not place document history, revision logs, ticket references, or guide metadata above the real summary. Show purpose, main takeaway, and requested action first, then place metadata below if needed.

Avoid em dash (`—`) as a mid-sentence separator. Korean business memos rarely use it, and it can read as a foreign habit in internal docs. Replace with one of: colon (`:`) for label and explanation, parentheses for parenthetical context, period to split into two sentences, slash (`/`) for parallel alternatives, or a nested bullet with 4-space indent for longer elaborations. If a single line reads like `X — Y`, first consider whether `Y` belongs as a sub-bullet under `X` instead.

## Rewrite Modes

Choose one mode first.

| Mode | Meaning | When to use |
| --- | --- | --- |
| Source-preserving rewrite | Keep the original logic and section order as much as possible. Improve wording and structure only. | The draft already has the right substance but reads poorly. |
| Light report-style rewrite | Keep the original logic, but add top summary, clearer headings, tables, or numbering where helpful. | The draft needs to be more readable for sharing or review. |
| Report-first rewrite | Reorder the document for decision support. Add stronger top summary and re-sequence sections around judgment. | The audience wants quick decision support, not source-faithful reading. |

If the user does not specify a mode, default to source-preserving rewrite plus structure improvement.

In practice, most users will not name the mode explicitly. If the user says `정리해줘`, `다듬어줘`, `위키용으로 다시 써줘`, or similar, default to `light report-style` unless source fidelity is clearly more important.

Natural-language shortcuts:

- `전략 문서`, `방향성 검토`, `논의 안` -> `Strategy Memo`
- `사업 기회 검토`, `시장 검증`, `파트너 연계 검토`, `사업성 검토`, `MVP 사업 검토` -> `Business Opportunity / Market Validation`
- `상위기획`, `연간 계획`, `컨셉 기획` -> `Upper Planning / Concept Planning`
- `상세기획`, `PRD`, `기획서` -> `PRD / Service Planning Doc`
- `유즈케이스`, `직군별 시나리오` -> `Use Case / Vertical Workflow Doc`
- `허브 문서`, `인덱스 페이지`, `문서 모음 소개` -> `Hub / Index Page`
- `위클리`, `주간 업데이트` -> 기본은 `Weekly Update`
- `상태판이 큰 위클리`, `보드형 위클리`, `큰 상태판 위클리`, `분기 보드` -> `Team Weekly Board` 변형
- `이슈 대응 문서`, `Q&A 대응`, `답변 정리` -> `Response Memo`
- `이슈 히스토리`, `장애 이력`, `대응 이력` -> `Issue History / Incident Log`
- `실행 가이드`, `점검 절차`, `런북`, `운영 가이드`, `스크립트 사용법`, `체크리스트` -> `Execution Guide / Runbook / Script Usage Guide`

## Default Tone

Prefer concrete nouns and verbs over abstract modifiers. Aim for report-style memo wording that sounds like an internal decision document, not an essay, not a telegraphic note dump, and not a textbook-style `~한다` narrative.

Prefer:

- `초기 도입은 A안 우선`
- `후속 연락 누락이 거래 누락으로 이어짐`
- `무료 유저 수익화는 필요하나 총매출 임팩트는 제한적`
- `초기 타깃은 반복 고객 관리 업종`

Avoid:

- `고객 경험을 보다 전략적으로 고도화할 수 있음`
- `본질적으로 중요한 의미를 갖는다고 판단됨`
- `결과적으로 여러 측면에서 유의미한 효과 기대 가능`
- `이 기능은 고객관리에 중요한 역할을 한다`
- `이번 건에서 가장 바꿀 가치가 큰 부분은 여기입니다`
- `핵심은 문제 발생 시 누가 얼마나 빨리 대응할 수 있나라는 점입니다`

Prefer replacing those bridge sentences with tighter forms such as:

- `우선 전환 대상은 전면 / 보상형 / 보상형 전면 preload API`
- `판단 기준은 대응 속도와 운영 단순화`
- `포맷별 preload 전환 우선순위는 대응 속도 기준으로 정리`

## Structural Defaults

Unless the user asks otherwise, start from this order and rename sections to match the source:

1. `목적`
2. `핵심 요약`
3. main analysis, decision, request, or operating-standard sections
4. `리스크 / 전제 / 고려사항`
5. `시사점 / 다음 액션 / R&R`

For long documents, add an executive-summary block near the top when it genuinely helps the reader. This can be bullets, short labeled lines, or a table. Do not default to a table.

For strategy memos, use-case docs, and hub pages, make the first screen compact, but choose bullets over tables when the content is not truly comparative.

For long documents, numbered section labels are often worth adding directly in headings. Preserve the existing numbering style when it works. Use `1.`, `2.`, `3-1.` for business review or Confluence working docs that read like internal 검토 자료. Use `A.`, `A-1.` when the document is closer to a narrative memo or strategy note.

When the document is a hub or index page, optimize for navigation first. The reader should understand what this document set is, where to start, and which child documents matter without reading long prose.

## Document-Type Presets

### Strategy Memo

Recommended structure:

- `목적`
- `핵심 요약`
- `왜 중요한가`
- `판단 / 방향`
- `근거`
- `리스크/전제`
- `시사점`

Rules:

- Put the judgment in headings
- Use a comparison table near the top only when the memo compares options, targets, tradeoffs, or criteria
- Use lists for reasons, risks, or evidence only
- Avoid essay-style narration
- If the first screen does not show `왜 중요한가 / 판단 또는 방향 / 시사점`, compress before expanding
- If the source is option-heavy, show `권고안`, `비교 기준`, and `요청사항` on the first screen before detailed evidence
- For option-comparison memos, use one compact comparison table and push detailed financial or operational backup below

### Upper Planning / Concept Planning

Recommended structure:

- `목적`
- `핵심 요약`
- `왜 지금`
- `방향`
- `우선순위`
- `1차 범위`
- `후속 상세기획 연결`
- `리스크 / 전제`

Rules:

- Treat this as a direction-setting document, not a full execution plan
- The first screen should show `방향 / 우선순위 / 1차 범위 / 결정 필요사항`
- Use summary bullets near the top by default; use tables only when comparing options, scope, or ownership
- Compress execution detail, long history tables, and metadata unless they change the current judgment
- If execution detail must remain, push it below the direction-setting sections
- Distinguish clearly between `방향`, `우선순위`, and `후속 상세기획에서 풀 내용`

### Business Opportunity / Market Validation

Recommended structure:

- `추진 목적 및 사업 비전`
- `타겟 시장 및 매출 풀 검토`
- `시장 니즈 및 자사 경쟁력`
- `MVP 방향성 및 유저 시나리오`
- `사업 모델 및 과금 구조 검토`
- `법무/개인정보보호 및 권한 공유 설계`
- `확인 필요 사항`
- `참고 문서`

Rules:

- Treat this as a working 검토 문서, not an executive recommendation memo. Do not force a separate `핵심 요약` or `핵심 판단` section unless the user asks for decision material.
- The first screen should show what opportunity is being verified, with whom, for which first market, and what expansion model is being tested.
- Prefer `추진 목적 및 사업 비전` with a one-line proposition, then bullets for `단기 목적`, `장기 목적`, and `핵심 방향`.
- Use business-specific section names over generic consulting labels. Prefer `타겟 시장 및 매출 풀 검토`, `시장 니즈 및 자사 경쟁력`, `MVP 방향성`, `과금 구조`, `확인 필요 사항`.
- Use tables for real repeated fields: market phase / target / size / revenue pool / note, field need / current problem / asset or solution, AS-IS / TO-BE, priority / feature / rationale, cost item / review point / note.
- Use nested bullets for R&R, sales message, charging flow, legal/privacy assumptions, and partner responsibilities when each role needs sub-detail.
- For priority tables in Confluence, status labels such as `핵심`, `추가`, and `가드레일` are useful when they separate MVP core, expansion, and risk-control items.
- Distinguish rough assumptions from confirmed facts. Use wording such as `가정`, `MAX`, `참고용`, `N/A`, `재검토`, and `확인 필요` when the number is directional.
- Do not invent detailed unit economics too early. Keep early cost sections to cost-item identification, ARPU floor, and margin-risk checks. Remove or down-rank speculative cost lines that are likely negligible or already covered by device capability or existing free channels.
- For legal/privacy-sensitive flows, state that the section is a planning assumption and requires legal/privacy review before application. Put automatic collection, employee-phone sharing, consent, retention, deletion, access logs, and advertising-message risk into explicit guardrails.
- Keep references and linked child pages at the bottom unless a linked page is required to understand the current decision.

### PRD / Service Planning Doc

Recommended structure:

- `목적`
- `배경`
- `문제 정의`
- `목표`
- `범위`
- `주요 사용자 흐름`
- `정책/예외`
- `리스크`
- `오픈 이슈`

Rules:

- Prefer explicit scope boundaries
- Use tables for requirements, scenarios, dependencies, or metrics when multiple rows share fields
- Put unresolved items in a separate section instead of burying them in prose
- For long planning docs, show `결론 또는 방향 / 범위 / 범위 제외 또는 후속 / 오픈 이슈` near the top
- If policy, exception, storage, upload, or lifecycle rules are mixed together, split them into labeled bullets or tables according to whether the reader needs vertical explanation or horizontal comparison
- When a source contains large mapping tables, keep the original detail but add a compact orientation block first. Use bullets if the orientation is just label + explanation; use a table if it compares repeated fields.
- If the document is policy-heavy, prefer `활성화 조건 → 생성/저장 → 예외 다운로드 → 업로드/리마인드 → 미노출/파기/삭제 → 오픈 이슈` ordering
- For policy-heavy planning docs, separate data principles, exception rules, and deletion/retention rules into grouped bullets or tables before narrative explanation
- Move revision history or operational metadata below the top summary unless the history itself is the subject

### Skill Spec / Capability Spec

Recommended structure:

- `한 줄 정의`
- `언제 쓰는가`
- `입력`
- `출력`
- `핵심 동작`
- `예외/금지`
- `평가 기준`

Rules:

- Keep definitions literal
- Prefer small examples over long explanation
- Avoid marketing language

### Report / Decision Material

Recommended structure:

- `목적`
- `핵심 요약`
- `주요 판단`
- `옵션 비교`
- `리스크`
- `일정/R&R`

Rules:

- Put summary first
- Use tables for options, impact, and ownership only when multiple rows share the same comparison columns
- Use collapsed detail only for backup material, not for the main argument

### Execution Guide / Runbook / Script Usage Guide

Recommended structure:

- `실행 요약`
- `바로 실행`
- `판정 기준`
- `결과 확인`
- `권한 제한 시 수동 확인`
- `주의사항`

Rules:

- Treat this as an execution-support document, not a narrative explanation
- Put the final artifact, final file, final column, or final judgment point on the first screen
- If the reader only needs one file, one command, or one result field, state that explicitly near the top
- Show the shortest successful execution path before detailed explanation
- Prefer compact bullets for short guidance. Use tables for `입력값`, `생성 파일`, `판정 기준`, `수동 확인 경로` only when there are multiple comparable items.
- When permission issues or environment limits are likely, add a separate fallback section instead of mixing it into the main flow
- This is not a live tracking board unless the document is continuously updated for status monitoring
- For CloudShell, console, script, or operational check docs, prefer `A. 실행 요약 -> B. 바로 실행 -> C. 판정 기준 -> D. 결과 확인 -> E. 권한 제한 시 수동 확인` ordering

### Weekly Update

Recommended structure:

- `이번 주 핵심 변화`
- `진행 현황`
- `이슈 / 리스크`
- `다음 주 계획`
- `지원 필요사항`

Rules:

- Keep it short enough to skim in one screen per section
- Prefer status tables over long progress prose only when status, owner, date, and next action need to be scanned together
- Separate done, blocked, next clearly
- Treat this as the default weekly preset
- Use this preset for short weekly summaries and dashboard-style updates
- Put `이번 주 핵심 변화 / 핵심 To-Do / 리스크` on the first screen before detailed tables
- If the source already has a stable project table, keep it below a compact executive summary instead of flattening it into prose
- Remove empty template rows, duplicated section blocks, and obvious system noise before polishing

### Team Weekly Board (Experimental)

Recommended structure:

- `이번 주 핵심 신호`
- `주요 공유 / 결정 필요`
- `핵심 To-Do`
- `포트폴리오 보드`
- `리스크 / 지원 요청`
- `참고 링크 / 부록`

Rules:

- Use this when the source is still a weekly-family document but the main body is a large board-heavy status page
- Keep one compact executive summary above the main board
- Preserve the board shape; do not rewrite the whole page into narrative summary
- Remove template noise, duplicated sections, and system metadata leaking into titles or cells
- If `전주 진행 / 금주 계획 / 장기 목표` are mixed in one cell, split them before polishing
- Keep the first screen meeting-friendly: top signals, decisions needed, and next actions first

### Decision One-Pager

Recommended structure:

- `목적`
- `추천안`
- `선택지 비교`
- `리스크 / 전제`
- `요청 결정사항`

Rules:

- Put the recommended option near the top
- Keep the document tight
- Use one main comparison table only when there are multiple options with shared criteria
- Avoid background history unless it changes the decision

### Use Case / Vertical Workflow Doc

Recommended structure:

- `한 줄 정의`
- `왜 이 직군 / 상황이 중요한가`
- `대표 장면 / 상황`
- `AI가 해야 하는 동작`
- `사용자 가치`
- `기본 기능`
- `사용자 설정값`
- `제한 / 금지`

Rules:

- Explain the situation as `상황 -> 동작 -> 가치` rather than loose description
- Use short scene-oriented headings
- Prefer a short bullet summary near the top for `핵심 가치 / 대표 장면 / 피해야 할 포지션`; use a table only when comparing multiple use cases
- Avoid turning the whole document into narrative explanation
- If multiple use cases exist, separate them as parallel blocks with the same shape
- If representative scenes are more than two, present them as repeated fixed blocks or a table when the same fields repeat

### Hub / Index Page

Recommended structure:

- `한 줄 정의`
- `왜 이 문서 묶음을 보는가`
- `현재 핵심 문서`
- `문서 구조 / 카테고리`
- `기본 원칙`

Rules:

- Optimize for navigation, not persuasion
- Keep the top area short and high-signal
- Use grouped bullets by default to show category purpose and representative documents. Use tables only when categories must be scanned across the same fields.
- Avoid repeating the same document list in multiple formats unless each list serves a different reading path
- First screen should show what the document set is for, which documents are current/core, and how the categories are organized before longer explanation

### Tracking / Ops Board (Experimental)

Recommended structure:

- `현재 상태`
- `이번 주 핵심 변화`
- `주요 이슈 / 리스크`
- `트래킹 항목`
- `다음 액션`
- `지원 필요사항`

Rules:

- Optimize for live tracking, not persuasive narrative
- Put status, owner, next action, and timing in tables when those fields repeat across multiple items
- Keep dated updates compact; do not let them drift into diary-style prose
- Separate `현재 상태`, `결정 필요`, and `참고 메모` clearly
- Use stable status labels such as `진행 중`, `대기`, `완료`, `리스크`
- If the page mixes agenda, tracking, and memo content, split them into separate labeled sections before polishing
- Use this preset for open issue boards, check-needed pages, and active coordination pages
- Keep unresolved items and resolved history in separate sections, grouped bullets, or tables according to scan needs
- If the source is mainly a chronological closed-issue log, do not force this shape; treat it as an issue history / incident log candidate instead

### Issue History / Incident Log (Experimental)

Recommended structure:

- `문서 범위`
- `최근 핵심 이슈`
- `이슈 / 사건 인덱스`
- `사건별 기록`
- `공통 패턴 / 재발 방지`
- `참고 링크`

Rules:

- Use this for accumulated issue history, known-issue memory, incident chronology, and response-history pages
- Optimize for reference and recall, not for live tracking
- Keep chronology and incident boundaries explicit
- For each incident, prefer a repeated fixed shape such as `이슈 내용 / 원인 / 영향 / 조치 / 후속`
- Put one compact index or summary block near the top before long historical detail. Use bullets when the index is short; use a table when the same fields repeat across incidents.
- Separate active unresolved tracking from closed historical record
- If the source is mainly a live open-issue board, use `Tracking / Ops Board` instead

### Response Memo (Experimental)

Recommended structure:

- `목적`
- `핵심 입장`
- `주요 질문 / 이슈`
- `권고 답변 / 모범 답변`
- `리스크 / 확인 필요사항`
- `요청사항 / 다음 액션`

Rules:

- Use this for PR response prep, executive Q&A prep, external inquiry 대응, and sensitive issue explanation memos
- Put the official stance or recommended answer on the first screen
- Separate `공식 답변`, `내부 판단`, `미확정 사항`, and `추가 확인 필요` clearly
- Prefer tables for `질문 / 답변 / 리스크 / 상태 / 담당` only when multiple questions share those fields
- If the source is mainly a day-by-day 대응 연표, treat it as `Issue History / Incident Log` instead of forcing a response-memo shape

## Hard Don’ts

Do not write long introductory filler before the real point.

Do not use bullet points to simulate paragraph breaks.

Do not hide comparisons, category roles, or reading order inside prose when a small table would show them faster.

Do not turn short summaries, label-and-detail notes, or two to three related ideas into tables when nested bullets would read more naturally.

Do not repeat `핵심 판단` as a default section title across documents. Reserve it for real decision material.

Do not merge default policy, exception policy, override behavior, and change-history/audit requirements into one sentence.

Do not use inline code in Confluence-bound prose when it breaks spacing or underscores; choose readable policy labels instead.

Do not repeat the same judgment in slightly different wording.

Do not add summary language unless it actually summarizes something.

Do not replace a concrete claim with an abstract phrase.

Do not put document history, revision logs, or metadata tables above the key summary in long planning or concept documents.

Do not hide the main body behind collapsed sections unless the user explicitly wants a report-first summary page.

Do not turn every sentence into rigid `~함` style. The target tone is concise internal memo/report wording, not forced shorthand.

Do not let the document slide into long `~한다` explanation mode. Declarative sentences are allowed when needed, but they should not dominate the page.

Do not write style guidance as dense narrative paragraphs when a short labeled checklist would communicate faster.

Do not use em dash (`—`) as a mid-sentence separator. Replace with `:`, `(...)`, `.`, `/`, or a nested bullet.

## Micro Examples

### Headings

Prefer:

- `### 무료 유저 수익화는 필요하나 총매출 임팩트는 제한적`
- `### 초기 도입 타깃은 반복 고객 관리 업종이 적절`

Avoid:

- `### 사업성`
- `### 타깃`

### Bullets

Good:

- `후속 연락 누락`
- `재방문 고객 관리 부재`
- `매출 회수 근거 약함`

Bad:

- `고객 관리가 중요함`
- `그래서 이 기능이 필요함`

The bad example is not parallel information. It should be a short paragraph or heading-level judgment instead.

### Tone

Prefer:

- `초기 타깃은 반복 고객 관리 업종`
- `추천 자동화보다 기억 복원과 후속 관리가 핵심`
- `규제 리스크로 자동 권유 포지션은 비적합`

Avoid:

- `이 기능은 특정 직군에게 중요한 가치를 제공한다`
- `이 서비스는 고객관리에 매우 유용한 역할을 한다`

### Punctuation

Prefer:

- `완료 조건은 케이스별 상이 (각 섹션 참조)`
- `기본: 총 예산 내 분배`
- `방향성만. 세부는 미정`

Avoid:

- `완료 조건은 케이스별 상이 — 각 섹션 참조`
- `기본 — 총 예산 내 분배`
- `방향성만 — 세부는 미정`

Em dash in Korean memos tends to read as translated English. Colon, parentheses, period, slash, and nested bullets cover the same roles more naturally.

### Tables

Use tables for:

- option comparison
- target segment comparison
- ownership / R&R
- repeated status, metric, policy, or question fields

Do not use tables for:

- one short claim
- one example sentence
- label + explanation content
- sequential reasoning
- two or three related bullets without shared columns
- a paragraph that reads naturally without comparison

## Rewrite Workflow

When using this skill:

1. Identify the document type first.
2. Decide whether the task is source-preserving rewrite, light report-style rewrite, or report-first rewrite.
3. Restructure the outline before rewriting sentences.
4. Convert long narrative blocks into one of:
   - a stronger heading plus short paragraph
   - nested bullets for label + explanation or cause + effect
   - a summary table only when shared columns make the scan faster
   - a true parallel bullet list
5. If the output is guidance, checklist, or a hub page, prefer grouped rule blocks over essay-style explanation.
6. Cut filler and abstract phrases last.

If unsure, prefer source-preserving rewrite plus structure improvement over aggressive summarization.

## Editing Existing Confluence Pages

When updating a page that already carries reader feedback, preserve collaborative context where possible.

### Check for Inline Comments Before a Full Body Rewrite

- Inline comments (sidebar comments anchored to a specific text span) are stored in Confluence storage XML as `<ac:inline-comment-marker ac:ref="...">selected text</ac:inline-comment-marker>` around the highlighted text.
- A full body overwrite (replacing the entire page body via markdown or HTML) erases those markers. The comments then fall into a "dangling" state, detached from the body.
- Before a full body overwrite, check whether the page has inline comments. If it does, warn the user and consider partial edits first.

### Prefer Partial Edits When Comments Exist

- Replace a single section under a heading, insert content after a heading, or append rather than overwriting the whole body, so that comment anchors elsewhere in the page survive.
- Only fall back to full body overwrite when the change spans most of the page and after confirming the user is willing to lose existing inline comment anchors.

### Dangling Comments Do Not Auto-Reattach

- Confluence Server / Data Center does not re-attach a dangling inline comment even if the original text and a matching `ac:ref` marker reappear later. The server tracks the dangling state as a property of the comment itself.
- The comment body is not lost. It remains accessible through the page's comment sidebar or dangling area. Recovery of the inline anchor requires a human to resolve the old comment and re-create it in the UI at the new location. Tools cannot reliably re-attach.

### When In Doubt

- Ask the user before a destructive overwrite.
- If comments are already dangling after an earlier edit, be transparent: explain the limitation and suggest the manual UI recovery path rather than claiming a fix.

## Self-check Before Finalizing

Before returning the final draft, check:

1. Does the first visible screen show the purpose and main takeaway, request, or next action?
2. Are `~입니다 / ~합니다 / ~됩니다` still overused?
3. Has the draft drifted into long `~한다` narrative explanation?
4. Are bullets used only for real parallel items?
5. Are tables used only where shared columns, comparison, status, ownership, metrics, or policy fields matter?
6. Would explicit `A. / A-1.` or `1. / 3-1.` numbering improve scanability while preserving the document's natural style?
7. Are the headings carrying actual messages?
8. Is any paragraph still too long and better split?
9. Is any em dash (`—`) used where a colon, parentheses, period, slash, or nested bullet would read more naturally?
10. Did the draft avoid creating a `핵심 판단` section unless the document is explicitly decision-oriented?
11. Are default rules, exceptions, overrides, and change-history requirements separated into bullets when they appear together?
12. Would Confluence markdown preserve inline code and underscores correctly, or should those tokens be written as readable labels?
13. If a Confluence bullet list is followed by a table or the next heading, is the boundary still clear after export/rendering?
14. Did any top summary table collapse into simple `label + judgment` rows that should be nested bullets instead?
15. Did the draft avoid meta headings such as `먼저 볼 항목`, `지금 먼저 볼 것`, `읽기 순서`, or `권장 읽기 순서` unless explicitly requested?
