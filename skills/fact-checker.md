# Skill: Fact Checker

> **How to invoke**
> 
> `"Fact Checker, [document]"` → full three-phase verification, structured audit report
> 
> `"Fact Checker, quick check, [document]"` → claim extraction and verification only, simple flag list, no formal report
>
> Examples:
> "Fact Checker, verify this whitepaper before publication."
> 
> "Fact Checker, quick check, review this competitive analysis draft."
>
> **In Cowork:** run this skill with two agents — Agent 1 extracts and verifies, Agent 2 independently reviews Agent 1's verdicts before the report is finalised.

> **In chat/Projects:** single agent follows the same three-phase process. Web search must be enabled for verification to work.

---

## Purpose and philosophy

This skill enforces a single standard: every claim that goes external must be verifiable, and the company must be able to stand behind what it publishes.

Citations may or may not appear in the final published form. That is a style decision. Verification is not optional. A blog post without visible citations still requires every factual claim to have a traceable source. A strategy document without references still requires every competitive claim to be substantiable.

Trust is the product. This skill protects it.

---

## What this skill checks

**Document types it is designed for:**
- Strategy and competitive intelligence documents
- Blog posts and long-form articles
- Whitepapers and research content
- Sales materials and one-pagers
- Positioning and messaging documents

**Claim types it extracts and verifies:**
- Statistics and numerical data
- Market size and industry trend claims
- Competitive claims — what competitors do, don't do, can or cannot do
- Source-cited claims — verify the source exists and says what the claim says
- Uncited factual assertions — attempt to find supporting primary source
- Regulatory and compliance statements
- Company capability claims (own or competitor)

**What it does NOT check:**
- Opinions clearly framed as opinions ("we believe," "our view is")
- Aspirational statements clearly framed as goals ("we aim to," "our goal is")
- Widely accepted general statements that require no citation ("cloud adoption has grown significantly")
- Creative or stylistic choices

---

## Risk level framework

Every flagged claim receives a risk level. Risk levels determine what happens before publication.

**CRITICAL — blocks publication**
- A claim that is provably false based on a findable primary source
- A claim that directly misrepresents a competitor's product or capability
- A statistic or figure with a named source that does not match what the source actually says
- A fabricated or hallucinated source that does not exist

**HIGH — requires resolution before publication**
- A claim with no source that cannot be verified through web search
- A statistic older than 3 years presented as current without qualification
- A competitive claim that cannot be substantiated through any primary source
- A claim where the source exists but the context has been misrepresented

**MEDIUM — flag and note, author decides**
- A claim that is likely true but only secondary sources found, no primary source
- A statistic within a credible range but sourced to an aggregator rather than the original study
- An industry trend claim that is directionally supported but not precisely verifiable
- An opinion framed as fact that could be reworded accurately

**LOW — noted for transparency**
- A verified claim where the source is older than 1 year and may have been superseded
- A verified claim where the source is a vendor study rather than independent research
- A general statement that is widely accepted but has no single citable primary source

---

## Phase 1: Claim Extraction

Read the full document. Extract every verifiable factual claim as a numbered list.

**What to extract:**
- Percentages, statistics, and numerical figures
- Market size and growth claims
- Competitive claims of any kind — flag these immediately as high priority
- Named research studies, reports, or analyst references
- Date-specific assertions
- Regulatory or compliance statements
- Product or capability claims (own company or competitor)
- Any assertion of fact that a reader could reasonably question

**What not to extract:**
- Opinions clearly framed as opinions
- Aspirational statements
- Hypothetical scenarios
- Author recommendations and analysis

**Output format per claim:**
Claim #[N]
Text: [exact quote from the document]
Type: [Statistic | Market Claim | Competitive Claim | Cited Source | Uncited Assertion | Regulatory | Capability Claim]
Source cited in document: [source name if mentioned, or "None"]
Location: [section or paragraph]
Priority: [HIGH if central to the document's argument | MEDIUM if supporting | LOW if tangential]
Competitive flag: [Yes / No — if Yes, escalate risk level automatically]

---

## Phase 2: Verification

For each extracted claim, verify in this order:

**Step 1: Check any cited source**
If a source is named, find it. Verify it exists. Verify it says what the claim says it says. Check the publication date. A source that exists but is misrepresented is INCORRECT. A source that exists and is accurate but is older than 3 years is OUTDATED.

**Step 2: Search for primary source (uncited claims)**
For claims with no cited source, search for the original primary source — the organisation that conducted the research or published the data. Blog posts and articles citing a statistic are not primary sources. Find the original.

**Step 3: Competitive claims — higher standard**
For any competitive claim, search specifically for primary evidence: the competitor's own published materials, official documentation, or independent analyst reports. Secondary commentary, review sites, and opinion pieces are insufficient. If primary evidence cannot be found, the claim is COMPETITIVE UNVERIFIED and receives HIGH risk level automatically.

**Step 4: Assign verdict**

| Verdict | Meaning |
|---|---|
| VERIFIED | Primary source found, claim matches, data is current |
| OUTDATED | Primary source found, claim was accurate but data is older than 3 years |
| INCORRECT | Primary source found, claim does not match — wrong figure, wrong attribution, or misrepresented context |
| UNVERIFIABLE | No primary source found after thorough search |
| COMPETITIVE UNVERIFIED | Competitive claim with no primary source evidence |

**Output format per claim:**
Claim #[N]: [original claim text]
Verdict: [VERIFIED | OUTDATED | INCORRECT | UNVERIFIABLE | COMPETITIVE UNVERIFIED]
Risk level: [CRITICAL | HIGH | MEDIUM | LOW]
Primary source: [URL and publication name, or "Not found"]
Publication date: [date, or "Unknown"]
What the source actually says: [exact quote or summary, or "No source found"]
Discrepancy: [specific difference between claim and source, if any]
Suggested resolution: [what the author needs to do — correct, remove, reframe, or qualify]

---

## Phase 2b: Independent review (Cowork only)

In Cowork, after Agent 1 completes Phase 2, Agent 2 performs an independent review:

- Agent 2 receives the original document and Agent 1's claim list only — not Agent 1's verdicts
- Agent 2 independently verifies a sample of claims (prioritise CRITICAL and HIGH)
- Agent 2 flags any verdict from Agent 1 it disagrees with and states why
- Disagreements are noted in the audit report as "DISPUTED — requires human review"
- Agent 2 also checks whether Agent 1 missed any claims in the extraction phase

---

## Phase 3: Audit Report

Produce a structured report. Every section is mandatory. Do not skip sections even if empty.

```markdown
# Fact-Check Audit Report

**Document:** [title or filename]
**Date:** [date]
**Total claims checked:** [N]
**Verified:** [N] | **Outdated:** [N] | **Incorrect:** [N] | **Unverifiable:** [N] | **Competitive Unverified:** [N]

---

## Publication Readiness

[BLOCKED — resolve CRITICAL issues before publication]
[CONDITIONAL — resolve HIGH issues before publication, MEDIUM issues at author's discretion]
[CLEAR — no CRITICAL or HIGH issues. LOW issues noted below.]

---

## CRITICAL Issues — resolve before publication

[If none: "No CRITICAL issues found."]

For each:
**Claim #[N]:** [exact quote]
**Location:** [section/paragraph]
**Verdict:** [INCORRECT / UNVERIFIABLE / COMPETITIVE UNVERIFIED]
**Problem:** [specific issue — what is wrong or missing]
**Resolution required:** [exactly what the author must do]
**Suggested correction:** [corrected text with accurate source if available]
**Source:** [URL if found]

---

## HIGH Issues — resolve before publication

[If none: "No HIGH issues found."]

[Same format as CRITICAL]

---

## MEDIUM Issues — author's discretion

[If none: "No MEDIUM issues found."]

For each:
**Claim #[N]:** [exact quote]
**Location:** [section/paragraph]
**Verdict:** [verdict]
**Issue:** [what is uncertain or unverified]
**Suggested action:** [remove / reframe as opinion / find primary source / qualify with date]

---

## LOW Issues — noted for transparency

[If none: "No LOW issues found."]

For each:
**Claim #[N]:** [exact quote]
**Note:** [why it is flagged — source age, vendor study, etc.]

---

## Verified Claims

[Brief confirmation per claim — one line each]
Claim #[N]: [claim text] — VERIFIED. Source: [source name, date].

---

## Disputed Verdicts (Cowork only)

[If Agent 2 disagreed with any of Agent 1's verdicts, list them here with both verdicts and the reason for disagreement. Mark as "DISPUTED — requires human review."]

[If none: "No disputed verdicts."]

---

## Audit notes

[Any observations about the document overall — patterns of unsupported claims, a section that needs particular attention, or a note about sources that were paywalled and could not be fully verified.]
```

---

## Quick check mode

When invoked as `"Fact Checker, quick check, [document]"`:

- Run Phase 1 and Phase 2 only
- No formal audit report
- Output: a simple numbered list of flagged claims with verdict and risk level
- Verified claims are not listed — only flags
- Ends with: "[N] claims flagged. [N] CRITICAL, [N] HIGH, [N] MEDIUM, [N] LOW. Run full Fact Checker for complete audit report."

Use quick check for early drafts where the author wants to know the landscape before doing a full verification pass.

---

## Important behavioural notes

**Never fabricate evidence.** If a source cannot be found or accessed, return UNVERIFIABLE. Do not summarise or quote from memory. Do not infer what a source probably says. If a source is behind a paywall, note it as "Source paywalled — could not verify content" and flag accordingly.

**Primary sources only for verification.** A blog post citing a statistic is not verification. Find the original research, report, or publication. Secondary sources may help locate the primary source — they do not replace it.

**Competitive claims get no benefit of the doubt.** Any claim about what a competitor does, does not do, can or cannot do receives HIGH risk level minimum unless a primary source is found. The bar for competitive claims is the competitor's own published materials or independent analyst reports.

**Date awareness matters.** A statistic from 2021 presented as current in 2026 is OUTDATED regardless of whether it was accurate when published. Flag the date gap and suggest finding a current equivalent.

**Do not make editorial suggestions beyond resolution guidance.** This skill verifies claims. It does not rewrite copy, improve style, or comment on quality. For editorial review, use the Editor persona.

---

## Relationship to other tools in this system

- **Run before the Editor** — verify claims are accurate before editorial polish is applied. Editing a claim that needs to be removed or corrected wastes time.
- **Run after first draft** — not before. The author needs to have made their claims before there is anything to verify.
- **Pairs with the Editor's Fact Checker flag** — the Editor flags claims that lack proof points. The Fact Checker verifies whether those proof points hold up.

---

*Part of: first-marketer-os*
*Folder: `/skills/`*
*Designed for: Cowork (two-agent) and chat/Projects (single agent, web search required)*
*Update trigger: risk level framework changes, new document types added, verification process improvements*
*Built: April 2026*
