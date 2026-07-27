# marketing-os

A portable marketing operating system for first marketers at B2B companies — from discovery to strategy to execution, without starting from scratch.

---

## What this is

Most first marketers spend their first 60–90 days reviewing and rebuilding the foundations from scratch: ICP documentation, positioning frameworks, competitive intel, value propositions, and go-to-market playbooks. This repo is that foundation — pre-structured, battle-tested, and designed to focus your time on curating company-specific data rather than building the architecure.

It works across teams. Marketing, sales, product, and engineering can all reference the same source of truth instead of working from different versions.

It works across tools. The same markdown files power Claude.ai Projects (chat interface), Claude Code (agentic/automation), and GitHub (browser reading and editing). No duplication, no drift.

**Other LLMs and tools** — The framework files are plain markdown and work with any AI tool that accepts context documents or system prompts: ChatGPT (Custom GPTs), Gemini, Cursor, and others. The files are optimised for Claude — `CLAUDE.md` is Claude Code-specific and the persona prompts are written for Claude's behaviour. Minor adjustments to instruction framing may be needed when using other models.

---

## What's in here

| Folder | What it contains | Who uses it |
|---|---|---|
| `/frameworks` | Reusable templates: ICP, positioning, campaigns, competitive intel, sales enablement | Everyone |
| `/prompts` | Copy-paste Claude prompts for common tasks | Everyone |
| `/guides` | How to use this system across different tools | Everyone |
| `/company-context` | One folder per company: the fill-in doc that makes everything else specific | First marketer + team |
| `/personas` | AI role prompts: CMO sparring partner, editor, commercial head, fact checker, coach | First marketer (private) |

---

## How to get started at a new company

1. Duplicate `/company-context/TEMPLATE.md` into `/company-context/[company-name]/context.md`
2. Fill it in — bring together input from subject matter experts and research to build your foundation
3. Open `/guides/how-to-use.md` and follow the surface that fits how you work
4. Run the onboarding prompt in `/prompts/onboarding.md` to orient Claude to your company

---

## How it works across tools

**Claude.ai Projects** — Upload the relevant `.md` files as Project docs. Write a brief system prompt referencing them. Best for daily use, persona invocation, and collaborative work with teammates.

**Claude Code** — Clone the repo locally. `CLAUDE.md` in the root acts as a persistent system prompt for every Claude Code session. Best for generating structured outputs and automation.

**GitHub (browser)** — Every `.md` file renders cleanly in the browser. Use GitHub's web editor for lightweight edits. No setup needed for non-technical teammates.

---

## What stays private

The `/personas` folder and all `/company-context/[company-name]/` folders are excluded from the public version of this repo via `.gitignore`. The TEMPLATE files in each folder are public — they show the structure without exposing any real data.

If you fork this repo, your personas and company data will never accidentally become public as long as you follow the naming convention in `/company-context/`.

---

## Who this is for

Built by a serial first marketer, for first marketers. Originally created with a lens considering B2B SaaS/services and series A-C stage companies, where marketing is being built from scratch. It can be extended to reflect the realities of other environments, such as different industries, life stages, product portfolios, team maturities. Useful for anyone who has to move fast, work cross-functionally, and build systems that outlast them.

---

*This is a living system. Frameworks get updated as you learn. Use Git commit messages as your version log.*
