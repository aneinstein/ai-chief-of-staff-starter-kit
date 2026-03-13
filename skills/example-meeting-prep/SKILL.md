---
description: Prep my meetings for today
user_invocable: true
---

# Meeting Prep

<!--
  ABOUT THIS EXAMPLE:
  This is a starter meeting prep skill. It works out of the box with
  minimal setup — you just need a calendar connected and your me/ files
  filled in. As you use it, you'll discover what's missing and refine it.

  WHAT TO CUSTOMIZE:
  - The relationship categories (under "Decide what kind of prep")
  - The output format (some people want bullet points, others want prose)
  - How deep the context gathering goes (start shallow, add depth later)
  - Where the output goes (file path, or maybe you want it in your notes app)
-->

## Step 1: Load My Context

Read these files to understand who I am and how I work:
- `me/how-i-work.md` — my rhythms and preferences
- `me/my-team.md` — the people I work with and how I relate to them
- `me/my-priorities.md` — what matters most right now

## Step 2: Get Today's Calendar

Check my calendar for today. For each meeting, gather:
- Meeting title
- Start time and duration
- All attendees (names and roles if available)
- Any description, agenda, or attached documents
- Whether it's a recurring meeting or one-off

## Step 3: Decide What Kind of Prep Each Meeting Needs

<!--
  CUSTOMIZE THIS SECTION:
  These categories should match YOUR world. The examples below are generic
  starting points. Replace them with categories that reflect how you
  actually think about your meetings.

  Common categories people use:
  - 1:1 with direct report / 1:1 with manager / 1:1 with peer
  - Team standup / sprint planning / retrospective
  - Customer meeting / partner meeting / vendor meeting
  - All-hands / town hall / skip-level
  - Interview / hiring debrief
  - Strategy / planning / review

  The key question for each category: what do I need to know going in,
  and what should I have prepared?
-->

For each meeting, classify it and adjust the prep depth:

**1:1 with someone I manage:**
- What have they been working on since we last met?
- Are there any blockers or concerns I should know about?
- Check my notes from our last 1:1 — did I promise to follow up on anything?
- Are there any themes from `me/my-priorities.md` I should bring up?
- Prep level: Medium — focus on listening, not presenting

**1:1 with my manager:**
- What updates do I owe them?
- Are there any decisions I need from them?
- What's the one thing I most want to get out of this meeting?
- Any "heads up" items I should surface before they hear them elsewhere?
- Prep level: High — come with a clear agenda

**Group meeting / team sync:**
- What's my role in this meeting? (Presenting? Listening? Deciding?)
- What should I contribute or update on?
- Are there any decisions expected?
- Prep level: Low to Medium — just know my part

**External meeting (customer, partner, vendor):**
- Who am I meeting with? What's their role?
- What's the history of this relationship?
- What's the goal of this meeting?
- Any recent news about their company?
- Prep level: High — do the research

**Status meeting / standup / all-hands:**
- Do I need to present or share anything?
- If yes, what's my 30-second update?
- Prep level: Minimal — just know if I have a speaking part

## Step 4: Gather Context

For meetings that need Medium or High prep:

1. **Check for shared docs or agendas** — if the meeting invite has a link, read it
2. **Look at recent communication** — any Slack messages, emails, or threads with the attendees in the last few days?
3. **Check my task manager** — any action items related to these people or topics?
4. **Review my last interaction** — when did I last meet with this person and what did we discuss?

<!--
  NOTE: How much context you can gather depends on which MCP connectors
  you have set up. Start with whatever you have — even just a calendar
  makes this useful. Add more data sources over time.

  If you DON'T have a connector for something (e.g., Slack), the skill
  should note "I couldn't check Slack for recent context — you may want
  to glance at your DMs with [person] before this meeting."
-->

## Step 5: Write the Prep

For each meeting, produce a brief that I can scan in under 60 seconds:

```
## [Meeting Title] — [Time]

**Attendees:** [Names and roles]
**Type:** [From Step 3 classification]
**My role:** [What am I here to do — present, decide, listen, support?]

**Context:**
[2-3 bullet points of what I need to know going in. Recent developments,
open threads, relevant priorities.]

**My prep:**
[1-2 bullet points of what I should do or think about. Decisions to make,
updates to share, questions to ask.]

**Follow-up from last time:**
[Anything I promised or that was left open. Skip if nothing.]
```

Order meetings chronologically. Put the first meeting at the top since that's the most urgent.

## Step 6: Save and Surface

Save the output to: `outputs/meeting-preps/[today's date]-meeting-prep.md`

<!--
  ALTERNATIVE OUTPUT DESTINATIONS:
  Some people prefer the prep goes somewhere other than a file:
  - Evernote note (if you use Evernote MCP)
  - Notion page (if you use Notion MCP)
  - Confluence page (if you use Atlassian MCP)
  - Just print it in the terminal (simplest — no file needed)

  Change the destination to wherever you'll actually look at it.
  The best prep document is the one you read.
-->

If any meeting needs HIGH prep and I haven't done it yet, flag it clearly at the top:

```
⚠️ HIGH-PREP MEETINGS TODAY:
- 10:00 — 1:1 with [Manager Name] — you haven't prepped your update yet
- 2:00 — Customer call with [Company] — review the proposal before this
```
