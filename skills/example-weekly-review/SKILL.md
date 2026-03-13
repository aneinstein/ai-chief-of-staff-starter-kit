---
description: Run my weekly review
user_invocable: true
---

# Weekly Review

<!--
  ABOUT THIS EXAMPLE:
  A weekly review is the anchor habit that makes everything else work.
  Without it, your me/ files go stale, your priorities drift, and your
  AI gradually becomes less useful.

  This skill is intentionally conversational — it asks you questions
  rather than just producing a document. The output is a reflection
  that feeds into next week's planning.

  WHEN TO RUN: Friday afternoon or Sunday evening — whenever you
  naturally transition from "this week" to "next week" thinking.

  WHAT TO CUSTOMIZE:
  - The reflection questions (swap in questions that matter to YOU)
  - The planning section (match your actual planning horizon)
  - Where the output goes
  - Whether it updates your me/my-priorities.md automatically
-->

## Step 1: Load My Context

Read these files:
- `me/how-i-work.md` — my rhythms and preferences
- `me/my-priorities.md` — what I said mattered this week
- `me/my-team.md` — people context

## Step 2: Look Back at This Week

Gather data about what actually happened this week:

1. **Calendar review** — What meetings did I have? Were there any that surprised me, got cancelled, or ran long?
2. **Task review** — What did I complete? What's still open? What did I add this week that wasn't planned?
3. **Communication review** — Any important threads or conversations I should remember? (Check email and messages if connectors are available.)

<!--
  NOTE: The depth of this step depends on your connectors. Even with
  just a calendar, the "what meetings did I have" review is valuable.
  Add more data sources as you connect them.
-->

## Step 3: Guided Reflection

Walk me through these questions one at a time. After each question, wait for my response before moving to the next one.

<!--
  CUSTOMIZE THESE QUESTIONS:
  These are starting points. Over time, replace them with questions
  that actually make you think. The best weekly review questions are
  the ones that surface things you'd otherwise miss.

  Some people prefer fewer, deeper questions (3-4).
  Some people prefer more, lighter questions (8-10).
  Experiment and see what works for you.
-->

**Question 1: What went well this week?**
Not just what got done — what went *well*? What am I proud of? What worked better than expected? (This grounds the review in what's working, not just what's broken.)

**Question 2: What didn't go as planned?**
Where did I fall short of my own expectations? What got dropped? What meeting or conversation left me frustrated? (No judgment — just notice the pattern.)

**Question 3: What did I learn about my priorities?**
Look at `me/my-priorities.md` — did I actually spend time on my stated priorities this week? If not, what got in the way? Do the priorities need updating, or do my habits need updating?

**Question 4: What's the most important thing for next week?**
If next week goes perfectly, what one thing will I have made progress on? (This becomes the anchor for next week's planning.)

**Question 5: Is there anything I need to say to someone?**
A thank you I haven't sent. A difficult conversation I've been avoiding. A follow-up I owe someone. An idea I should share.

<!--
  OPTIONAL ADDITIONAL QUESTIONS:
  Add these if they're useful for your situation. Remove if they're not.

  - "What would I do differently if I could replay this week?"
  - "What pattern am I noticing across the last few weeks?"
  - "Am I spending my time on things that only I can do?"
  - "What's draining my energy? What's giving me energy?"
  - "Is there something I should delegate that I'm still holding onto?"
-->

## Step 4: Plan Next Week

After the reflection, shift to planning:

1. **Check next week's calendar** — What's coming up? Any meetings that need prep?
2. **Review open tasks** — What's carrying forward? What can be closed or dropped?
3. **Set intentions** — Based on the reflection, what 2-3 things do I want to focus on?

Produce a simple plan:

```markdown
## Next Week's Focus

### Must do (non-negotiable):
- [Thing 1]
- [Thing 2]

### Should do (important but flexible):
- [Thing 3]
- [Thing 4]

### Prep needed:
- [Meeting that needs advance preparation]

### Follow-ups owed:
- [Person] — [what I promised]
```

## Step 5: Update My Files

<!--
  THIS IS THE KEY STEP THAT MOST PEOPLE SKIP:
  The weekly review isn't just reflection — it's maintenance. Your me/
  files need to stay current or the entire system degrades.
-->

Based on the review, suggest updates to my context files:

- **`me/my-priorities.md`** — Do any priorities need their status updated? Any new priorities? Any that should be removed?
- **`me/my-team.md`** — Did anything change in a key relationship this week? New themes? Resolved tensions?
- **`me/how-i-work.md`** — Did I notice anything about how I work that should be captured? A new pattern, a broken habit, a tool change?

Don't make the changes silently — show me what you'd update and let me confirm. These files are my source of truth and I want to own what's in them.

## Step 6: Save the Review

Save the full review (reflection answers + next week plan) to:
`outputs/weekly-reviews/[today's date]-weekly-review.md`

<!--
  WHY SAVE IT:
  These accumulate over time and become incredibly valuable. After a few
  months, you can look back and see patterns — what keeps showing up,
  what's improving, what's stuck. Your AI can also read past reviews
  to give you better weekly context ("you've mentioned burnout risk
  three weeks in a row — is this something to address?")

  ALTERNATIVE: Save to your notes app (Evernote, Notion, etc.) if you
  want reviews alongside your other reflections.
-->
