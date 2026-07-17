---
name: korean-doc-skill
description: Rewrites Korean business documents for the people who will read, review, or hear them in natural Korean workplace language. Primarily for shared deliverables such as Confluence pages, presentations, and report-ready documents, not ordinary assistant replies, private working notes, progress updates, or files merely because they are Markdown. Preserves exact policies, steps, fields, definitions, and evidence when fidelity matters; surfaces findings in strategy and data analysis; removes repetition and unnecessary explanation without forcing one report format. Use for leadership reports, strategy memos, data analysis, PRDs and policies, runbooks and checklists, weekly updates, knowledge wikis, and data catalogs. Use when Korean docs feel too long, repetitive, translated, table-heavy, or hard to scan, or when the user says 정리해줘 / 다듬어줘 / 보고서처럼 / 번역투 없애줘 / 자연스러운 한국어로.
metadata: {"openclaw":{"homepage":"https://github.com/quanttraderkim/korean-doc-skill", "version": "2.4.0"}}
---

# Korean Doc Skill

Write concise, natural Korean business documents without replacing the document's job with a fixed report template. Structure should help the reader decide, understand, execute, track, or look up information. Treat the requesting user as the author or editor unless they explicitly name themselves as the audience.

## Choose the document job first

Classify the document before rewriting and load the closest section from [PRESETS.md](PRESETS.md).

- **Decide or persuade**: strategy, leadership report, proposal, decision memo
- **Explain evidence**: data analysis, research result, diagnostic report
- **Define**: PRD, policy, service plan, specification
- **Execute or verify**: runbook, checklist, operating guide
- **Track**: weekly update, project board, incident history
- **Look up**: knowledge wiki, reference page, data catalog

If one document mixes jobs, identify the job of each section. Do not force reference, policy, or procedure sections into a decision-report shape.

## Core rules

1. **Separate the author from the audience.** Identify who will actually read, review, or hear the shared document and what they must decide, understand, execute, verify, track, or find. The person requesting the rewrite is usually the author or editor, not the audience. Infer the audience from the destination, page purpose, and surrounding context. Write in the author's document voice; do not address the requester or use assistant handoff phrases such as `요청하신`, `제가 확인한`, `다음으로 진행`, or `필요하시면`.

2. **Separate shared content from working notes.** Keep findings, evidence, decisions, requirements, and limitations that can change the audience's interpretation or action. Exclude AI actions, research steps, files opened, validation commands, revision chatter, and every alternative or uncertainty considered during drafting. Put those in a worklog, handoff, or review record when they need to be retained. When method matters for trust or interpretation, state the analysis scope, source, formula, or validation method as an objective fact instead of a chronological work log. Remove generic defenses such as `자료가 제한적` or `추가 검토 필요`; keep or rewrite them only when they say what is unknown and which conclusion cannot yet be made. PRDs, runbooks, and reference pages may still need implementation constraints, open issues, and exact verification details because their readers use them directly.

3. **Preserve meaning and required detail.** Keep claims and enough evidence to support them. Keep exact policies, exceptions, ordered steps, commands, field names, definitions, denominators, and limitations when the document depends on them. Remove filler, translation-like wording, and detail that serves neither the reader nor the document's use.

4. **Make headings match the section's job.** Strategy and analysis-result sections should surface the finding or implication. Put method, denominator, aggregation conditions, and limitations under the relevant finding unless the document exists to define those items. PRDs, policies, runbooks, checklists, and reference pages may use topic, action, condition, field, or question headings. A heading is useful when readers know what they will get from the section; it does not always need to state a judgment.

5. **Give each point one home.** Treat preset sections as choices, not required slots. Merge sections that answer the same reader question, omit empty sections, and do not repeat a point in a summary, body, table, and appendix. Link or refer back when the same point is needed elsewhere.

6. **Choose prose, bullets, and tables by information shape.** Use prose for connected reasoning, bullets for genuinely parallel items, ordered lists for sequences, and tables for repeated fields or comparisons that are faster to scan row by row. Do not split, merge, promote, or tabulate content only to satisfy a fixed count or hierarchy.

7. **Do not expand without a use.** Rewrites should not grow merely because headings, summaries, or explanation were added. Allow added length when it prevents ambiguity or makes a PRD, runbook, checklist, or reference page safer and easier to use. Judge every added block by reader value, not by a universal percentage.

8. **Use natural Korean workplace language.** Prefer concrete nouns and verbs over abstract evaluation. Avoid long polite prose, mechanical `~함`, repeated `~한다 / ~이다`, literal translations, and invented jargon. Keep widely used terms and exact identifiers such as DAU, API, product names, commands, and field names. If a term is unfamiliar, explain it in a sentence instead of coining a noun or abbreviation. See [EXAMPLES.md](EXAMPLES.md).

## Rewrite modes

| Mode | Use when |
| --- | --- |
| Source-preserving | Fidelity and lookup matter most, especially PRDs, policies, runbooks, specs, and reference pages |
| Light report-style | Logic stays intact but findings, status, or next actions should scan faster, especially analysis and weekly updates |
| Report-first | The reader must make a decision or approve a direction, especially strategy and leadership reports |

Choose the mode from the request and document job; there is no single default for every document type.

## Workflow

1. Identify the author, actual audience, document job, intended use, required facts, and delivery surface
2. Load the closest preset and choose a rewrite mode
3. Mark each source block as `shared content`, `working record`, or `remove`, then mark shared content as `keep`, `merge`, or `move`; preserve required detail before changing the outline
4. Choose each heading's role and the best representation for the content
5. Rewrite in natural Korean, then check facts, terminology, order, and cross-section repetition
6. For Confluence delivery or existing-page edits, read [REFERENCE.md](REFERENCE.md)

## Self-check

1. Is the requesting user treated as the author or editor unless they are explicitly the audience, and can the actual audience use the first screen for the document's job?
2. Are required facts, evidence, policies, exceptions, steps, fields, definitions, denominators, and limitations intact?
3. Does any sentence address the requester, report the AI's work or drafting process, or add a vague caveat that does not change the audience's interpretation or action?
4. Do headings match their section roles without forcing every section into a judgment?
5. Does each point appear once, with no empty template sections or repeated summary/body/table content?
6. Do prose, bullets, ordered steps, tables, numbering, and any appendix make this document easier to use?
7. Is every added block justified, and does the language sound natural in a Korean workplace?
