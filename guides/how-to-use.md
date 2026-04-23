# How to Use Marketing OS

This guide explains how to use this system depending on how you work. Pick your surface and follow the steps.

---

## Before anything else: fill in the company context

Everything in this system is generic until you fill in `/company-context/[company-name]/context.md`. That file is what makes outputs specific, accurate, and commercially grounded.

**Don't skip this. A half-filled context doc produces half-useful outputs.**

Time to complete: 30–60 minutes.
Who should fill it in: the first marketer, ideally with input from the CEO or a senior commercial person.

---

## Surface 1: Claude.ai Projects (recommended for most people)

Best for: daily use, drafting, reviewing, persona invocation, team collaboration.

**Setup (one time):**
1. Create a new Project in Claude.ai
2. Upload the framework files relevant to your current focus (e.g. `icp-personas.md`, `positioning.md`)
3. Upload your company's `context.md`
4. Write a short system prompt: *"You are working within the marketing-os system. The uploaded files are your source of truth. Always read the company context before generating any output."*

**Daily use:**
- Start a conversation with: *"[Persona name if relevant], here's what I need: [task]"*
- Reference framework files by name: *"Using the ICP framework, draft personas for our Series B deck"*
- Update context: re-upload `context.md` when it changes

---

## Surface 2: Claude Code (for generating structured outputs or automation)

Best for: populating frameworks, batch outputs, working with multiple files at once.

**Setup (one time):**
1. Clone the repo locally: `git clone https://github.com/[you]/marketing-os`
2. Open the repo in your terminal or IDE
3. Run `claude` in the repo root — `CLAUDE.md` loads automatically as context

**Daily use:**
- Claude Code reads your repo files directly — no uploading needed
- Ask it to populate a framework: *"Populate /frameworks/icp-personas.md using the context in /company-context/[company]/context.md"*
- Commit the output: `git add . && git commit -m "ICP v1 — [company name]"`

---

## Surface 3: GitHub in browser (for reading and lightweight editing)

Best for: non-technical teammates who need to read or update docs without any setup.

**To read a file:**
Navigate to the file in GitHub — all `.md` files render as formatted documents.

**To edit a file:**
Click the pencil icon (✏️) in the top right of any file. Edit in the browser. Click "Commit changes" and write a short message describing what you changed and why.

**No setup required. No software to install.**

---

## Recommended sequencing at a new company

| Week | Priority | Files involved |
|---|---|---|
| 1 | Fill in company context | `/company-context/[company]/context.md` |
| 1 | Run onboarding prompt | `/prompts/onboarding.md` |
| 1–2 | Generate ICP first pass | `/frameworks/icp-personas.md` + context |
| 2–3 | Build positioning | `/frameworks/positioning.md` + ICP |
| 3–4 | Map competitive landscape | `/frameworks/competitive-intel.md` |
| 4–6 | Build campaign system | `/frameworks/campaign-system.md` |
| Ongoing | Sales enablement | `/frameworks/sales-enablement.md` |

---

## How to invoke a persona

Personas are defined in `/personas/`. To invoke one, simply name it at the start of your message:

- *"CMO, review this go-to-market strategy"*
- *"Editor, tighten this one-pager"*
- *"Commercial Head, sense-check this campaign budget"*
- *"Fact Checker, review this before it goes to the board"*

Personas are available in Claude.ai Projects (if you've uploaded the persona file) and in Claude Code (they're in the repo).

---

## How to update a framework

1. Open the file (in GitHub browser, locally, or via Claude Code)
2. Make your changes
3. Commit with a message that explains *why* it changed: *"Updated ICP — removed SMB segment after Q2 win/loss review"*

Git keeps every version. You can always go back.

---

## Getting help

If an output doesn't seem right, check:
1. Is the company context complete? Missing fields = generic outputs
2. Is the right framework loaded? Each prompt references specific files
3. Is the persona invoked correctly? Name it explicitly at the start

If you're unsure, run the onboarding prompt again — it will flag gaps.
