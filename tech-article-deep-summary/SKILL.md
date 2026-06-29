---
name: tech-article-deep-summary
description: "Deeply summarize and explain technology articles, AI/agent essays, product announcements, engineering blogs, research explainers, and Lark/web/PDF articles. Use when the user provides one or more technology articles and wants a reusable high-readability summary with original-source verification, article structure, key mechanisms, diagrams, writing style extraction, and practical takeaways."
---

# Tech Article Deep Summary

## Goal

Turn a technology article into a reliable, readable analysis report. Do not only translate or paraphrase. Preserve source facts, reconstruct the argument, explain mechanisms, separate source claims from interpretation, and surface practical implications.

Default to Chinese. Start with the conclusion, then show evidence, structure, and next-level details.

## Source Handling

1. Read every source the user provides.
2. If a secondary article cites an original, read the original too.
3. Record title, publisher, author if available, publish date, URL or document token, and whether each source is primary or secondary.
4. Separate three layers:
   - **原文事实**: directly supported by the original article.
   - **二次整理**: structure, labels, or tables added by the reference article.
   - **我的推断**: inferred implications; mark them explicitly.
5. If source access fails, say exactly which source was not verified.

## Reading Spine

Identify the article's spine before writing:

- **Thesis**: the one-sentence answer to "这篇文章到底想让读者相信什么".
- **Trigger**: why this article exists now, such as a launch, trend, internal practice, new model, incident, or engineering constraint.
- **Object**: product, system, method, architecture, team practice, or research finding.
- **Mechanism**: how it works, what components interact, what workflow it changes.
- **Boundary**: permissions, risks, cost, privacy, quality, limitations, or governance.
- **Evidence**: dates, numbers, examples, user stories, internal practice, benchmarks, or quoted claims.
- **Implication**: what changes for builders, teams, users, or organizations.

## Report Template

Use this outline by default. Merge or delete sections that do not fit.

1. **一句话结论**
   - State the core claim in one concise paragraph.
   - Add one line on why it matters.

2. **资料卡**
   - Title, source, date, author, article type, topic, related products/projects, and source reliability.

3. **原文写作主线**
   - Explain the author's sequence: problem -> concept -> evidence -> mechanism -> practice -> conclusion.
   - For secondary articles, note what they added beyond the original.

4. **方法与限制**
   - For research papers, reverse-engineering posts, benchmark reports, or investigative articles, identify the method, dataset/snapshot, evidence tiers, and limitations.
   - State whether the source is official documentation, source-code analysis, benchmark evidence, user report, or author inference.

5. **核心要点完整拆解**
   - Use sections for the 3-6 most important ideas.
   - For each idea, answer: "是什么", "怎么工作", "为什么重要", "边界是什么".

6. **机制/架构/流程**
   - Reconstruct data flow, control flow, human workflow, team workflow, agent loop, lifecycle, or governance loop.
   - Prefer concrete nouns over abstract slogans.

7. **关键证据**
   - List numbers, dates, product names, model names, availability, migration paths, examples, and caveats.
   - Keep exact names and terms unchanged.
   - Mark what each evidence item supports: thesis, mechanism, limitation, comparison, or implication.

8. **反向校验**
   - Name the strongest boundary conditions, missing evidence, or counterexamples that could weaken the article's main claim.
   - Do this even when the article is persuasive; it keeps the summary from becoming advocacy.

9. **绘图设计**
   - Include diagrams when they reduce cognitive load.
   - Use one focused diagram for a hard concept and one overview diagram for the whole system when useful.

10. **写作手法**
   - Extract the article's reusable structure, rhythm, tables, examples, metaphors, and conclusion style.

11. **实践启示**
   - Convert the article into action points, checklists, design principles, or questions a team can use.

12. **可复用总结模板**
   - End with a short template or checklist if the user wants to reuse the approach.

## Technology Article Patterns

Use the matching pattern as the backbone:

- **Product announcement**: definition -> launch context -> users -> core capabilities -> setup path -> governance/cost/privacy -> migration/availability -> ecosystem position.
- **Engineering architecture**: problem -> constraints -> architecture -> control/data flow -> tradeoffs -> failure modes -> verification -> rollout.
- **AI/agent practice**: old workflow -> new collaboration model -> agent capabilities -> human roles -> trust/verification -> operating checklist.
- **Research explainer**: question -> method -> evidence tier -> result -> limitation -> counterevidence -> implication.
- **Incident or postmortem**: impact -> timeline -> root cause -> contributing factors -> fix -> prevention -> lessons.

## Long Article Compression

For long papers or multi-section reports:

1. First pass: capture the abstract, introduction, conclusion, tables/figures, and section headings.
2. Second pass: select at most 5-7 load-bearing claims; drop decorative examples.
3. Keep named mechanisms, numbers, constraints, comparisons, and limitations.
4. Collapse repeated evidence into one table instead of repeating paragraphs.
5. If the source has many subsystems, group them by design question rather than source order.
6. Say what was not fully read if only the abstract, HTML, or selected sections were available.

## Diagram Rules

Choose diagrams by the concept being explained:

- **Actor/role map**: humans, agents, tools, data sources, reviewers, admins.
- **Flow diagram**: request -> planning -> execution -> verification -> human review -> learning.
- **Boundary diagram**: permissions, memory scope, data scope, security boundary, private vs shared channels.
- **Matrix/table**: old vs new, capability vs governance, risk vs mitigation, role vs tool.
- **Dependency stack**: prerequisite capabilities -> practices -> outcomes.

Drawing conventions:

- Boxes: actors, components, tools, products, roles.
- Cylinders: memory, datasets, documents, state, logs.
- Solid arrows: work flow, delegation, data access, task handoff.
- Dotted arrows: constraints, isolation, governance, replacement, verification.
- Keep labels short and readable.
- In Feishu/Lark documents, use `lark-whiteboard`; do not use Mermaid diagrams in the document.
- In ordinary chat, either provide a concise diagram plan or a Markdown/Mermaid sketch if the interface supports it.

## Writing Rules

- Lead with the conclusion; avoid suspense.
- Prefer tables for dense facts and comparisons.
- Prefer bullets for behavior and mechanisms.
- Use short quotes only when exact wording matters.
- Do not overstate unsupported claims.
- Call out what is original-source fact versus added analysis.
- Translate important terms once, then keep the original term in parentheses if it will recur.
- Explain why each detail matters to builders or decision makers.

## Calibrated Examples

The skill is calibrated on two Anthropic-style article pairs:

- **Claude Tag product announcement**: a launch article works best when summarized as product definition, availability, capability pillars, Slack workflow, access control, spend/audit governance, migration path, internal usage data, and ecosystem position.
- **Building effective human-agent teams**: an operating-principles article works best when summarized as paradigm shift, prerequisites, lessons, practical checklist, hidden bottleneck, trust-building loop, and organizational implications.

The shared pattern is: make facts scannable first, then explain the system-level meaning behind them.
