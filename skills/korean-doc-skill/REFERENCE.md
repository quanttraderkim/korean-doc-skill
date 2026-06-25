# Reference: Confluence / Wiki Delivery

Load this only when the output is bound for Confluence or edits an existing wiki page.

## Page body basics

- Do not repeat the page title as a top-level `#` heading. Confluence renders the title above the body; start with a short lead or the first real section
- Leave blank lines between blocks (heading -> paragraph -> table -> code). Do not stack them densely
- Markdown export can collapse blank lines. If a list glues to the next table or heading, add one short role-setting line (`아래 표는 pool 유형별 상세 우선순위`). Never generic filler; the bridge must state the next block's role
- After export, check rendered block boundaries for list -> table and list -> heading transitions

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
- 핵심 주장·결론은 본문에 펼쳐 두고, 접기(expand)는 상세 근거·배경·계산 과정에 쓴다. 본문 자체를 접기 뒤에 숨기지 말 것. 보고·제안 문서에서 접기는 본문을 핵심 주장으로 간결히 유지하면서 근거 깊이를 함께 제공하는 도구

## 펼치기·이미지·시각화 (conjira markdown round-trip)

conjira의 update-page/create-page는 마크다운을 storage XHTML로 변환한다. 다음 패턴이 round-trip된다.

- 펼치기(expand): `> [!EXPAND] 제목` 한 줄 뒤 인용블록(`>`) 본문 → Confluence expand 매크로로 변환. 핵심 주장은 본문에, 상세 근거·배경·산식은 펼치기로
- 이미지: `![](파일명.png)` → `ri:attachment` 첨부 참조. 먼저 upload-attachment로 같은 파일명을 페이지에 올린 뒤 본문에서 파일명으로 참조. download URL(`![](https://.../download/...)`)은 외부 링크로 박혀 첨부로 안 붙음
- 데이터·현황 문서는 차트·타임라인을 본문에 첨부: 표 나열보다 추세·집중도·단계가 한눈에 들어옴 (seaborn/matplotlib 등으로 생성 후 upload-attachment)
- 한눈 요약(표·차트) + 상세 근거(펼치기)의 균형은 임원·비실무 독자에게 특히 효과적

## Editing existing pages

- Native-managed pages (hand-tuned colors, merged cells, embedded images, smart links, manual layout): prefer storage-aware HTML edits or surgical section updates over a full markdown rewrite, which destroys that polish
- Inline comments are stored as `<ac:inline-comment-marker ac:ref="...">` around the highlighted text in storage XML. A full body overwrite erases the markers and the comments become dangling
- Dangling comments do not auto-reattach, even if the original text and a matching marker reappear. The comment body survives in the sidebar; restoring the anchor is manual UI work
- Before a full overwrite, check for inline comments. If present, warn the user and prefer partial edits: replace one section under a heading, insert after a heading, or append
- If comments are already dangling after an earlier edit, say so plainly and point to the manual recovery path instead of claiming a fix
