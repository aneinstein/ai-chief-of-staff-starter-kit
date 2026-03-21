---
description: Set up your weekly review skill. Walks you through customizing the example weekly review for your rhythm and reflection style. Use /init-weekly-review when you're ready to set up your anchor habit.
user_invocable: true
---

# Set Up Your Weekly Review

You are helping the user customize and activate the example weekly review skill. The weekly review is the anchor habit that keeps the whole system healthy — it's where me/ files get updated, priorities get checked, and patterns get noticed.

**Tone:** Encouraging but honest. The weekly review is the thing most people skip. Help them set it up so it's easy enough to actually do.

---

## Step 0: Check prerequisites

Read `me/how-i-work.md` if it exists — their daily rhythm and pain points inform how the review should work.

Read `me/my-priorities.md` if it exists — the review should check progress against these.

---

## Step 1: Find their rhythm

Ask: "When would you actually do a weekly review? Be honest — not when you think you *should*, but when you'd realistically sit down for 15-20 minutes of reflection. Some options:
- Friday afternoon (close out the week while it's fresh)
- Sunday evening (plan the week ahead)
- Monday morning (before the week starts)
- Some other time?"

Wait for their response.

---

## Step 2: Choose their reflection questions

Ask: "The weekly review will ask you a few reflection questions each week. Here are some options — pick the ones that resonate, or tell me your own:

1. What went well this week?
2. What didn't go as planned?
3. What did I learn about my priorities?
4. What's the most important thing for next week?
5. Is there anything I need to say to someone? (a thank you, a tough conversation, a follow-up)
6. What am I avoiding?
7. What should I stop doing?
8. Where did I spend time that wasn't worth it?

Pick 3-5 of these, or tell me what questions you'd rather ask yourself."

Wait for their response.

---

## Step 3: Set output preferences

Ask: "Two quick preferences:
1. **Where should the review be saved?** A file in your workspace, a note in your notes app, or just shown in the terminal?
2. **Should the review update your me/ files?** For example, if you notice a priority has shifted, should the skill suggest edits to `my-priorities.md`? (Recommended — this is how the system stays current.)"

Wait for their response.

---

## Step 4: Create their customized weekly review skill

Read the example skill at `skills/example-weekly-review/SKILL.md` for the base structure.

Create a new skill at `.claude/skills/weekly-review/SKILL.md` customized with:

1. **Their timing** — mention when they plan to run it in the skill description
2. **Their reflection questions** — replace the example questions with theirs from Step 2
3. **Their output destination** — set the save location from Step 3
4. **Their me/ file update preference** — if yes, include a step that reviews me/ files and suggests specific edits
5. **Their connected tools** — if they have a task manager or calendar connected, include a lookback step that pulls completed tasks and past meetings

**Frontmatter:**
```yaml
---
description: Weekly review and planning session. Reflect on the past week, plan the next one, and keep your me/ files current.
user_invocable: true
---
```

**Keep the core structure from the example:**
1. Load context (me/ files)
2. Look back at the week (calendar, completed tasks if available)
3. Guided reflection (ask questions, wait for answers)
4. Plan next week
5. Suggest me/ file updates
6. Save the review

**Key design choice:** The reflection questions should be asked **one at a time** with pauses for the user to respond. This is a conversation, not a form.

---

## Step 5: Set the expectation

Tell them: "Your weekly review is set up. Here's the deal — this is the most important habit in the whole system. Everything else (meeting prep, priorities, team context) degrades if you don't review and update it. But it only takes 15-20 minutes.

Try to run `/weekly-review` at the time you picked for 3 weeks in a row. After 3 weeks, it starts feeling like a habit instead of a chore."

---

## Step 6: Update init.md

If `init.md` exists, mark the weekly review item as complete:
- Change `- [ ] Weekly review skill activated (/init-weekly-review)` to `- [x] Weekly review skill activated (/init-weekly-review)`

---

## Step 7: Wrap up

Tell them:
- Where the skill file lives (`.claude/skills/weekly-review/SKILL.md`)
- How to run it (`/weekly-review`)
- When they planned to run it (remind them of their answer from Step 1)
- "The review will feel a little forced the first time. By week 3, you'll start noticing patterns you wouldn't have caught otherwise."
- Suggest next step based on what's unchecked in `init.md`

Commit: `git add .claude/skills/weekly-review/ init.md && git commit -m "Activate weekly review skill via /init-weekly-review"`

---

## Important rules

- **The reflection questions are the soul of this skill.** Don't rush past the customization. If they pick questions that feel right to them, they'll actually answer them honestly.
- **Encourage honesty over polish.** "I avoided the hard conversation with Jordan again" is more useful than "communication could be improved."
- **The me/ file update step is critical.** Without it, the system slowly rots as priorities shift and team dynamics change. Make this feel like a natural part of the review, not extra homework.
- **Don't over-structure.** Some people want 5 crisp questions. Others want a free-form "what's on your mind?" prompt. Adapt to what they told you.
