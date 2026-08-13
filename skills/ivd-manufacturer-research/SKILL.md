---
name: ivd-manufacturer-research
description: Research and write traceable IVD manufacturer cards with strict scope checks, evidence grading, inference ranges, and reusable Obsidian, Excel, or database outputs. Use when investigating an IVD company or diagnostic business, validating vendor revenue and China-market claims, updating a seven-section manufacturer profile, or converting research into structured knowledge-base records.
---

# IVD Manufacturer Research

## Goal

Produce an auditable IVD manufacturer card that separates disclosed facts, reasoned estimates, and analyst judgment. Prefer accuracy and traceability over false precision. Treat every potentially time-sensitive fact as requiring current verification.

## Workflow

1. Define the research subject, cutoff date, reporting currency, and required output format.
2. Run the mandatory scope checks before collecting or calculating figures.
3. Search sources in the required priority order and grade every material claim.
4. Record official facts separately from inferred values.
5. Build estimates from explicit anchors, constraints, and cross-checks; use ranges when exact disclosure is absent.
6. Write the fixed seven-section card.
7. Complete the final quality gate before saving to Obsidian or exporting structured fields.

## Mandatory scope checks

For every material number, label all five dimensions. Do not compare or combine numbers until they align.

| Dimension | Required distinction |
|---|---|
| Geography | Global vs. China |
| Business scope | Group vs. Diagnostics/IVD segment |
| Period | Calendar year vs. fiscal year; note fiscal year-end |
| Metric | Manufacturer revenue vs. end-market size |
| Entity | Parent/group entity vs. subsidiary or product brand |

Also record currency, unit, whether growth is reported or calculated, and whether acquisitions or discontinued operations affect comparability. Mark unresolved scope as `待确认`; do not silently normalize it.

## Source priority and evidence grades

Research in this order:

1. Official annual report, 10-K, 20-F, financial appendix, investor presentation, and earnings call materials.
2. Values that can be directly derived from official disclosures.
3. Multi-constraint industry models supported by several independent anchors.
4. Industry rumor or unsupported market talk.

Assign one evidence grade to every material claim:

- **A — Official direct disclosure:** The exact figure or statement appears in a primary company filing, regulator filing, or official dataset.
- **B — Official derivation:** The value is calculated from official inputs with a reproducible formula and no major hidden assumption.
- **C — Constrained estimate:** The value is modeled from multiple credible anchors and checked against competitors and market capacity; report a range and confidence.
- **D — Unverified signal:** Rumor, single weak secondary source, or claim with unresolved scope. Use only as a lead, clearly label it, and never present it as fact.

When sources conflict, prefer the higher-grade and better-aligned source. Explain material differences rather than averaging them.

## Inference methods

Use at least two independent checks for a material estimate and prefer three or more when the result drives an Insight.

- **Anchors:** Start with disclosed global segment revenue, regional revenue, growth rate, instrument placements, reagent volume, or another directly relevant base.
- **Bounds:** Establish defensible lower and upper limits before choosing a midpoint. Do not report midpoint-only estimates.
- **Regional share:** Apply geography shares only when the region definition and business scope align; treat broad “high-growth markets” as a constraint, not China revenue.
- **Product mix:** Adjust for the target market's actual modality and channel mix. Do not mechanically copy the global product structure into China.
- **Competitor cross-validation:** Compare implied scale, growth, installed base, and share with similarly scoped peers.
- **Market-capacity constraint:** Ensure estimated manufacturer revenue and implied share fit a separately reasoned end-market capacity after accounting for channel layers and pricing.

Write each calculation in this form:

`Result range = anchor × applicable share/ratio × adjustments`

Then list the source for each input, its evidence grade, assumptions, lower/upper cases, sensitivity, and confidence. If the interval remains too wide to support a decision, say so instead of forcing a precise answer.

## Fixed seven-section card

Use these headings in this order:

### 1. 基本信息

State headquarters, founding/background, current reporting entity, business segments, major diagnostic brands, IVD relevance, and the entity used as the card's statistical subject. Explain parent–brand relationships.

### 2. 官方数据（Facts）

Include only grade A facts and simple grade B calculations. Cover the latest comparable period, global group/diagnostic data, officially disclosed geography or China data, and relevant operating indicators. Put the source and scope next to each figure.

### 3. 推导数据（Inference）

Present non-disclosed China or product estimates as ranges. Show formula, anchors, assumptions, constraints, evidence grades, scenarios, confidence, and update date. Keep estimates visibly separate from Facts.

### 4. 产品布局

Map modalities, representative platforms, reagent/consumable model, customer settings, channel model, and position in high-, mid-, or low-throughput segments. Verify current portfolio status.

### 5. 中国战略

Describe localization, manufacturing, R&D, registration, distribution/direct sales, pricing, installed-base or menu strategy, and policy exposure. Separate official statements from interpretation.

### 6. 重大事件

List acquisitions, divestitures, launches, approvals, recalls, management changes, partnerships, investigations, and policy events that materially change scope or outlook. Use event date and source; distinguish announcement from completion.

### 7. 我的判断（Insight）

Synthesize competitive position, growth drivers, risks, uncertainty, and what would change the view. Tie each judgment to preceding Facts or Inference; do not introduce unsupported numbers here.

## Required claim metadata

Every material fact or estimate must make these fields recoverable:

- Source title, publisher, date, and URL or repository path
- Source page, section, or table when available
- Scope: geography, business/entity, period, metric, currency, and unit
- Evidence grade: A/B/C/D
- Formula for derived values
- Assumptions and lower/base/upper cases
- Result range rather than false precision
- Confidence: high, medium, or low, with a short reason
- Last updated date in `YYYY-MM-DD`

Prefer inline citations in Obsidian Markdown and stable source IDs in Excel/database outputs.

## Error traps

Stop and re-check the full calculation when any of these patterns appears:

- **Sysmex:** Converting China revenue reported in JPY at the wrong unit and producing a one-order-of-magnitude error. Verify whether the table uses yen, thousands, millions, or hundred-millions before FX conversion; perform an independent magnitude check.
- **Danaher:** Treating Danaher's total China revenue as China Diagnostics revenue. The group, Diagnostics segment, and brands such as Beckman Coulter, Cepheid, Radiometer, and Leica Biosystems are different scopes.
- **Global-to-China product mix:** Applying the global modality mix directly to China. Rebuild or bound the China mix using local registration, installed base, channel, procurement, and competitor evidence.
- **Roche:** Missing an official Roche China Diagnostics disclosure and replacing it with an estimate. Search company filings, local official releases, investor materials, and archived primary documents before modeling. If official data exists, Facts take precedence over estimates.

These are methodological examples, not permanent factual conclusions. Re-verify the latest primary sources whenever using Roche, Abbott, Danaher, Sysmex, or any other manufacturer; avoid copying old figures from prior cards.

## Output formats

### Obsidian

Create one Markdown file per manufacturer using the fixed seven headings. Preserve source links and add YAML metadata when the vault convention supports it, for example company, aliases, card scope, reporting period, currency, evidence status, and updated date. Follow the existing vault naming and linking rules.

### Excel or database

Keep display text and normalized fields separate. At minimum support:

`manufacturer`, `parent_entity`, `brand`, `section`, `metric`, `value_low`, `value_base`, `value_high`, `currency`, `unit`, `geography`, `business_scope`, `period_start`, `period_end`, `fiscal_calendar`, `metric_scope`, `evidence_grade`, `source_title`, `source_url`, `source_locator`, `formula`, `assumptions`, `confidence`, `updated_at`, `notes`.

Use one row per claim or estimate rather than embedding several incompatible scopes in one cell.

## Final quality gate

Before delivery, verify that:

- All seven sections exist in the required order.
- Facts and Inference are visibly separated.
- Every material number passes all five scope checks.
- Currency conversions show source unit, exchange-rate source/date or policy, and formula.
- Every estimate has anchors, bounds, formula, assumptions, range, confidence, and update date.
- Major estimates have competitor and market-capacity cross-checks.
- Grade D material is not presented as a conclusion.
- Latest primary sources have been re-checked; time-sensitive values are not copied uncritically from examples.
- Obsidian links or spreadsheet/database fields conform to the target repository's existing convention.

If a required item cannot be verified, label it `待确认` and state what source or decision is needed.
