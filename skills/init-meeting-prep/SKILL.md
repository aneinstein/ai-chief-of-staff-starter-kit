---
description: Activate your meeting prep skill. Walks you through customizing the example meeting prep for your tools, meeting types, and preferences. Use /init-meeting-prep when you're ready to set up automated meeting prep.
user_invocable: true
---

# Activate Your Meeting Prep Skill

You are helping the user customize and activate the example meeting prep skill for their specific setup. By the end, they'll have a working `/meeting-prep` command.

**Tone:** Practical, hands-on. You're setting something up together, not lecturing about architecture.

---

## Step 0: Check prerequisites

Read `me/my-tools.md` if it exists — you need to know what calendar they use.

Read `me/my-team.md` if it exists — the skill works better with relationship context.

If neither exists, let them know: "For the best results, I'd suggest running `/init` first to set up your basics. But we can set up meeting prep now and add context later — it'll just be more generic at first."

---

## Step 1: Understand their calendar setup

Ask: "What calendar do you use? And do you have it connected to Claude Code via an MCP connector?"

**If they don't know what MCP is**, explain briefly: "MCP connectors let Claude Code read your calendar directly — so the meeting prep skill can automatically pull today's meetings. Without one, you'd need to paste your meeting list manually. Check Claude Code's docs for available connectors."

**If they have a connector:** Great, the skill can query their calendar automatically.

**If they don't have a connector:** The skill will ask them to paste their meeting list. This still works — it's just manual.

---

## Step 2: Understand their meeting types

Ask: "What types of meetings fill your calendar? For example:
- 1:1s with direct reports
- 1:1 with your manager
- Team syncs or standups
- Cross-functional meetings
- External calls (customers, partners, vendors)
- Board or leadership meetings
- Something else?

Which of these do you have, and which ones do you most want prep for?"

Wait for their response.

---

## Step 3: Understand their output preferences

Ask: "Two quick preferences:
1. **Where do you want meeting preps saved?** Options: a file in your workspace, printed to the terminal, sent to a notes app, or something else?
2. **How much detail do you want?** Quick bullet points (30 seconds to scan) or deeper context (2-3 minutes of reading per meeting)?"

Wait for their response.

---

## Step 4: Create their customized meeting prep skill

Read the example skill at `skills/example-meeting-prep/SKILL.md` for the base structure.

Create a new skill at `.claude/skills/meeting-prep/SKILL.md` customized with:

1. **Their calendar tool** — update the "get today's calendar" step to reference their specific tool and connector (or manual paste)
2. **Their meeting types** — replace the example meeting categories with their actual types from Step 2
3. **Their relationship context** — if `me/my-team.md` exists, reference it for 1:1 prep
4. **Their output preferences** — set the save location and detail level from Step 3
5. **Their context sources** — based on what tools they have connected (task manager, notes, chat), customize which context-gathering steps are included

**Frontmatter:**
```yaml
---
description: Prep for today's meetings. Pulls calendar, gathers context, produces a scannable prep sheet.
user_invocable: true
---
```

**Keep the core structure from the example:**
1. Load context (me/ files)
2. Get today's calendar
3. Classify each meeting
4. Gather context per meeting
5. Format the prep
6. Save the output

**Customize the details** based on what they told you. Add comments like `<!-- Customize: add more meeting types as your role evolves -->` where appropriate.

---

## Step 5: Test it

Tell them: "Your meeting prep skill is set up. Try running `/meeting-prep` now and let's see what happens."

**If they run it and share the output**, help them evaluate:
- Did it find all their meetings?
- Were the meeting types classified correctly?
- Was the context useful or generic?
- What's missing?

**If something is off**, suggest specific fixes to the SKILL.md or their me/ files.

---

## Step 6: Update init.md

If `init.md` exists, mark the meeting prep item as complete:
- Change `- [ ] Meeting prep skill activated (/init-meeting-prep)` to `- [x] Meeting prep skill activated (/init-meeting-prep)`

---

## Step 7: Wrap up

Tell them:
- Where the skill file lives (`.claude/skills/meeting-prep/SKILL.md`)
- How to run it (`/meeting-prep`)
- "Run it for a few days in a row. You'll notice what's missing or wrong — each observation is a small edit to the skill file or your me/ files."
- "The first run is always the worst. By day 3-4, it starts feeling useful."
- Suggest next step based on what's unchecked in `init.md`

Commit: `git add .claude/skills/meeting-prep/ init.md && git commit -m "Activate meeting prep skill via /init-meeting-prep"`

---

## Important rules

- **Don't over-engineer.** The first version should be simple — calendar + basic context. They'll add complexity as they learn what they need.
- **Respect missing tools.** If they don't have Slack connected, don't include Slack context steps. The skill should work with what they have.
- **The example skill is a starting point, not gospel.** Customize freely based on what the user actually needs.
- **Encourage iteration.** The whole point is that version 1 is mediocre. Make that feel normal, not like a failure.
