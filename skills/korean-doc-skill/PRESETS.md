# Document-Type Presets

Structures below are menus of candidate sections, not mandatory templates. Include a section only when the source has real content for it (SKILL.md rule 3). Rename sections to match the source's own vocabulary.

## Natural-language mapping

- `전략 문서`, `방향성 검토`, `논의 안` -> Strategy Memo
- `추진 보고`, `킥오프`, `경영진 보고` -> Executive Kickoff / 추진 보고
- `사업 기회 검토`, `시장 검증`, `파트너 연계 검토`, `사업성 검토`, `MVP 사업 검토` -> Business Opportunity / Market Validation
- `상위기획`, `연간 계획`, `컨셉 기획` -> Upper Planning / Concept Planning
- `상세기획`, `PRD`, `기획서` -> PRD / Service Planning Doc
- `유즈케이스`, `직군별 시나리오` -> Use Case / Vertical Workflow Doc
- `허브 문서`, `인덱스 페이지`, `문서 모음 소개` -> Hub / Index Page
- `위클리`, `주간 업데이트` -> Weekly Update. 상태판이 큰 보드형이면 Team Weekly Board
- `이슈 대응 문서`, `Q&A 대응`, `답변 정리` -> Response Memo
- `이슈 히스토리`, `장애 이력`, `대응 이력` -> Issue History / Incident Log
- `실행 가이드`, `점검 절차`, `런북`, `운영 가이드`, `스크립트 사용법`, `체크리스트` -> Execution Guide / Runbook

## Structural default (no preset matched)

1. `목적`
2. `핵심 요약`
3. main analysis, decision, or request sections
4. `리스크 / 전제`
5. `다음 액션 / R&R`

Top summaries are bullet-first. Keep `개요`-type sections to the largest changes, purpose, and scope; push edge cases and implementation detail into body sections.

## Executive Kickoff / 추진 보고

Structure: `핵심 요약 (Executive Summary)` / `추진 개요 (목적·범위)` / `추진 계획·일정` / `진행 현황·Key Findings` / `Next Step·핵심 원칙`

- Top summary explicitly structured in an Executive Summary box.
- Ensure the 'Ask' (목적: 합의, 결정 등) is clearly stated for upcoming reviews.
- Timelines and stages should be visualized (e.g., Markdown images `![](...)` or tables) to aid rapid scanning.

## Strategy Memo

Structure: `목적` / `핵심 요약` / `왜 중요한가` / `판단 / 방향` / `근거` / `리스크 / 전제` / `시사점`

- Judgment in headings; first screen shows 왜 중요한가 + 판단 + 시사점
- Option-heavy memos: `권고안`, `비교 기준`, `요청사항` on the first screen, one compact comparison table, detailed financial or operational backup below

## Upper Planning / Concept Planning

Structure: `목적` / `핵심 요약` / `왜 지금` / `방향` / `우선순위` / `1차 범위` / `후속 상세기획 연결` / `리스크 / 전제`

- Direction-setting document, not an execution plan: first screen shows 방향 / 우선순위 / 1차 범위 / 결정 필요사항
- Push execution detail and long history below; distinguish 방향 vs 우선순위 vs 후속 상세기획에서 풀 내용

## Business Opportunity / Market Validation

Structure: `추진 목적 및 사업 비전` / `타겟 시장 및 매출 풀 검토` / `시장 니즈 및 자사 경쟁력` / `MVP 방향성 및 유저 시나리오` / `사업 모델 및 과금 구조 검토` / `법무/개인정보보호` / `확인 필요 사항` / `참고 문서`

- Working 검토 문서, not an executive memo: no forced `핵심 요약` or `핵심 판단`
- First screen: what opportunity is being verified, with whom, for which first market, and what expansion model
- Distinguish assumptions from facts: `가정`, `MAX`, `참고용`, `N/A`, `확인 필요`. Rough market sizing is not confirmed revenue
- No premature unit economics: keep cost sections to cost-item identification, ARPU floor, margin risk. Likely-negligible cost lines (device capability, existing entitlement, free channel) get said plainly and move to `확인 필요`
- Legal/privacy flows are planning assumptions pending review. Automatic collection, consent, retention, deletion, access logs, advertising-message risk as explicit guardrails
- Tables for repeated fields: market phase / target / size / revenue pool, AS-IS / TO-BE, priority / feature / rationale. Status labels `핵심` / `추가` / `가드레일` work for priority tables

## PRD / Service Planning Doc

Structure: `목적` / `배경` / `문제 정의` / `목표` / `범위` / `주요 사용자 흐름` / `정책/예외` / `리스크` / `오픈 이슈`

- Explicit scope boundaries; unresolved items in their own section; top shows 방향 / 범위 / 범위 제외 / 오픈 이슈
- Policy-heavy docs: split 기본 규칙 / 예외 / override / 변경 이력 into grouped bullets or tables, never one sentence. Lifecycle ordering helps: 활성화 조건 -> 생성/저장 -> 예외 -> 업로드/리마인드 -> 미노출/파기 -> 오픈 이슈
- UI, layout, or visible behavior changes: AS-IS / TO-BE comparison near the top
- Large mapping tables: keep the original detail, add a compact orientation block first
- Revision history below the top summary

## Skill Spec / Capability Spec

Structure: `한 줄 정의` / `언제 쓰는가` / `입력` / `출력` / `핵심 동작` / `예외/금지` / `평가 기준`

- Literal definitions, small examples over long explanation, no marketing language
- Writing-rule or guidance docs: short labeled blocks (`A. 기본 방향`, `B. 문체`) over narrative paragraphs

## Report / Decision Material

Structure: `목적` / `핵심 요약` / `주요 판단` / `옵션 비교` / `리스크` / `일정/R&R`

- Summary first; collapsed detail only for backup material, never the main argument

## Execution Guide / Runbook / Script Usage Guide

Structure: `실행 요약` / `바로 실행` / `판정 기준` / `결과 확인` / `권한 제한 시 수동 확인` / `주의사항`

- Execution support, not narrative: the final artifact, file, column, or judgment point goes on the first screen
- Shortest successful path first. If the reader needs only one file, one command, or one result field, say so explicitly near the top
- Permission or environment fallbacks in their own section, not mixed into the main flow
- CloudShell, console, script, or operational check docs: `A. 실행 요약 -> B. 바로 실행 -> C. 판정 기준 -> D. 결과 확인 -> E. 수동 확인` ordering

## Weekly Update

Structure: `이번 주 핵심 변화` / `진행 현황` / `이슈 / 리스크` / `다음 주 계획` / `지원 필요사항`

- Default weekly preset: one screen per section, done / blocked / next clearly separated
- First screen: 핵심 변화 / 핵심 To-Do / 리스크 before detail tables
- Keep a stable project table below a compact summary; delete empty template rows and system noise first

## Team Weekly Board

Structure: `이번 주 핵심 신호` / `주요 공유 / 결정 필요` / `핵심 To-Do` / `포트폴리오 보드` / `리스크 / 지원 요청` / `참고 링크 / 부록`

- For board-heavy weekly pages: one compact executive summary above the board, preserve the board shape
- Split mixed cells (전주 진행 / 금주 계획 / 장기 목표) before polishing; keep the first screen meeting-friendly

## Decision One-Pager

Structure: `목적` / `추천안` / `선택지 비교` / `리스크 / 전제` / `요청 결정사항`

- Recommended option near the top; one comparison table only when options share criteria; background history only if it changes the decision

## Use Case / Vertical Workflow Doc

Structure: `한 줄 정의` / `왜 이 직군 / 상황` / `대표 장면` / `AI가 해야 하는 동작` / `사용자 가치` / `기본 기능` / `사용자 설정값` / `제한 / 금지`

- `상황 -> 동작 -> 가치` framing with scene-oriented headings
- Multiple use cases: parallel blocks of the same shape. Three or more scenes with repeated fields: fixed blocks or a table

## Hub / Index Page

Structure: `한 줄 정의` / `왜 이 문서 묶음` / `현재 핵심 문서` / `문서 구조 / 카테고리` / `기본 원칙`

- Navigation first: the top shows what the set is, which documents are core, and how categories are organized
- Grouped bullets by default; do not repeat the same document list in multiple formats

## Tracking / Ops Board

Structure: `현재 상태` / `이번 주 핵심 변화` / `주요 이슈 / 리스크` / `트래킹 항목` / `다음 액션` / `지원 필요사항`

- Live tracking: status, owner, next action, timing in tables when those fields repeat. Stable labels: `진행 중`, `대기`, `완료`, `리스크`
- Separate 현재 상태 / 결정 필요 / 참고 메모; keep unresolved items apart from resolved history
- Mostly a chronological closed-issue log: use Issue History / Incident Log instead

## Issue History / Incident Log

Structure: `문서 범위` / `최근 핵심 이슈` / `이슈 인덱스` / `사건별 기록` / `공통 패턴 / 재발 방지` / `참고 링크`

- Reference and recall, not live tracking; explicit incident boundaries and chronology
- Fixed shape per incident: `이슈 내용 / 원인 / 영향 / 조치 / 후속`. Compact index near the top
- Mostly a live open-issue board: use Tracking / Ops Board instead

## Response Memo

Structure: `목적` / `핵심 입장` / `주요 질문 / 이슈` / `권고 답변` / `리스크 / 확인 필요사항` / `요청사항 / 다음 액션`

- PR response, executive Q&A, external inquiry prep: official stance or recommended answer on the first screen
- Separate 공식 답변 / 내부 판단 / 미확정 사항 / 추가 확인 필요. Question tables only when 질문 / 답변 / 리스크 / 담당 repeat across items
- Mostly a day-by-day 대응 연표: use Issue History / Incident Log instead
