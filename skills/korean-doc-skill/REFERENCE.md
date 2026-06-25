# Reference: Confluence / Wiki Delivery

Load this only when the output is bound for Confluence or edits an existing wiki page.

## Page body basics

- Do not repeat the page title as a top-level `#` heading. Confluence renders the title above the body; start with a short lead or the first real section
- Leave blank lines between blocks (heading -> paragraph -> table -> code). Do not stack them densely
- Markdown export can collapse blank lines. If a list glues to the next table or heading, add one short role-setting line (`아래 표는 pool 유형별 상세 우선순위`). Never generic filler; the bridge must state the next block's role
- After export, check rendered block boundaries for list -> table and list -> heading transitions

## Expanded Blocks and Visualizations (펼치기와 시각화)

- 임원 보고나 킥오프 등 비즈니스 기획서에서는 본문에 핵심만 간결하게 두고, "왜/상세 근거"는 펼치기로 접어 스캔 효율성과 정보의 깊이를 양립시킨다.
- Confluence/Jira 호환성을 위해 펼치기는 `> [!EXPAND] 제목` Markdown 블록을 사용한다.
- 데이터·수치를 보여주는 문서는 차트, 타임라인 등의 시각화 자료를 첨부하여 스캔을 돕는다.
- 이미지는 반드시 `![](파일명)` 문법을 사용해야 한다 (일반 URL 링크 문법을 쓰면 Confluence에서 attachment로 붙지 않음).

## Inline code and identifiers

- Inline code around Korean text or underscore identifiers can export poorly: missing spaces around code spans, underscores turning into emphasis
- If the token does not need to be copied exactly, use readable labels (`Rate Card`, `priority override`, `campaign id`)
- Exact field names that must be preserved go in a table column or a code block that renders safely

## Table conventions

- Column labels: literal and functional (`변경 항목`, `이번 변경 범위`, `유지 정책`, `예외`, `다음 액션`) over labels that need interpretation (`핵심 판단`, `주요 내용`)
- Qualify scope-ambiguous labels: `26.4 변경 항목`, `이번 현행화 범위`, not bare `적용 대상`
- Keep terminology aligned across summary, policy, and definition tables. One concept, one term: if the policy table says `미노출`, do not define it elsewhere as `영역 사라짐`
- Mark changed rows or cells with an explicit version tag (`26.4 변경`) rather than color alone; color may support the cue but must not carry the meaning
- First-column background shading on label columns (`항목`, `구분`, `용어`) improves scanability when the tool can write native styling; in markdown-only pipelines treat it as optional post-processing
- Do not hide the main body behind collapsed sections; collapse is for backup material only

## Editing existing pages

- Native-managed pages (hand-tuned colors, merged cells, embedded images, smart links, manual layout): prefer storage-aware HTML edits or surgical section updates over a full markdown rewrite, which destroys that polish
- Inline comments are stored as `<ac:inline-comment-marker ac:ref="...">` around the highlighted text in storage XML. A full body overwrite erases the markers and the comments become dangling
- Dangling comments do not auto-reattach, even if the original text and a matching marker reappear. The comment body survives in the sidebar; restoring the anchor is manual UI work
- Before a full overwrite, check for inline comments. If present, warn the user and prefer partial edits: replace one section under a heading, insert after a heading, or append
- If comments are already dangling after an earlier edit, say so plainly and point to the manual recovery path instead of claiming a fix
