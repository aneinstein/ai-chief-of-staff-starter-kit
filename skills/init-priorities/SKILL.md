---
description: Define your strategic focus. Guided conversation to create me/my-priorities.md with what matters most right now. Use /init-priorities when you're ready to clarify your top priorities.
user_invocable: true
---

# Define Your Strategic Focus

You are guiding the user through creating their `me/my-priorities.md` file — the document that keeps their AI focused on what actually matters.

**Tone:** Direct and clarifying. You're helping them think, not just transcribe. Good follow-up questions are more valuable than good templates.

**Golden rule:** Priorities should be specific and honest. "Grow the business" is not a priority — "Close 3 enterprise deals this quarter because we need the revenue to fund the next hire" is.

---

## Step 0: Check context

Read `me/how-i-work.md` if it exists — pain points and role description often hint at priorities.

Read `me/my-priorities.md` if it exists — don't overwrite, build on it.

---

## Step 1: Surface the priorities

Ask: "What are the 3-5 things that only YOU can move forward right now? These aren't your team's goals or your company's OKRs — they're the things that stall if you stop pushing."

Wait for their response.

**If they give vague answers** (like "drive growth" or "improve culture"), ask a follow-up: "What specifically are you doing about that this week? What's the next concrete move?" This usually surfaces the real priority underneath.

**If they give more than 5**, ask: "If you could only focus on 3 of these, which ones would you pick? What would happen to the others?" Help them distinguish between priorities and responsibilities.

---

## Step 2: Go deeper on each priority

For each priority, ask:

"For **[priority name]** — three quick questions:
1. Why does this matter? What happens if it stalls for two weeks?
2. What's your next concrete move this week?
3. Is anyone else helping, or is this all you?"

Wait for their response, then move to the next priority.

---

## Step 3: Ask about the edges

These questions surface context that makes the priority list much more useful:

Ask: "Two more things, if you have a minute:
1. **What are you delegating?** Anything you've handed off but still need to track?
2. **What are you saying no to?** Anything you've deliberately deprioritized that keeps trying to pull you back in?"

Wait for their response. Either or both may be empty — that's fine.

---

## Step 4: Generate `me/my-priorities.md`

Write the file using their actual language:

```markdown
# My Priorities

The 3-5 things that matter most right now. This file tells the AI what to focus on, what to flag, and what to deprioritize.

<!-- Review monthly. If a priority hasn't changed in 6 weeks, ask yourself if it's actually a priority or just a permanent responsibility. -->

---

## [Priority Name]

**What:** [one sentence — their words]
**Why it matters:** [stakes, consequences of stalling]
**Why only me:** [what makes this their problem specifically — if they mentioned it]
**This week's move:** [concrete next action]
**Status:** [on track / needs attention / stalled / blocked — infer from their description]

---

[Repeat for each priority]

---

## What I'm Delegating

[List anything they mentioned handing off, with who owns it]

## What I'm Saying No To

[List anything they're deliberately deprioritizing — this is valuable context for the AI to avoid surfacing irrelevant things]
```

**If delegation or saying-no sections are empty**, include them as empty sections with a comment:
```markdown
## What I'm Delegating
<!-- Nothing tracked yet. Add items here as you delegate — format: what, who owns it, when you expect an update -->
```

---

## Step 5: Update init.md

If `init.md` exists, mark the priorities item as complete:
- Change `- [ ] my-priorities.md — strategic focus (/init-priorities)` to `- [x] my-priorities.md — strategic focus (/init-priorities)`

---

## Step 6: Wrap up

Tell them:
- What you created and where it lives
- How many priorities are in the file
- "Review this monthly — your priorities will shift, and stale priorities make the AI focus on the wrong things."
- Suggest next step based on what's unchecked in `init.md`

Commit: `git add me/my-priorities.md init.md && git commit -m "Add priorities via /init-priorities"`

---

## Important rules

- **Push for specificity.** Vague priorities produce vague AI output. If they say "be a better manager," ask what that means in practice this week.
- **Respect their judgment.** If they say 3 priorities, don't push for 5. If they say 7, gently ask them to rank.
- **Status is a snapshot.** Don't overthink it — "on track" or "needs attention" is enough. This gets updated weekly.
- **The "saying no" section is powerful.** It prevents the AI from surfacing things the user has deliberately deprioritized. Encourage them to fill it in even if it feels uncomfortable.
