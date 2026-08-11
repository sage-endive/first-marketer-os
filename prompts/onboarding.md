# Onboarding Prompt

> Paste this into Claude (chat or Claude Code) at the start of a new company engagement.
> Replace everything in [brackets] before sending.

---

## Prompt

```
I'm setting up a new marketing foundation for a company. Please read the following two files and confirm you understand the context before we start generating any outputs.

First, the system overview:
[paste contents of CLAUDE.md]

Second, the company context:
[paste contents of /company-context/[company-name]/context.md]

Once you've read both:
1. Summarise the company in 3 sentences — what they do, who they sell to, and at what stage they are
2. List the top 3 things that seem most important to get right for marketing at this company
3. Flag any gaps in the context doc that would limit the quality of marketing outputs

Don't generate any marketing content yet. Just confirm your understanding and flag gaps.
```

---

## What to expect back

Claude should return:
- A tight 3-sentence company summary (a good test of whether the context doc is clear enough)
- 3 prioritised marketing focuses — if these don't match your instincts, update the context doc before proceeding
- A gap list — treat this as your first task list

---

## Next steps after running this

1. Close the gaps Claude flagged (update `/company-context/[company-name]/context.md`)
2. Move to `/prompts/icp-first-pass.md` to generate your first ICP draft
3. Check `/guides/how-to-use.md` for the recommended sequencing
