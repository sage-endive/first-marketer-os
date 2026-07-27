# CLAUDE.md — First Marketer OS

This file is read automatically by Claude Code at the start of every session in this repo. It tells you what this repo is, how it's structured, and how to behave when working with it.

---

## What this repo is

A portable marketing operating system for first marketers at B2B companies. It contains reusable frameworks, AI persona definitions, company-specific context, and ready-to-use prompts.

The person using this repo is typically the first or only marketer at a company — working cross-functionally with sales, product, and engineering. They move fast. They need outputs that are commercially grounded, not just well-written.

---

## Repo structure

```
/frameworks       Reusable templates — the portable spine. These travel across companies.
/prompts          Copy-paste prompts for common tasks across surfaces.
/guides           Usage documentation for different tools and audiences.
/company-context  One subfolder per company. Contains context.md with all company-specific data.
/personas         AI role definitions — private, not committed publicly.
```

---

## How to orient to a company

Before generating any output, always check whether a `/company-context/[company-name]/context.md` exists. If it does, read it first. It contains:
- Company name, industry, stage
- ICP summary
- Product/service description
- GTM motion
- Key differentiators
- Tone-of-voice guidelines
- Competitors
- What this company is NOT

If no context file exists, ask which company to work with or whether to create one from the template.

---

## How to use the frameworks

Each file in `/frameworks` is a structured template with two parts:
1. The framework itself — headers, sections, fields to fill in
2. A `## How to use this with Claude` section at the bottom — a prompt you can run to generate a first-pass output for a specific company

When filling in a framework for a company, always load the relevant `context.md` first. The framework fields are designed to be populated from it.

---

## Personas

Files in `/personas` define AI roles: sparring partners when one is needed but there's no time from the actual person in the seat or no actual person exists. Examples are CMO, editor, commercial head, fact checker, management coach. When a persona is invoked by name, adopt that role's defined behaviour, tone, and focus. Persona files specify exactly how each role behaves.

The coach persona is permanently private and should never be referenced in shared or public outputs.

---

## Behavioural defaults for this repo

- **Audience**: Outputs may be read by non-marketers (engineers, product managers, sales). Avoid jargon without explanation. Annotate structure when it would help a non-specialist understand why a section exists.
- **Commercial grounding**: Always connect marketing outputs to pipeline, revenue, or commercial outcomes where relevant. This is a B2B context.
- **Brevity over completeness**: A tight, usable first draft beats an exhaustive one. Flag gaps rather than padding.
- **Ask before assuming**: If company context is missing or ambiguous, ask one specific question rather than inferring and potentially going in the wrong direction.
- **Commit messages**: When committing changes, write messages that describe *why* something changed, not just what. E.g. "Updated ICP after Q2 win/loss review" not "Updated icp-personas.md".

---

## What not to do

- Do not fabricate company-specific data if no context file exists
- Do not use generic B2C marketing language or consumer framing
- Do not produce outputs longer than needed — this system is for people who are time-constrained
- Do not treat framework templates as finished outputs — they are structures to populate, not copy to reuse verbatim
