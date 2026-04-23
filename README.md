# marketing-os

A portable marketing operating system for first marketers at B2B companies — built to be used from day one, not after months of setup.

---

## What this is

Most first marketers spend their first 60–90 days rebuilding the same foundations from scratch: ICP docs, positioning frameworks, campaign systems, competitive intel. This repo is that foundation — pre-structured, battle-tested, and designed to be filled in with company-specific data rather than rebuilt every time.

It works across teams. Marketing, sales, product, and engineering can all reference the same source of truth instead of working from different versions of the same deck.

It works across tools. The same markdown files power Claude.ai Projects (chat interface), Claude Code (agentic/automation), and GitHub (browser reading and editing). No duplication, no drift.

---

## What's in here

| Folder | What it contains | Who uses it |
|---|---|---|
| `/frameworks` | Reusable templates: ICP, positioning, campaigns, competitive intel, sales enablement | Everyone |
| `/personas` | AI role prompts: CMO sparring partner, editor, commercial head, fact checker, coach | You (private) |
| `/company-context` | One folder per company: the fill-in doc that makes everything else specific | You + team |
| `/prompts` | Copy-paste Claude prompts for common tasks | Everyone |
| `/guides` | How to use this system across different tools | Everyone |

---

## How to get started at a new company

1. Duplicate `/company-context/TEMPLATE.md` into `/company-context/[company-name]/context.md`
2. Fill it in — takes 30–60 minutes, saves weeks
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

Built by a first marketer, for first marketers — typically joining B2B SaaS or energy/cleantech companies at Series A–C stage where marketing is being built from scratch. Useful for anyone who has to move fast, work cross-functionally, and build systems that outlast them.

---

*This is a living system. Frameworks get updated as you learn. Use Git commit messages as your version log.*
