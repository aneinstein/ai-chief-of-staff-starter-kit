---
description: Build your relationship map. Guided conversation to create me/my-team.md with the people you work with most. Use /init-team when you're ready to teach your AI about your team.
user_invocable: true
---

# Build Your Relationship Map

You are guiding the user through creating their `me/my-team.md` file — the relationship map that helps their AI understand who they work with and how.

**Tone:** Conversational, curious, non-judgmental. You're helping them articulate things they already know but haven't written down.

**Golden rule:** Use their words. If they say "he's kind of a pain but brilliant," write that — don't sanitize it to "strong-willed collaborator."

---

## Step 0: Check context

Read `me/how-i-work.md` if it exists — it may mention people, meeting patterns, or team size that gives you a head start.

Read `me/my-team.md` if it exists — they may have started manually. Don't overwrite existing entries. Add to them.

---

## Step 1: Get the list

Ask: "Who are the 5-8 people you meet with most often? Just names and a quick label — like 'Sarah, my manager' or 'Dev, peer on the product team.' We'll go deeper on each one."

Wait for their response.

---

## Step 2: Walk through each person

For each person they listed, ask these questions **as a group** (not one at a time — that would take forever for 5-8 people):

"Let's start with **[Name]**. Quick round:
1. What's your relationship? (direct report, manager, peer, stakeholder, external partner, etc.)
2. What do you typically talk about in your meetings?
3. What do you wish you remembered or prepared before meeting with them?
4. Any patterns or friction worth noting? (Things that come up repeatedly, communication style quirks, etc.)"

Wait for their response, then move to the next person.

**Pacing:** Do 2-3 people, then check in: "Want to keep going with the rest, or is this enough to start?" Some users will want to do all 8, others will want to start with 3 and add more later. Both are fine.

---

## Step 3: Generate `me/my-team.md`

Write the file using their actual descriptions. Structure:

```markdown
# My Team

The people I work with regularly. This file helps the AI prep for meetings, draft messages, and understand relationship dynamics.

<!-- Update this file when relationships change, new people join, or you notice patterns worth capturing. The weekly review is a good time to check if anything here is stale. -->

## Relationship Types

How I categorize the people I work with:
[List the relationship types that came up naturally — direct reports, manager, peers, stakeholders, external, etc. Only include types they actually have.]

---

## [Person Name]

**Relationship:** [type]
**What we talk about:** [their description]
**What to remember before meetings:** [their answer to question 3]
**Patterns and notes:** [their answer to question 4, if any]

---

[Repeat for each person]
```

**Formatting notes:**
- Use `---` between people for visual separation
- Keep entries short — 4-6 lines each. This is a reference doc, not a biography.
- If they mentioned a meeting cadence ("we meet every Tuesday"), include it
- If they didn't answer a question, skip that field. Don't fill in placeholders.

---

## Step 4: Update init.md

If `init.md` exists, mark the team item as complete:
- Change `- [ ] my-team.md — relationship map (/init-team)` to `- [x] my-team.md — relationship map (/init-team)`

---

## Step 5: Wrap up

Tell them:
- What you created and where it lives
- How many people are in the file
- "You can add more people anytime by editing `me/my-team.md` directly, or run `/init-team` again to add more through conversation."
- Suggest next step based on what's unchecked in `init.md`

Commit: `git add me/my-team.md init.md && git commit -m "Add relationship map via /init-team"`

---

## Important rules

- **Wait for answers.** Don't generate fictional entries.
- **Use their words.** Especially for patterns and friction — these are the most valuable parts and the most personal.
- **Don't push for completeness.** 3 well-described people is better than 8 shallow entries. They can always come back.
- **Don't judge.** If they say "my manager micromanages and it drives me crazy," that's useful context. Write it down.
