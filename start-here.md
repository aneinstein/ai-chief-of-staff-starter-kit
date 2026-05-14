# Build Your First AI Agent This Weekend

You've heard about people using Claude Code to build personal AI systems — agents that prep their meetings, summarize their week, manage their tasks. It sounds impressive and complicated. It's not. You can build your first useful agent in about an hour.

This guide gets you from zero to a working AI agent. No coding experience required.

---

## What You'll Build

A **meeting prep agent** — you say "prep my meetings" and it pulls your calendar, looks up the people you're meeting with, and writes you a one-page brief before your day starts.

It's a small thing. But once you feel the difference between walking into a meeting cold vs. walking in with context your AI pulled together for you, you'll immediately see where else this applies.

## What You Need

- **Claude Code** installed on your computer ([claude.ai/download](https://claude.ai/download))
- **A Google Calendar** (or Outlook — any calendar that has an MCP connector)
- **A markdown editor** — [Obsidian](https://obsidian.md) (free) is recommended. It turns `.md` files into something that looks and feels like a notes app, which makes editing your workspace files much more pleasant if you're not used to working with code.
- **About an hour** of uninterrupted time
- That's it. No APIs to configure. No databases. No deployment.

---

## Step 1: Create Your Workspace

Open your terminal and create a folder. This folder becomes your AI's home base — everything it knows, everything it creates, lives here.

```bash
mkdir ~/ai-workspace
cd ~/ai-workspace
```

Then open Claude Code in that folder:

```bash
claude
```

That's your workspace. Think of it like giving your AI a desk. Right now the desk is empty. Let's furnish it.

## Step 2: Write Your CLAUDE.md

Create a file called `CLAUDE.md` in the root of your workspace. This is the single most important file in the system — it's the set of rules and context that Claude reads at the start of every conversation.

Think of it as the employee handbook for your AI. Here's a minimal one to start:

```markdown
# My AI Workspace

## About This Workspace
This is my personal AI workspace. All files live here.

## Folder Structure
- `me/` — Context about who I am and how I work
- `outputs/` — Things the AI creates for me
- `_claude/` — The AI's working files (scratch space, plans)

## Rules
- Always read files in `me/` before starting a task — that's your context
- Put finished work in `outputs/`
- Ask before doing anything destructive (deleting files, sending messages)
```

That's it. You can — and will — add to this over time. But this is enough to start.

## Step 3: Teach It About You

Create a `me/` folder and add one file: `how-i-work.md`. Write it in plain English. No special format required. Just describe how you work:

```markdown
# How I Work

## My Role
I'm a product manager at a mid-size SaaS company. I manage a team of 4
and report to the VP of Product.

## My Typical Day
- Morning: check Slack, review calendar, prep for meetings
- Most of my day is meetings (6-8 per day)
- I try to block 2-4pm for deep work but it rarely survives
- I capture notes in Apple Notes during meetings

## People I Meet With Most
- Jordan (my manager) — weekly 1:1, Thursdays at 10am
- Sam, Alex, Casey (my direct reports) — weekly 1:1s
- Engineering leads — sprint planning on Mondays
- Customer success — monthly business reviews

## What I Wish I Had More Time For
- Preparing for meetings (I usually walk in cold)
- Following up on action items from meetings
- Thinking strategically instead of reacting
```

This isn't a template to fill in mechanically. Just write about how you actually work. The more honest and specific you are, the more useful your AI becomes.

## Step 4: Build Your First Skill

Skills are reusable prompts that Claude Code can run on command. Create this folder structure:

```
.claude/skills/meeting-prep/SKILL.md
```

And write your first skill:

```markdown
---
description: Prep my meetings for today
user_invocable: true
---

# Meeting Prep

Read the file `me/how-i-work.md` to understand who I am and how I work.

Then check my calendar for today's meetings.

For each meeting:
1. **Who's in the meeting?** List the attendees.
2. **What's the context?** What do I probably need to know going in? Look at
   recent emails or messages with these people if you can.
3. **What should I prepare?** Any decisions I need to make, updates I should
   bring, or questions I should ask?

Write the prep as a simple, scannable document. Put it in `outputs/`.

Keep it short. I'm going to glance at this between meetings, not read an essay.
```

Now in Claude Code, you can type `/meeting-prep` and it runs.

## Step 5: Make It Yours

Your first run won't be perfect. That's the point. After running it, you'll notice things:

- "It spent too long on the standup — I don't need prep for that"
- "It didn't know that Jordan and I have a running doc for our 1:1"
- "I wish it included the last time I met with this person"

Each of those observations becomes an improvement. Add context to `me/how-i-work.md`. Refine the skill prompt. Over time, your system gets sharper because it's learning YOUR patterns, not following someone else's template.

**This is the real insight:** the AI agent isn't a product you download. It's a system you grow. The `me/` folder is the soil. The skills are the plants. And the more you tend it, the more it gives back.

---

## What to Build Next

Once your meeting prep agent is working, here are natural next steps (in rough order of impact):

1. **Morning briefing** — A daily skill that combines your calendar, tasks, and recent messages into a single "here's your day" document. This is the single highest-value skill after meeting prep — it replaces the 15 minutes of tab-switching you do every morning. 2-3 hours to build.

2. **Weekly review** — A Friday afternoon skill that looks at your past week (meetings, tasks, notes) and helps you plan next week. This is the habit that keeps the whole system healthy. 30 minutes to build.

3. **Action item sweep** — A skill that reads your meeting notes and extracts action items, delegated tasks, and follow-ups. The gap between "discussed in a meeting" and "tracked in a system" is where most dropped balls live. 1 hour to build.

4. **Voice memo capture** — Record a 3-5 minute voice memo each evening about your day. Your AI transcribes it and feeds it into tomorrow's briefing. This is the lowest-effort, highest-context input channel. See `architecture-patterns.md` Pattern 4 for how this creates a compounding cycle.

5. **Industry radar** — A skill that scans news, publications, and feeds relevant to your field and produces a curated brief of what matters. Useful when staying current is part of your job but you can't read everything.

Each one teaches you something about how to make the system better. The people who get the most out of this aren't the best programmers — they're the people who are most honest about how they actually work and most willing to iterate.

---

## Common Questions

**Do I need to know how to code?**
No. You're writing prompts in plain English and organizing files in folders. If you can write an email and use Finder, you can do this.

**What if I don't use the same tools?**
The concepts work with any tools. Calendar, notes, tasks — whatever you use. The specifics of connecting tools depend on which MCP connectors are available, but the framework is tool-agnostic.

**How is this different from just asking Claude questions?**
Two things: persistence and context. A regular Claude conversation forgets everything when you close it. Your workspace remembers. And because Claude reads your `me/` files and `CLAUDE.md` every time, it starts each conversation already knowing how you work. That's the difference between a stranger and a chief of staff.

**How long before it's actually useful?**
The meeting prep agent is useful on day one. The system becomes transformative over weeks as you add more context to `me/` and build more skills. Most people hit an inflection point around week 3 where they stop thinking of it as a tool and start thinking of it as a teammate.
